# 할당

## 정적 할당

```c++
int a;
```

## 동적 할당

```c++
#include <iostream>

using namespace std;

class Point {
public:
    Point(int x, int y): x(x), y(y) {}
    ~Point() {
        cout << "R.I.P" << endl;
    }
private:
    int x, y;
};

int main() {
    // int의 경우
    int *a = new int;
    delete a;

    // int array의 경우
    int len;
    cin >> len;
    int *arr = new int[len];
    for (int i = 0; i < len; i++) {
        cout << i << endl;
    }
    delete[] arr;

    // class의 경우
    Point *p = new Point(4, 6);
    delete p;
}
```

> 실행화면
```
4
0
1
2
3
R.I.P
```