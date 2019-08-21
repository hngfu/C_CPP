# 배열과 포인터

## 배열

```c
int arr[4]; // 4byte(int의 크기) * 4 만큼 공간이 생김

int arr2[] = {1, 2, 3, 4, 5};   // 4byte * 5(5개를 넣었으니까) 만큼 공간이 생김  
```

## 포인터

```c
#include <stdio.h>

int main() {
    int n = 1;
    int* foo;
    int *doo;
    int * goo;

    doo = &n;
    foo = &n;
    goo = &n;

    printf("%ld\n", *doo);
    printf("%ld\n", *foo);
    printf("%ld\n", *goo);
}
```

> 실행화면
```
1
1
1
```

## 관계

```c
#include <stdio.h>

int main() {
    int foo[] = {1, 2, 3, 4, 5, 6};
    printf("%ld\n", &foo[0]);
    printf("%ld", foo);
}
```

> 실행화면
```
140732891761216
140732891761216
```

같다.  
결국, `foo == &foo[0]`.  
foo는 foo의 0번째 인덱스의 주소를 나타냄.  

```c
#include <stdio.h>

int main() {
    int foo[] = {1, 2, 3, 4, 5, 6};

    for (int i = 0; i < 6; i++) {
        printf("%ld %ld\n", &foo[i], foo+i);
    }
}
```

> 실행화면
```
140732704025152 140732704025152
140732704025156 140732704025156
140732704025160 140732704025160
140732704025164 140732704025164
140732704025168 140732704025168
140732704025172 140732704025172
```

같다.  
`&foo[0] == foo`  
`&foo[i] == foo+i`  
`*(&foo[i]) == foo[i] == *(foo+i)`

```c
#include <stdio.h>

int main() {
    int n = 1;
    int *ptr_n = &n;

    printf("%ld\n", ptr_n);
    printf("%ld", ptr_n+1);
}
```

> 실행화면
```
140732920425052
140732920425056
```

4만큼 증가했다.

```c
#include <stdio.h>

int main() {
    double n = 1;
    double *ptr_n = &n;

    printf("%ld\n", ptr_n);
    printf("%ld", ptr_n+1);
}
```

> 실행화면
```
140732669139544
140732669139552
```

8만큼 증가했다.

해당 자료형의 크기만큼 움직인다는걸 알 수 있다.

```c
#include <stdio.h>

int main() {
    int arr[] = {1, 2, 3, 4, 5, 6};
    int *ptr_arr = &arr;

    printf("arr의 주소: %ld\n", &arr);
    printf("arr의 주소 + 1: %ld\n", &arr+1);

    printf("ptr_arr의 주소 + 1: %ld\n", &ptr_arr);
    printf("ptr_arr의 주소 + 1: %ld", &ptr_arr+1);
}
```

> 실행화면
```
arr의 주소: 140732790762048
arr의 주소 + 1: 140732790762072
ptr_arr의 주소 + 1: 140732790762040
ptr_arr의 주소 + 1: 140732790762048
```

arr의 크기는 int 개수가 6개인 배열이기 때문에 4(sizeof(int)) * 6개해서 24가 증가되었다.  
하지만 ptr_arr의 크기는 8이기 때문에(포인터 변수이니까) 8이 증가되었다.

```c
#include <stdio.h>

int main() {
    int arr[4];
    int *ptr_arr = arr;

    for (int i = 0; i < 4; i++) {
        printf("%ld %ld\n", &arr[i], &ptr_arr[i]);
    }
}
```

> 실행화면
```
140732768811584 140732768811584
140732768811588 140732768811588
140732768811592 140732768811592
140732768811596 140732768811596
```

## 배열포인터

```c
int arr[] = {1, 2, 3, 4, 5, 6};

// 배열 포인터
int (*ptr_arr)[3] = arr;
// or
int(*ptr_arr)[3] = arr;
```

```c
#include <stdio.h>

int main() {
    int arr[] = {1, 2, 3, 4, 5, 6};
    int (*ptr_arr)[3] = arr;
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 3; j++) {
            printf("%d\n", ptr_arr[i][j]);
        }
    }
}
```

>  실행화면
```
1
2
3
4
5
6
```

```c
#include <stdio.h>

int main() {
    int arr[2][3] = {{1, 2, 3,}, {4, 5, 6,}};

    for (int(*row)[3] = arr; row < arr + 2; row++) {
        for (int(*col) = *row; col < *row + 3; col++) {
            printf("%d ", *col);
        }
        printf("\n");
    }
}
```

> 실행화면
```
1 2 3 
4 5 6 
```

```c
int(*row)[3] // 4byte * 3의 배열을 가리키는 배열 포인터

int(*col);
// ==
int *col;
```

## 포인터 배열

```c
#include <stdio.h>

int main() {
    int arr[] = {1, 2, 3, 4, 5, 6};

    int *ptr_arr[6];

    for (int i = 0; i < 6; i++) {
        ptr_arr[i] = &arr[i];
    }

    for (int i = 0; i < 6; i++) {
        printf("%d\n", *ptr_arr[i]);
    }
}
```

> 실행화면
```
1
2
3
4
5
6
```

## 정리

```c
int *ptr;           // 포인터
int *ptr_arr[6];    // 포인터 배열
int(*arr_ptr)[6];   // 배열 포인터
```

```c
#include <stdio.h>

int main() {
    int *ptr;
    int *ptr_arr[6];
    int(*arr_ptr)[6];

    printf("포인터: %d, 포인터 배열: %d, 배열 포인터: %d", sizeof(ptr), sizeof(ptr_arr), sizeof(arr_ptr));
}
```

> 실행화면
```
포인터: 8, 포인터 배열: 48, 배열 포인터: 8  // 크기(단위는 byte)
```

포인터는 64bit에서 8byte, 포인터 배열은 포인터 크기인 8byte * 6(개수) 해서 48.

```c
#include <stdio.h>

int main() {
    int arr[] = {2, 4, 6, 8, 10, 12};
    int (*ptr_arr)[3] = arr;
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 3; j++) {
            printf("%ld ", ptr_arr[i][j]);
            printf("%ld\n", *(*(ptr_arr + i) + j));
        }
    }
}
```

> 실행화면
```
2 2
4 4
6 6
8 8
10 10
12 12
```

`ptr_arr[i][j] == *(*(ptr_arr + i) + j)`  
`ptr_arr[i] == *(ptr_arr + i)`  
`ptr_arr[0] == *(ptr_arr) == *ptr_arr`
