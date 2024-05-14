# サニタイザー
サニタイザーとはコンパイラについている機能でプログラム中で明らかにおかしいことをした場合に知らせてくれる機能です。

## 使用方法

`hello.c`をgccでコンパイルする際にオプションをつけることで有効化できます。通常このようにコンパイルするところを、

```shell
$ gcc hello.c
```

このように変更します。

```shell
$ gcc hello.c -fsanitize=undefined -g
```

これで有効になります。

## 使用例 -配列の要素外アクセス-

次のプログラムで配列の最後の要素を出力しようとしてもうまく行きません。

```c
#include <stdio.h>

int main(){
    int array[3] = {1,2,3};
    printf("%d\n", array[3]); // ???
}
```

サニタイザを有効にして確認してみると、このような出力が出ます。

```
test.c:5:25: runtime error: index 3 out of bounds for type 'int [3]'
test.c:5:5: runtime error: load of address 0x7ffe370d7ac0 with insufficient space for an object of type 'int'
0x7ffe370d7ac0: note: pointer points here
 03 00 00 00  01 00 00 00 00 00 00 00  0e d1 03 b0 b9 7f 00 00  d8 7b 0d 37 fe 7f 00 00  46 11 40 00
              ^ 
1
```

何やら難しいことが書いてありますが、一行目に着目してみると、

```
index 3 out of bounds for type 'int [3]'
```

と書いてあります。
配列の添字は0から数えるので0,1,2しかないですね。しかし3にアクセスしようとしているよ！という内容のエラーです。
読み方さえわかってしまえばありがたいエラーメッセージですね。

