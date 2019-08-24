# 동적 할당과 객체 복사

```c++
#include <iostream>

using namespace std;

class Point {
public:
    Point(): x(0), y(0) {}
    Point(int x, int y): x(x), y(y) {}

    int x, y;
};

class Polygon {
public:
    Polygon() {
        nPoints = 0;
        points = NULL;
    }
    Polygon(const int nPoints, const Point *points) : nPoints(nPoints) {
        this->points = new Point[nPoints];
        for (int i = 0; i < nPoints; i++)
            this->points[i] = points[i];
    }

    // 복사 생성자 구현
    Polygon(const Polygon &p) {
        nPoints = p.nPoints;
        points = new Point[nPoints];
        for (int i = 0; i < nPoints; i++) {
            points[i] = p.points[i];
        }
        cout << "깊은 복사" << endl;
    }

    // 이동 생성자 구현
    Polygon(Polygon &&p) {
        nPoints = p.nPoints;
        points = p.points;
        p.points = NULL;
        cout << "얕은 복사" << endl;
    }

    ~Polygon() {
        delete[] points;

    }

    // 복사 대입 연산자 구현
    //     ↓ 반환값을 참조로 주는게 포인트
    Polygon& operator=(const Polygon &rhs) {
        if (this != &rhs) {
            nPoints = rhs.nPoints;
            delete[] points;
            points = new Point[nPoints];
            for (int i = 0; i < nPoints; i++) {
                points[i] = rhs.points[i];
            }
        }
        cout << "깊은 복사" << endl;
        return *this;
    }

    // 이동 대입 연산자 구현
    //     ↓ 반환값을 참조로 주는게 포인트
    Polygon& operator=(Polygon &&rhs) {
        if (this != &rhs) {
            nPoints = rhs.nPoints;
            delete[] points;
            points = rhs.points;
            rhs.points = NULL;
        }
        cout << "얕은 복사" << endl;
        return *this;
    }

    int GetNPoints() const {
        return nPoints;
    }

    Point *GetPoints() const {
        if (nPoints == 0) return NULL;
        return points;
    }

private:
    int nPoints;
    Point *points;
};

Polygon getSqare() {
    Point points[4] = { {0, 0}, {1, 0}, {1, 1}, {0, 1} };
    Polygon p(4, points);
    return p;
}

int main() {
    Polygon a;
    a = getSqare(); // 얕은 객체 복사 2회
    Polygon b = a; // 깊은 객체 복사 1회
    Polygon c;
    c = a; // 깊은 객체 복사 1회

    int nPoints = c.GetNPoints();
    Point *points = c.GetPoints();
    for (int i = 0; i < nPoints; i++) {
        cout << "(" << points[i].x << "," << points[i].y << ")" << endl;
    }
}
```

> 실행화면
```
얕은 복사
깊은 복사
깊은 복사
(0,0)
(1,0)
(1,1)
(0,1)
```
