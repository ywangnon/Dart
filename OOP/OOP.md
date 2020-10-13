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



## 접근 지정자



- 변수명 앞에 _ 기호를 붙이지 않으면 외부에서 접근 가능하고, 붙이면 접근 불가능
- 프라이빗 변수: 다른 파일에서 직접 접근 불가, 정의되어 있는 파일내에서만 접근 가능



```dart
// person.dart
class Person {
  String name;
  int _age; // 프라이빗 변수
  
  void addOneYear() {
    _age++;
  }
}

// main.dart
import 'person.dart';

var person = Person();
person._age = 10; // 에러. 접근 불가
```



## 생성자



- 인스턴스화하는 방법을 제공하는 메서드



```dart
class Person {
  String name;
  int _age;
}

var person = Person();
```



- 사용자 정의 생성자를 추가하면 기본생성자 사용 불가
- 선택 매개변수를 사용하면 기본 생성자도 사용 가능. 실제로는 기본 생성자를 호출하는 것이 아니라, 모든 매개변수에 null을 대입한 생성자 호출



```dart
class Person {
  String name;
  int _age;
  
  Person({this.name, this._age}); // 생성자
}

var person = Person();
var person2 = Person(name: '홍길동', _age: 20);
```



## 게터, 세터



- 프라이빗 변수에 접근하려면 게터, 세터 메서드가 필요



```dart
// person.dart
class Person {
  String name;
  int _age;
  
  int get age => _age;
}

// main.dart
import 'person.dart';

var person = Person();
print(person.age); // _age값 출력
```



- 프로퍼티끼리 직접 계산하는 방식보다 세터와 게터를 이용해 계산하는 방식이 실수를 줄일 수 있다.



```dart
class Rectangle {
  num left, top, width, height;
  
  Rectangle(this.left, this.top, this.width, this.height);
  
  num get right => left + width;
  set right(num value) => left = value - width;
  num get bottom => top + height;
  set bottom(num value) => top = value - height;
}
```



