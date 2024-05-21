# 文字列の長さ

文字列の長さを取得するには、`strlen` 関数を使用します。 `strlen` 関数は、文字列の長さを返します。 `#include <string.h>` が必要です。

以下に、最大15文字の入力された文字列の長さを表示するプログラム例を示します。

```c
#include <stdio.h>
#include <string.h>

int main(){
    char str[16];
    int length;

    scanf("%s", str);

    length = strlen(str);

    printf("length = %d\n", length);
}
```

`tuat` と入力すると、以下のように表示されます。

```txt
tuat
length = 4
```

`012345678901234` と入力すると、以下のように表示されます。

```txt
012345678901234
length = 15
```

以下にイメージ図を示します。文字列の最後には、ヌル文字が追加されています。

![文字列のメモリ上の配置](./strlen1.svg)

`strlen` 関数は、char 型の配列で、ヌル文字 (`\0`) までの文字をカウントしてくれます。
