# 연산자

## 증감연산자의 전위, 후위

```c
#include <stdio.h>

int main() {
    int foo = 0;
    int hoo = 0;
    int n = 0;
    int m = 0;

    // 후위연산 할당한 '후' 더함
    foo = n++;
    printf("foo==%d, n==%d\n",foo, n);

    // 전위연산 할당하기 '전' 더함
    hoo = ++m;
    printf("hoo==%d, m==%d\n", hoo, m);
}
```

> 실행화면
```
foo==0, n==1
hoo==1, m==1
```