# Function N Method

- 함수 : 최상위 함수(가장 바깥쪽에 작성하는 함수)
- 메서드 : 클래스 내부 함수
- static : 클래스 내부 함수라도 static이 붙으면 정적 메서드가 되며, 함수로 볼 수 있다. static 키워드가 붙은 함수는 최상위 함수처럼 사용 가능

```swift
bool isEven(int number) {
  return number % 2 == 0;
}

void main() {
  print(isEven(10));
}


class MyClass {
  // 메서드
  bool isEven(int number) {
    return number %2 == 0;
  }
}

var myClass = MyClass();
print(myClass.isEven(10));

class MyClass {
  static bool isEven(int number) {
    return number % 2 == 0;
  }
}

print(MyClass.isEven(10));

void main() {
  Person person = Person("ojs", age: 39);
  person.greeting();
}

class Person {
  String name;
  int age;
  Person(this.name, {this.age});

  void greeting() {
    print('안녕하세요 저는 $name입니다.');
  }
}

```
