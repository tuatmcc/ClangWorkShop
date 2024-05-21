# 文字列の連結

文字列の連結とは、複数の文字列を一つの文字列に結合することです。C言語においては、文字列の連結を行うために`strcat`関数があります。 `strcat`関数は、2つの文字列を連結して、1つの文字列にします。以下に、`strcat`関数を使って文字列を連結するプログラムを示します。

```c
#include <stdio.h>
#include <string.h>

int main(){
    char str1[16] = "Hello ";
    char str2[16];

    scanf("%s", str2);

    strcat(str1, str2);
 
    printf("%s\n", str1);
}
```

`World` と入力すると、以下のように表示されます。

```txt
World
Hello World
```

イメージ図を示します。`str1` と `str2` は、それぞれの文字列を表しています。`str1` は、`Hello` という文字列で初期化されています。`str2` に入力された文字列が連結されて、`str1` に格納されます。

![文字列の連結](./strcat.svg)
