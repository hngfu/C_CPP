# 범위 기반 for 문

```c++
#include <iostream>

using namespace std;

int main() {
    int arr[] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
    for (int i: arr) {
        cout << i << endl;
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
7
8
9
10
```