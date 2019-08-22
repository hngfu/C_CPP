# 생성자, 소멸자

```c++
#include <iostream>

using namespace std;

class Human {
public:
    Human() {   // 생성자
        cout << "i was born." << endl;
    }

    ~Human() {  // 소멸자
        cout << "R.I.P" << endl;
    }
};

int main() {
    Human him;
}
```

> 실행화면
```
i was born.
R.I.P
```

## 이런것도 가능

```c++
#include <iostream>

using namespace std;

class Point {
public:
//    Point() {
//        x = 0;
//        y = 0;
//    }

    Point(int x, int y) {
        this->x = x;
        this->y = y;
    }
private:
    int x, y;
};

int main() {
//    Point p1;
    Point p2 = Point(4, 6);
    Point p3(4, 6);
    Point p4 = {4, 6};
    Point p5 = Point{4, 6};
    Point p6{4, 6};
}
```