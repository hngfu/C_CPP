# 자료형
## 크기

```c
#include <stdio.h>

int main() {
    printf("정수형----\n");
    printf("char의 크기: %d\n", sizeof(char));
    printf("short의 크기: %d\n", sizeof(short));
    printf("int의 크기: %d\n", sizeof(int));
    printf("long의 크기: %d\n", sizeof(long));
    printf("long long의 크기: %d\n", sizeof(long long));

    printf("실수형----\n");
    printf("float의 크기: %d\n", sizeof(float));
    printf("double의 크기: %d\n", sizeof(double));
    printf("long double의 크기: %d\n", sizeof(long double));

    printf("------\n");
    printf("부호가 있는 변수 signed(default)\n");
    printf("부호가 없는 변수 unsigned\n");
    printf("signed int의 크기: %d\n", sizeof(signed int));
    printf("unsigned int의 크기: %d\n", sizeof(unsigned int));
}
```

> 실행결과 (64bit 컴퓨터의 경우)
```
*단위는 byte
정수형----
char의 크기: 1
short의 크기: 2
int의 크기: 4
long의 크기: 8
long long의 크기: 8
실수형----
float의 크기: 4
double의 크기: 8
long double의 크기: 16
------
부호가 있는 변수 signed(default)
부호가 없는 변수 unsigned
signed int의 크기: 4
unsigned int의 크기: 4
```

> 32bit 컴퓨터의 경우
```
long의 크기: 4
long double의 크기: 12
가 다르다고 함.
```

## 포인터의 크기

```c
#include <stdio.h>

int main() {
    printf("정수형----\n");
    printf("char*의 크기: %d\n", sizeof(char*));
    printf("short*의 크기: %d\n", sizeof(short*));
    printf("int*의 크기: %d\n", sizeof(int*));
    printf("long*의 크기: %d\n", sizeof(long*));
    printf("long long*의 크기: %d\n", sizeof(long long*));

    printf("실수형----\n");
    printf("float*의 크기: %d\n", sizeof(float*));
    printf("double*의 크기: %d\n", sizeof(double*));
    printf("long double*의 크기: %d\n", sizeof(long double*));

    printf("------\n");
    printf("부호가 있는 변수 signed(default)\n");
    printf("부호가 없는 변수 unsigned\n");
    printf("signed int*의 크기: %d\n", sizeof(signed int*));
    printf("unsigned int*의 크기: %d\n", sizeof(unsigned int*));
}
```

> 실행결과 (64bit 컴퓨터의 경우)
```
*단위는 byte
정수형----
char*의 크기: 8
short*의 크기: 8
int*의 크기: 8
long*의 크기: 8
long long*의 크기: 8
실수형----
float*의 크기: 8
double*의 크기: 8
long double*의 크기: 8
------
부호가 있는 변수 signed(default)
부호가 없는 변수 unsigned
signed int*의 크기: 8
unsigned int*의 크기: 8
```

> 32bit 컴퓨터의 경우
```
포인터의 크기가 전부 4byte
```
