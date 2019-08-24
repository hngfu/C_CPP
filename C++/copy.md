# 복사 

```c++
#include <iostream>

using namespace std;

int main() {
    int *a = new int(4);
    int *b = new int(6);

    a = b;      // 얕은 복사 (참조만 복사)
    *a = *b;    // 깊은 복사 (값을 복사)

    delete a;
    delete b;
}
```