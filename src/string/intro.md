# 文字列

**文字列**は、**文字**の並びです。 C 言語では、文字列は文字の配列として表現されます。

```c
#include <stdio.h>

int main(){
    char str1[] = "TUAT";
	char str2[] = {'T', 'U', 'A', 'T', '\0'};
    
	printf("%s\n", str1);
	printf("%s\n", str2);
}
```

