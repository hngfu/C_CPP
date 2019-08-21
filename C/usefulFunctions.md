# 몇몇 유용한 함수들

## getchar, putchar

```c
#include <stdio.h>

int main() {
    char ch;

    ch = getchar();     // 입력
    putchar(ch);        // 출력
}
```
> 실행화면
```
4
4
```

## sscanf, sprintf

```c
#include <stdio.h>

int main() {
    char str[] = "4646";
    int n;

    sscanf(str, "%d", &n);
    sprintf(str, "%d", n + 1);

    printf("%s", str);
}
```
> 실행화면
```
4647
```

## random

```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main() {
    srand(time(0));
    for (int i = 0; i < 10; i++) {
        printf("%d\n", rand() % 10);
    }
}
```

> 실행화면
```
0
8
4
3
0
8
7
4
0
8
```

그냥 rand()만 쓰면 항상 같은 값이 나온다.  
시드를 설정해서 다른 수가 나오도록 해줘야 함.

## exit

```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main() {
    srand(time(0));
    for (int i = 0; i < 10; i++) {
        if (i == 1) exit(0);
        printf("%d\n", rand() % 10);
    }
}
```

> 실행화면

```
2
```

exit(0)으로 프로그램 종료 가능