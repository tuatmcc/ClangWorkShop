# 構造体

構造体とは、複数の異なるデータをまとめて扱うデータ構造です。構造体を使うことで、複数のデータを一つのデータとして扱うことができます。

以下に人の情報をまとめた構造体 `Person` という構造体名を宣言する例を示します。

```c
struct Person{
    char name[16];
    int age;
    double height;
};
```

`Person` には、 `name` 、 `age` 、 `height` という変数が含まれています。これらのように構造体の中に含まれる変数を**メンバ**(メンバ変数)と呼びます。変数の箱の中に変数の箱が入ってるのをイメージしてください。

以下に、構造体を使って人の情報を表示するプログラムを示します。構造体のメンバにアクセスするには、`.` (ドット(直接メンバ参照演算子)) を使います。

```c
#include <stdio.h>
#include <string.h>

struct Person{
    char name[16];
    int age;
    double height;
};

int main(){
    struct Person person;

    person.age = 24;
    person.height = 180.5;
    strcpy(person.name, "daniel");

    printf("Name: %s\n", person.name);
    printf("Age: %d\n", person.age);
    printf("Height: %.1f\n", person.height);
}
```

実行すると、以下のように表示されます。

```txt
Name: daniel
Age: 20
Height: 180.5
```

構造体は、異なるデータ型をまとめて扱うことができます。上記の例では、`name`は文字列、`age`は整数、`height`は浮動小数点数を扱っています。
