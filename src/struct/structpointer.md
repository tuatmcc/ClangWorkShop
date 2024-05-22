# 構造体のポインタ変数

構造体のポインタ変数も使うことができます。構造体のポインタ変数も宣言時には、普通のポインタ変数の宣言と同じように、`*`を変数名の前につけます。また、構造体のアドレスを取得するのにも、普通のポインタ変数と同様に `&`を変数名の前につけます。

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
	struct Person *p;

    person.age = 24;
    person.height = 180.5;
    strcpy(person.name, "daniel");

	p = &person;
	
	printf("Name: %s\n", (*p).name);
	printf("Age: %d\n", (*p).age);
	printf("Height: %.1f\n", (*p).height);
}
```

実行すると、以下のように表示されます。

```txt
Name: daniel
Age: 20
Height: 180.5
```

## アロー演算子

構造体のポインタ変数を使う場合、`(*p).name` のように、`*`を使って構造体のメンバにアクセスすることができます。C 言語では、構造体ポインタが示すアドレスにある構造体のメンバにアクセスするための演算子として、`->` (アロー演算子)が用意されています。アロー演算子を使うと、`(*p).name` は `p->name` と書くことができます。

上記のプログラムをアロー演算子を使って書き換えると以下のようになります。

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
	struct Person *p;

    person.age = 24;
    person.height = 180.5;
    strcpy(person.name, "daniel");

	p = &person;
	
	printf("Name: %s\n", (*p).name);
	printf("Age: %d\n", (*p).age);
	printf("Height: %.1f\n", (*p).height);
}
```

実行すると、以下のように表示されます。

```txt
Name: daniel
Age: 20
Height: 180.5
```