# printf

printfは画面に文字を表示するための関数です。

使用例：

```c
int main(){
    printf("Hello World\n");
}
```

## 変数の出力

整数型の`int`はprintfの文字列の中に`%d`を入れることで表示することができます。

```c
int main(){
    int a = 10;
    printf("a = %d\n", a);
}
```

他にも浮動小数点の出力には`%f`,文字列の出力には`%s`など他にもいくつか使用できます。