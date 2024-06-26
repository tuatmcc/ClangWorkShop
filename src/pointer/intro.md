# ポインタ

ポインタは、メモリアドレスを格納するための変数です。メモリアドレスは、コンピュータのメモリ上の位置を示します。

## 値のコピー

変数を、別の変数に代入したら、元の変数の値がコピーされます。以下のコードを実行してみましょう。

```c
#include <stdio.h>

int main()
{
    int n;
    int m;

    n = 100;
    m = n;
    n = 200;

    printf("n = %d, m = %d\n", n, m);
}
```

このコードを実行すると、`n = 200, m = 100` と表示されます。`n` に `100` を代入した後、`m` に `n` を代入しています。その後、`n` に `200` を代入していますが、`m` には影響がありません。 `m` に `n` を代入したときに、`n` の値がコピーされます。

コンピューターのメモリは、変数の箱が並んでいる数直線のようにイメージすることができます。そして、それぞれの変数に対してメモリの**アドレス** (番地) が存在します。 先程のプログラムを図にすると以下のようになります。(以下の例では `n` のアドレスを 102番地、 `m` のアドレスを 103番地 としています。)

![値のコピー](./intro1.svg)

## 値の参照

**ポインタ変数**を使うと、変数のアドレスを格納することができ、**変数のメモリアドレスを使ったプログラミング**をすることができます。ポインタ変数の宣言には、変数の宣言時に変数名の前に `*` (アスタリスク) をつけます。変数のアドレスを取得するには、変数名の前に `&` をつけます。 ポインタ変数に格納されているアドレスに格納されている値を参照するには、変数名の前に `*` をつけます。以下のコードを書いて実行して、書き方と挙動を確認してみましょう。

```c
#include <stdio.h>

int main()
{
    int n;
    int *p;

    n = 100;
    p = &n;
    n = 200;

    printf("n = %d, *p = %d\n", n, *p);
}
```

このコードを実行すると、`n = 200, *p = 200` と表示されます。以下の図に先ほどのプログラムのイメージ図を示してます。 `n` に `100` を代入した後、`p` に `n` の**アドレス**を代入しています。 その後、`n` に `200` を代入します。`printf` の `*p` は、`p` が参照しているアドレスにある値を示します (ここでは 102番地の値)。そのため、`*p` は `n` の値を参照してるため、 `200` になります。

![値の参照](./intro2.svg)

## `printf` でメモリアドレスを表示

`printf` でメモリアドレスを表示する場合、 `%p` を使います。先程のプログラムに、`printf` でポインタ変数 `p` に格納されているアドレスと `p` のアドレスと `n` のアドレスを表示する処理を追加したプログラムを示します。

```c
#include <stdio.h>

int main()
{
    int n;
    int *p;

    n = 100;
    p = &n;
    n = 200;

    printf("n = %d, *p = %d\n", n, *p);
    printf("p = %p, &p = %p, &n = %p\n", p, &p, &n);
}
```

このコードを実行すると、以下のように表示されます。アドレスは 16 進数で表示されます。 `p` には、 `n` のアドレスが格納されているのがわかります。また、`p` と `n` のアドレス(つまり `&p` と `&n`) は別の変数であるため、異なるアドレスであることがわかります。
メモリアドレスは実行するたびに変わります。

```txt
n = 200, *p = 200
p = 0x7fff8bf26a2c, &p = 0x7fff8bf26a30, &n = 0x7fff8bf26a2c
```

図での例では、以下の用に表示されます。(わかりやすく、10進数で表示しています。)

```txt
n = 200, *p = 200
p = 102, &p = 103, &n = 102
```

![ポインタのアドレス](./intro3.svg)
