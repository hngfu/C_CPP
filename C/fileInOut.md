# 파일 입출력

```c
#include <stdio.h>

int main() {
    FILE *in, *out;
    int n;

    in = fopen("/Users/hngfu/Desktop/CLionHngfu/input.txt", "r");
    out = fopen("/Users/hngfu/Desktop/CLionHngfu/output.txt", "w");     // 'a'도 있음 append
    
    fscanf(in, "%d", &n);
    fprintf(out, "%d", n);

    // 사용했으면 닫아줘야함
    fclose(in);
    fclose(out);
}
```

```c
#include <stdio.h>

int main() {
    FILE *cfile = fopen("/Users/hngfu/Desktop/CLionHngfu/main.c", "r");

    char ch;
    // while (!feof(cfile)) { ... 의 방법도 있음
    while (fscanf(cfile, "%c", &ch) != EOF) {
        printf("%c", ch);
    }

    fclose(cfile);
}
```

> 실행화면
```
#include <stdio.h>

int main() {
    FILE *cfile = fopen("/Users/hngfu/Desktop/CLionHngfu/main.c", "r");

    char ch;
    // while (!feof(cfile)) { ... 의 방법도 있음
    while (fscanf(cfile, "%c", &ch) != EOF) {
        printf("%c", ch);
    }

    fclose(cfile);
}
```