# 構造体

構造体とは、複数の異なるデータをまとめて扱うデータ構造です。構造体を使うことで、複数のデータを一つのデータとして扱うことができます。以下に人の情報をまとめた構造体の例を示します。

```c
#include <stdio.h>
#include <string.h>

struct Person{
    char name[16];
    int age;
    double height;
};

int main(){
    struct Person person1;

    person1.age = 24;
    person1.height = 180.5;
    strcpy(person1.name, "daniel");

    printf("Name: %s\n", person1.name);
    printf("Age: %d\n", person1.age);
    printf("Height: %.1f\n", person1.height);
}
```

実行すると、以下のように表示されます。

```txt
Name: daniel
Age: 20
Height: 180.5
```

構造体は、異なるデータ型をまとめて扱うことができます。上記の例では、`name`は文字列、`age`は整数、`height`は浮動小数点数を扱っています。

構造体の配列を作ることもできます。以下に構造体の配列を作る例を示します。

```c
#include <stdio.h>
#include <string.h>

struct Person{
    char name[16];
    int age;
    double height;
};

int main(){
    struct Person people[3];

    strcpy(people[0].name, "daniel");
    people[0].age = 24;
    people[0].height = 180.5;

    strcpy(people[1].name, "sugawa");
    people[1].age = 22;
    people[1].height = 164.4;

    strcpy(people[2].name, "genchan");
    people[2].age = 21;
    people[2].height = 170.3;

    for(int i = 0; i < 3; i++){
        printf("Name: %s\n", people[i].name);
        printf("Age: %d\n", people[i].age);
        printf("Height: %.1f\n", people[i].height);
    }
}
```

実行すると、以下のように表示されます。

```txt
Name: daniel
Age: 24
Height: 180.5
Name: sugawa
Age: 22
Height: 164.4
Name: genchan
Age: 21
Height: 170.3
```
