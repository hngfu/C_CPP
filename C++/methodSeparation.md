# 메서드 선언, 정의 분리

```c++
#include <iostream>

using namespace std;

class Point {
public:
    // 메서드 선언
    Point();
    Point(int x, int y);

    static Point Center(Point lhs, Point rhs);

    void ShowPoint();
private:
    int x, y;
};

int main() {
    Point a(1, 1);
    Point b(3, 3);
    Point c = Point::Center(a, b);
    c.ShowPoint();
}

// 메서드 정의
Point::Point(): x(0), y(0) {}
Point::Point(int x, int y): x(x), y(y) {}

void Point::ShowPoint() {
        cout << "x: " << x << ", y: " << y << endl;
}

Point Point::Center(Point lhs, Point rhs) {
    return Point((lhs.x + rhs.x) / 2, (lhs.y + rhs.y) / 2);
}
```

> 실행화면
```
x: 2, y: 2
```