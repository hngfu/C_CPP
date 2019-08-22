# 상수화

```c++
#include <iostream>

using namespace std;

class Human {
public:
    Human(string name): name(name) {}
                // ↓ 매개변수의 상수화  // ↓ 메서드의 상수화
    void Greeting(const string name) const {
        cout << name << "씨 안녕하세요. 저는 야망있는 " << this->name << "입니다. 반가워요 ^^" << endl;
    }
private:
    string name;
};

int main() {
    Human hngfu("hngfu");
    hngfu.Greeting("JaeHeung");
}
```

> 실행화면
```
JaeHeung씨 안녕하세요. 저는 야망있는 hngfu입니다. 반가워요 ^^
```
