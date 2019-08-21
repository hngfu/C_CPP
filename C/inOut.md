# 입출력

```c
#include <stdio.h>

int main() {
    int first, second;
    scanf("%d %d", &first, &second);
    printf("first: %d, second: %d", first, second);
}
// 4 3 (입력)
// first: 4, second: 3 (출력)
```

## 다양한 데이터 출력

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