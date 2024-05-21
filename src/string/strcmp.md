# 文字列の比較

文字列の比較とは、2つの文字列が同じかどうかを判定することです。C言語で文字列の比較を行うには、`strcmp`関数を使います。同じ文字列であれば、`0` が返ります。異なる文字列であれば、辞書順で比較した際、どちらが先かによって、正の値か負の値が返ります。以下に　入力された文字列が`TUAT`と一致するかどうかを判定するプログラムを示します。

```c
#include <stdio.h>
#include <string.h>

int main(){
    char tuatStr[] = "TUAT";
    char inputstr[16];
    int result;

    printf("Input TUAT\n");
    scanf("%s", inputstr);

    result = strcmp(tuatStr, inputstr);

    if(result == 0){
        printf("Correct\n");
    }else{
        printf("Incorrect\n");
    }

    printf("result = %d\n", result);
}
```

`TUAT`と入力すると、以下のように表示されます。

```txt
Input TUAT
TUAT
Correct
result = 0
```

同じ文字列であるため、 `result` は `0` になります。

`tuat`と入力すると、以下のように表示されます。

```txt
Input TUAT
tuat
Incorrect
result = -32
```

`TUAT` と `tuat` は異なる文字列で、 `tuat` は辞書順で `TUAT` よりも後ろであるため、`result` は負の値になります。

`MCC`と入力すると、以下のように表示されます。

```txt
Input TUAT
MMC
Incorrect
result = 7
```

`TUAT` と `MCC` は異なる文字列で、 `MCC` は辞書順で `TUAT` よりも前であるため、`result` は正の値になります。
