# 構造体の配列

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
