# 入力

標準入力から入力を受けとります。キーボードで入力を行い、Enter を押したところまでを取得してくれます。また、`%d`などの表現を用いることで整数などへの型変換も行ってくれます。

数値を受け取ってその倍の値を出力するプログラムの例：

```c
int main(){
    int n;
    scanf("%d", &n);
    printf("%d\n", n);
}
```
