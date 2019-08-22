# 입출력

```c++
#include <iostream>

using namespace std;

int main() {
    string name;
    cin >> name;                  // 입력
    cout << name << "입니다~!@#";   // 출력
}
```

> 실행화면
```
Hngfu
Hngfu입니다~!@#
```

## 다른 경우

```c++
#include <iostream>

//using namespace std;

int main() {
    std::string name;
    std::cin >> name;
    std::cout << name << "입니다~!@#";
}
```

> 실행화면
```
Hngfu
Hngfu입니다~!@#
```