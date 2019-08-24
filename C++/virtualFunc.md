# 가상 함수와 동적 바인딩

```c++
#include <iostream>

using namespace std;

class Weapon {
public:
    virtual void Attack() { // here!
        cout << "Weapon으로 attack." << endl;
    }
};

class Bow: public Weapon {
public:
    void Attack() {
        cout << "휙 화쌀~ 휙 화쌀~ 휙 휙~~" << endl;
    }
};

class Magic: public Weapon {
public:
    void Attack() {
        cout << "윙가르디움 레비오우사" << endl;
    }
};

int main() {
    Weapon *weapon;
    Bow bow;
    Magic magic;

    weapon = &bow;
    weapon->Attack();
    weapon = &magic;
    weapon->Attack();

}
```

> 실행화면
```
휙 화쌀~ 휙 화쌀~ 휙 휙~~
윙가르디움 레비오우사
```
