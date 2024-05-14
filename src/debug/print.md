# printデバッグ
プログラムの様々な場所にprintfを入れてどこまで動いたか、望んだ通りの挙動をしているか確認する方法です。単純ですがとても効果的な方法です。

## 例：1+2+...+5のプログラム
このようなプログラムを書いたとしましょう。

```c
#include <stdio.h>

int main(){
    int sum = 0;
    for (int i = 1; i < 5; i++) {
        sum += i;
    }
    printf("%d\n", sum); // 10
}
```

答えは15になるはずですが、10になってしまっていますね。

ではprintfをループ内に入れて確認してみましょう。

```diff
 #include <stdio.h>
 
 int main(){
     int sum = 0;
     for (int i = 1; i < 5; i++) {
         sum += i;
+        printf("i=%d, sum=%d\n", i, sum);
     }
     printf("%d\n", sum); // 10
 }
```

出力を見ると次のようになっているはずです。
```
1, 1
2, 3
3, 6
4, 10
10
```

5回目が入っていないようですね。これは不等号の書き間違いのようなのでこのように修正すると動くでしょう。

```diff
 #include <stdio.h>
 
 int main(){
     int sum = 0;
-    for (int i = 1; i < 5; i++) {
+    for (int i = 1; i <= 5; i++) {
         sum += i;
         printf("i=%d, sum=%d\n", i, sum);
     }
     printf("%d\n", sum); // 15
 }
```

