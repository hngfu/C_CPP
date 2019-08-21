# 비트 연산자

```c
#include <stdio.h>

int main() {
    char a = 12, b = 10;

    printf("%d\n", a & b);  // 둘다 1이어야 1
    printf("%d\n", a | b);  // 하나만 1이면 1
    printf("%d\n", a ^ b);  // 두개가 다르면 1, 같으면 0
    printf("%d\n", ~a);     // 반전
}
```

> 실행화면
```
8
14
6
-13
```

```c
#include <stdio.h>

int main() {
    char a = 22;

    printf("%d\n", a << 1);     // 44
    printf("%d\n", a << 4);     // 352
    printf("%d\n", a << 6);     // 1408
    printf("%d\n", a >> 1);     // 11
    printf("%d\n", a >> 4);     // 1
    printf("%d\n", a >> 6);     // 0
}
```

```c
#include <stdio.h>

int main() {
    char a = 22;

    printf("%d\n", sizeof(a));          // 1
    printf("%d\n", sizeof(a << 4));     // 4
    printf("%d\n", sizeof(a << 6));     // 4
}
```