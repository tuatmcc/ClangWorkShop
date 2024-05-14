# アサーション

この機能は紹介だけに留めます。
アサーションはプログラム中に現在この条件を満たしていますか？ということを確認する機能です。

## 使用例 -入力が正であることを確認-

10 を入力値で割るプログラムで受け取った入力が 0 ではないことを確認したい。

```c
#include <stdio.h>
#include <assert.h>

int main(){
    int n;
    scanf("%d",&n);
    assert(n!=0);
    printf("%d\n", 10 / n);
}
```

2 を入力した場合

```shell
$ ./a.out
2
5
```

0 を入力した場合

```shell
$ ./a.out
0
a.out: test.c:7: main: Assertion `n!=0' failed.
zsh: IOT instruction (core dumped)  ./a.out
```
