# 상속

```c++
#include <iostream>

using namespace std;

class God {
public:
    void Greeting() {
        cout << "#@!~<>Hi<>~!@#" << endl;
    }
};

class Hngfu: public God {

};

int main() {
    Hngfu *hngfu = new Hngfu();
    hngfu->Greeting();
    delete hngfu;
}
```

> 실행화면
```
#@!~<>Hi<>~!@#
```