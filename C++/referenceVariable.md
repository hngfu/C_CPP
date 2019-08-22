# 참조 변수

```c++
#include <iostream>

using namespace std;

int main() {
    int a = 4;
    int &b = a;
    b = 6;

    cout << "a: " << a << endl;
    cout << "b: " << b << endl;
}
```

> 실행화면
```
a: 6
b: 6
```

원래 기존에는 아래↓와 같이 포인터를 이용해야했는데 정말 awesome하다. 🤩

```c++
#include <iostream>

using namespace std;

int main() {
    int a = 4;
    int *b = &a;
    *b = 6;

    cout << "a: " << a << endl;
    cout << "b: " << *b << endl;
}
```

> 실행화면
```
a: 6
b: 6
```

## 범위 기반 for문으로 2차원 배열 출력하는 방법

```c++
#include <iostream>

using namespace std;

int main() {
    int arr[2][3] = {{1, 2, 3}, {4, 5, 6}};
    for (int (&i)[3]: arr) {    // int 3개짜리 배열을 가르키는 참조 변수 i
        for (int j: i) {
            cout << j << endl;
        }
    }
}
```

`배열 포인터` 만드는 것처럼 만들어서 사용하면 됨.

> 실행화면
```
1
2
3
4
5
6
```