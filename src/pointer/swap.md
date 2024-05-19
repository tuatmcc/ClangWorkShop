# Swap 関数

Swap 関数は、2 つの変数の値を交換する関数です。

以下のコードを書いたら、実行する前に 1回目の `printf` と 2回目の `printf` の出力を予想してみましょう。

```c
#include <stdio.h>

void swap(int a, int b)
{
    int tmp;

    tmp = a;
    a = b;
    b = tmp;
}

int main()
{
    int n = 100;
    int m = 200;

    printf("n = %d, m = %d\n", n, m);
    swap(n, m);
    printf("n = %d, m = %d\n", n, m);
}
```

このコードを実行すると、以下のようになります。

```txt
n = 100, m = 200
n = 100, m = 200
```

これは、関数呼び出しを行うと、引数の値はコピーされるためです。関数内で値を変更しても、元の変数には影響がありません。以下に先程のプログラムのイメージ図を示してます。

![copyswap](./3.svg)
