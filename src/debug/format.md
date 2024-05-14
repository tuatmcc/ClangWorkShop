# clang-format

フォーマットが整っていないプログラムは書き手にとっても読み手にとっても分かりづらいだけでなく、バグを探すことを難しくしてしまいます。そこで、フォーマッタを使ってみましょう。

## clang-format のインストール

### MacOS

- [brew のインストール](https://brew.sh/ja/)
- `brew install clang-format`の実行

### Windows

- WSL 上で Linux と同様の手順を行う

### Linux

- `sudo apt update && sudo apt install -y clang-format`の実行

## 使用例

こんなコードが

```c
#include <stdio.h>


int main(){
int array[
5
] ={1,2,3,4,5};
for
(int i; i<5;
i++){printf("%d\n",array[i]);
}}
```

これを実行するだけで

```shell
$ clang-format hello.c -i
```

こうなります！

```c
#include <stdio.h>

int main() {
  int array[5] = {1, 2, 3, 4, 5};
  for (int i; i < 5; i++) {
    printf("%d\n", array[i]);
  }
}
```

だいぶ読みやすくなったのではないでしょうか？
