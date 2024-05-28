# 構造体の動的メモリ確保

構造体の動的メモリ確保は、構造体のサイズを `sizeof` で取得し、`malloc` 関数で確保します。

以下のコードを実行してみましょう。

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

struct Person{
    char name[16];
    int age;
    double height;
};

int main(){
    struct Person *person;
    person = (struct Person *)malloc(sizeof(struct Person));

    person->age = 24;
    person->height = 180.5;
    strcpy(person->name, "daniel");

    printf("Name: %s\n", person->name);
    printf("Age: %d\n", person->age);
    printf("Height: %.1f\n", person->height);

    free(person);
}
```

メモリを確保したときのメモリのイメージ図を以下に示します。malloc関数では、指定したサイズのメモリを確保し、確保したメモリのアドレスを返します。ポインタの構造体であるため、アロー演算子を使ってメンバにアクセスしましょう。

![メモリの確保](2.svg)
