# C 와 C++
흥푸의 기초다지기 시리즈 1

## C

### 목차

[변수](/C/variable.md)  
[자료형](/C/dataType.md)  
[입출력](/C/inOut.md)  
[연산자](/C/operator.md)  
[배열과 포인터](/C/array&pointer.md)  
[함수](/C/function.md)  
[구조체](/C/structure.md)  
[구조체 포인터](/C/structurePointer.md)  
[상수](/C/constant.md)  
[비트 연산자](/C/bitOperator.md)  
[파일 입출력](/C/fileInOut.md)  
[몇몇 유용한 함수들](/C/usefulFunctions.md)

## C++

### 목차

[입출력](/C++/inOut.md)  
[변수 선언](/C++/declaration.md)  
[범위 기반 for 문](/C++/for.md)  
[참조 변수](/C++/referenceVariable.md)  
[접근 제어](/C++/accessControl.md)  
[클래스와 구조체 차이](/C++/classStruct.md)  
[this 포인터](/C++/this.md)  
[생성자, 소멸자](/C++/constructorDestructor.md)  
[생성자 응용](/C++/constructorApplication.md)  
[정적 멤버](/C++/staticMember.md)  
[상수화](/C++/toConstant.md)  
[메서드 선언, 정의 분리](/C++/methodSeparation.md)  
[연산자 오버로딩](/C++/operatorOverloading.md)  
[할당](/C++/allocate.md)  
[복사](/C++/copy.md)  
[동적 할당과 객체 복사](/C++/allocateAndCopy.md)  
[형변환](/C++/typeCasting.md)  
[상속](/C++/inheritance.md)  
[오버라이드](/C++/override.md)  
[가상 함수](/C++/virtualFunc.md)  



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
