# 생성자 응용

```c++
#include <iostream>

using namespace std;

class Time {
public:
    Time(): h(0), m(0), s(0) {}
    Time(int s_): Time() {
        s = s_;
    }
    Time(int m_, int s_): Time(s_) {
        m = m_;
    }
    Time(int h_, int m_, int s_): Time(m_, s_) {
        h = h_;
    }

    void ShowTime() {
        cout << h << "시" << m << "분" << s << "초" << endl;
    }

private:
    int h;
    int m;
    int s;
};

int main() {
    Time t(1, 2, 3);
    t.ShowTime();
}
```

> 실행화면
```
1시2분3초
```