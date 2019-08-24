# override와 정적 바인딩

## override: 우선하다.

```c++
#include <iostream>

using namespace std;

class Foo {
public:
    int i = 10;
};

class Boo: public Foo {
public:
    int i = 20;
};

int main() {
    Boo b;

    cout << b.i << endl;
    cout << b.Foo::i << endl;
    cout << b.Boo::i << endl;
}
```

> 실행화면
```
20
10
20
```