# 객체지향 프로그래밍



- 다트는 객체 지향 프로그래밍 언어



## 클래스



- 객체: 저장 공간에 할당되어 값을 가지거나 별자에 의해 참조되는 공간
- 변수, 자료 구조, 함수 또는 메서드 등
- 인스턴스화: 객체를 메모리에 작성하는 것
- 인스턴스: 메모리에 작성된 객체
- 클래스: 인스턴스화할때의 설계도 역할
- 프로퍼티: 클래스 안에서 속성을 표현



```dart
/// 클래스
class Person {
  String name;
  int age;
  
  void addOneYear() {
    age++;
  }
}

// 인스턴스화
var person = Person();
  
var person2 = Person();

//프로퍼티 접근
print(person.name);
print(person.age);
print('${person.age}살');

// 메서드 접근
person.age = 10;
person.addOneYear();
print(person.age);
```



