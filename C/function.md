# 함수

```c
#include <stdio.h>

// 프로토 타입
void swap(int*, int*);

int main() {
    int a = 4;
    int b = 6;

    swap(&a, &b);
    printf("a: %d, b: %d", a, b);
}

void swap(int *lhs, int *rhs) {
    int tmp = *lhs;
    *lhs = *rhs;
    *rhs = tmp;
}
```

> 실행화면
```
a: 6, b: 4
```