# 상수

## const

```c
#include <stdio.h>

int main() {
    int foo = 4;
    foo = 6;
    printf("%d", foo);  // 6이 출력됨.
}
```
```c
#include <stdio.h>

int main() {
    const int foo = 4;  // const가 붙어서
    foo = 6;            // foo에 값을 할당할 수 없게됨. 에러
    printf("%d", foo);
}
```

## 매크로

```c

#include <stdio.h>

#define PI 3.141592

int main() {
    printf("파이값: %lf", PI);
}
```

> 실행화면

```
파이값: 3.141592
```

`#define PI 3.141592`  
컴파일할때 `PI`를 `3.141592`로 대체함  
아래처럼 응용 가능

```c
#include <stdio.h>

#define GREETING printf("holla\n");
#define SQUARE(X) ((X) * (X))
#define MAX(A, B) (((A) > (B)) ? (A) : (B))
#define FOR(I, S, E) for(int I = S; I < E; I++)
#define LOOP while (true)

int main() {
    GREETING
    printf("%d\n", 100 / SQUARE(5));
    printf("%d\n", MAX(4, 6));
    FOR(i, 0, 5) {
        printf("%d입니당\n", i);
    }
}
```

> 실행화면
```
holla
4
6
0입니당
1입니당
2입니당
3입니당
4입니당
```



## enum

```c
#include <stdio.h>

enum EGAMESTATE {
    GAMESTATE_MAINMENU = 0, // ';'을 붙이지 않고 ','로 구분
    GAMESTATE_PLAYING = 1
};

int main() {
    printf("main menu: %d\n", GAMESTATE_MAINMENU);
    printf("playing: %d\n", GAMESTATE_PLAYING);
}
```

> 실행화면
```
main menu: 0
playing: 1
```