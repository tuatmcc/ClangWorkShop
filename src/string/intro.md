# 文字列

**文字列**は、**文字**の並びです。 C 言語では、文字列は文字の配列として表現されます。

```c
#include <stdio.h>

int main(){
    char str1[] = "Hello, World!";
    char str2[14] = {'H', 'e', 'l', 'l', 'o', ',', ' ', 'W', 'o', 'r', 'l', 'd', '!', '\0'};
    
	printf("%s\n", str1);
	printf("%s\n", str2);
}
```

