# 文字列のコピー

文字列をコピーするには、`strcpy`関数を使います。

```c
#include <stdio.h>
#include <string.h>

int main(){
    char str1[16] = "Hello ";
    char str2[16] = "World";

    strcpy(str1, str2);

    printf("%s\n", str1);
}
```

実行すると、以下のように表示されます。

```txt
World
```

`strcpy`関数は、`str2`の文字列を`str1`にコピーします。`str1`の文字列は`Hello`から`World`に変わります。

以下にイメージ図を示します。`str1`と`str2`は、それぞれ別のメモリ領域に配置されています。`strcpy`関数を使うことで、`str2`の文字列を`str1`にコピーします。

![文字列のコピー](./strcpy.svg)
