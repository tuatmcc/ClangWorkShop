# 参照 Swap 関数

Swap 関数は、2 つの変数の値を交換する関数です。しかし、 Swap 関数の引数を普通の変数にした場合、値がコピーされるため、正しく値を交換することはできませんでした。

次は、 Swap 関数の 2 つの引数をポインタ変数にしてみましょう。以下のコードを書いたら、実行する前に 1回目の `printf` と 2回目の `printf` の出力を予想してみましょう。

```c
#include <stdio.h>

void swap(int *a, int *b)
{
    int tmp;

    tmp = *a;
    *a = *b;
    *b = tmp;
}

int main()
{
    int n = 100;
    int m = 200;

    printf("n = %d, m = %d\n", n, m);
    swap(&n, &m);
    printf("n = %d, m = %d\n", n, m);
}
```

このコードを実行すると、以下のようになります。

```txt
n = 100, m = 200
n = 200, m = 100
```

ポインタ変数を使い、main 関数の変数 `n`、`m` のアドレスを swap 関数に渡し、swap 関数でそのアドレスを参照することで、値を交換することができました。以下に先程のプログラムのイメージ図を示してます。

![refswap](./refswap.svg)
