# 형변환

```c++
#include <iostream>

using namespace std;

class Human {
public:
    Human(int age): age(age) {      // 변환 생성자
        name = "NoNameD";
        cout << "i was born!" << endl;
    }

    // int로의 형변환 연산자 오버로딩
    operator int() {
        cout << "int()" << endl;
        return age;
    }
private:
    int age;
    string name;
};

void printInt(int num) {
    cout << num << endl;
}

int main() {
    Human a = Human(1);
    Human b(2);
    Human c = 3;
    c = 4;                  // 묵시적 변환
    Human d = (Human)5;     // 명시적 변환

    printInt(a);            // 묵시적 형변환
    printInt((int)b);       // 명시적 형변환
}
```

> 실행화면
```
i was born!
i was born!
i was born!
i was born!
i was born!
int()
1
int()
2
```