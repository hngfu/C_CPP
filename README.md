# C 와 C++
흥푸의 기초다지기 시리즈 1

## C

### 변수

```c
int a;
```

`주기억장치`인 `RAM(Random Access Memory)`에 4byte크기의 정수형 데이터를 넣을 수 있는 공간이 생김.

> byte란?
- 정보의 최소 `처리` 단위
- 1byte == 8bit

> bit란?
- Binary Digit를 줄인 말.
- 정보의 최소 단위

### 자료형
#### 크기

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

>32bit 컴퓨터의 경우
```
long의 크기: 4
long double의 크기: 12
가 다르다고 함.
```

#### 포인터의 크기

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

>실행결과 (64bit 컴퓨터의 경우)
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

>32bit 컴퓨터의 경우
```
포인터의 크기가 전부 4byte
```

### 입출력

```c
#include <stdio.h>

int main() {
    int first, second;
    scanf("%d %d", &first, &second);
    printf("first: %d, second: %d", first, second);
}
//4 3 (입력)
//first: 4, second: 3 (출력)
```

#### 다양한 데이터 출력

```c
#include <stdio.h>

int main() {
    printf("정수 출력: %d\n", 6);
    printf("실수 출력: %f\n", 6123.1234);
    printf("실수 출력: %.2f\n", 6123.1234);
    printf("실수 출력: %g\n", 4123.123456);
    printf("실수 출력: %.2g\n", 4123.123456);
    printf("문자 출력: %c\n", 'H');
    printf("문자열 출력: %s\n", "호잇~!");
}
```

> 실행화면

```
정수 출력: 6
실수 출력: 6123.123400
실수 출력: 6123.12  //소수 둘째까지 반올림해서 출력해라
실수 출력: 4123.12  //6개의 숫자만 보여줌
실수 출력: 4.1e+03  //앞에서부터 2개만 보여줌. 4.1에 10^3을 해라
문자 출력: H    //영어는 1byte인데 한글은 2byte임
문자열 출력: 호잇~!   //char배열의 NULL문자까지 출력해라
```