# 정적 멤버

## static method

```c++
#include <iostream>

using namespace std;

class Point {
public:
    Point(): x(0), y(0) {}
    Point(int x, int y): x(x), y(y) {}

    static Point Center(Point lhs, Point rhs) {     // here!
        return Point((lhs.x + rhs.x) / 2, (lhs.y + rhs.y) / 2);
    }

    void ShowPoint() {
        cout << "x: " << x << ", y: " << y << endl;
    }
private:
    int x, y;
};

int main() {
    Point a(1, 1);
    Point b(3, 3);
    Point c = Point::Center(a, b);
    c.ShowPoint();
}
```

> 실행화면
```
x: 2, y: 2
```

`static` 붙여서 사용하면 됨.

private property에 직접적으로 접근할 수 있다는 매우 큰 장점이 있음.

## static property

```c++
#include <iostream>

using namespace std;

class Point {
public:
    Point(): x(0), y(0), id(idCounter++) {}
    Point(int x, int y): x(x), y(y), id(idCounter++) {}

    void ShowPoint() {
        cout << "id: " << id << endl;
    }

    static int idCounter;       // here!

private:
    int x, y;
    int id;
};

int Point::idCounter = 1;       // here!

int main() {
    Point a;
    Point b(1, 1);
    Point c(4, 4);

    a.ShowPoint();
    b.ShowPoint();
    c.ShowPoint();
}
```

> 실행화면
```
id: 1
id: 2
id: 3
```