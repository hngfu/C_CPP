# 연산자 오버로딩

```c++
#include <iostream>

using namespace std;

class Point {
public:
    Point();
    Point(int x, int y);

    Point operator+(const Point rhs) const;

    void ShowPoint();
    int GetX() { return x; }
    int GetY() { return y; }
private:
    int x, y;
};

// here!
Point operator*(Point lhs, int rhs) {
    return Point(lhs.GetX() * rhs, lhs.GetY() * rhs);
}

int main() {
    Point a(1, 1);
    Point b(3, 3);

    Point c = a + b;
    c.ShowPoint();
    Point d = c * 2;
    d.ShowPoint();
}

Point::Point(): x(0), y(0) {}
Point::Point(int x, int y): x(x), y(y) {}

void Point::ShowPoint() {
        cout << "x: " << x << ", y: " << y << endl;
}

// here!
Point Point::operator+(const Point rhs) const {
    return Point(x+rhs.x, y+rhs.y);
}
```

> 실행화면
```
x: 4, y: 4
x: 8, y: 8
```