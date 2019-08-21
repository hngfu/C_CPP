# 구조체 포인터

```c
#include <stdio.h>

int main() {
    typedef struct {
        int x, y;
    } Coordinate;
    Coordinate coordinate = { 4, 6 };
    Coordinate *ptr_coordinate = &coordinate;
    printf("x: %d, y: %d", (*ptr_coordinate).x, ptr_coordinate->y);
}
```

> 실행화면
```
x: 4, y: 6
```

```c
// Coordinate 자료형의 경우
Coordinate *ptr_coordinate = &coordinate;

// int 자료형의 경우
int *ptr_foo = &foo;
```
구조체 포인터의 선언과 할당은 일반적인 경우와 같다.

## 구조체 포인터로 property 접근하기

`(*ptr_coordinate).x == ptr_coordinate->x`  
