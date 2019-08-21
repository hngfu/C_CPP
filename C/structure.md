# 구조체

## typedef

```c
#include <stdio.h>

int main() {
    typedef unsigned int Uint;
    typedef int Coordinate[2];
    typedef char *String;

    Uint num = 4;
    Coordinate xy = {6, 4};
    String str = "흥푸임돠";

    printf("num: %d\n", num);
    printf("x: %d, y: %d\n", xy[0], xy[1]);
    printf("%s\n", str);
}
```

> 실행화면
```
num: 4
x: 6, y: 4
흥푸임돠
```

## 구조체 사용법 1

```c
#include <stdio.h>

int main() {
    struct {int x, y;} coordinate;
    coordinate.x = 4;
    coordinate.y = 6;
    printf("x: %d, y: %d", coordinate.x, coordinate.y);
}
```

> 실행화면
```
x: 4, y: 6
```

## 구조체 사용법 2

```c
#include <stdio.h>

int main() {
    typedef struct {
        int x, y;
    } Coordinate;
    Coordinate coordinate = { 4, 6 };
    printf("x: %d, y: %d", coordinate.x, coordinate.y);
}
```

> 실행화면
```
x: 4, y: 6
```

## 구조체 사용법 3

```c
#include <stdio.h>

int main() {
    struct Coordinate {
        int x, y;
    };
    struct Coordinate coordinate = { 4, 6 };
    printf("x: %d, y: %d", coordinate.x, coordinate.y);
}
```

> 실행화면
```
x: 4, y: 6
```