# 객체지향 프로그래밍



- 다트는 객체 지향 프로그래밍 언어



[toc]



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



## 상속



- 슈퍼클래스: 상속을 주는 쪽
- 서브클래스: 받는 쪽
- 슈퍼클래스를 그대로 복사한 후 기능 추가나 변경이 첨가



```dart
class Hero {
  String name = '영웅';
 
  void run() {}
}

class SuperHero extends Hero { // Hero를 상속
  // 오버라이드 - 재정의
  @override
  void run() {
    super.run(); 	// 슈퍼클래스의 run() 실행
    this.fly();		// SuperHero의 fly() 실행
  }
  
  void fly() {}
}

void main() {
  var hero = SuperHero();
  hero.run();
  hero.fly();
  print(hero.name);	// 영웅
}
```



## 추상클래스



- 추상메서드를 포함하는 클래스
- 추상메서드: 선언만 되고 정의가 없는 메서드
- 다른 클래스에 implements하여 기능을 완성하는 상속 재료로 사용
- 클래스는 implements 키워드, 메서드에는 @override 키워드 사용
- 한 번에 여러 추상 클래스 임플리먼트 가능. 구현시에는 모든 추상 메서드 재구현 해야함



```dart
abstract class Monster {
  void attack();
}

abstract class Flyable {
  void fly();
}

class Goblin implements Monster {
  @override
  void attack() {
    print('고블린 어택');
  }
}

class Bat implements Monster, Flyable {
  @override
  void attack() {
    print('할퀴기!');
  }
  
  @override
  void fly() {
    print('펄럭펄럭');
  }
}
```



## 믹스인



- with 키워드 사용
- 상속하지 않고 다른 클래스의 기능을 가져오거나 오버라이드 가능



```dart
class Goblin implements Monster {
  @override
  void attack() {
    print('고블린 어택');
  }
}

class DarkGoblin extends Goblin with Hero {
  
}
```



! 혼란스러운 부분인데, 재구현이 없는 상속으로 보는 것이 맞나? 찾아보니 고정된 상속이라고 보는 것이 맞을지도? 믹스인에서 구현된 메소드들은 재구현이 불가능하고 그대로 사용한다. 다중으로 믹스인 가능하지만 같은 메소드명은 마지막에 선언된 것으로 사용된다. 코드의 간편한 재사용을 위한 문법인듯하다.



## 열거 타입



- 상수를 정의하는 특수 형태의 클래스
- 상수처럼 사용 가능
- switch 문 사용시 모든 상수를 case로 검토 강제.



```dart
enum Status { login, logout }

switch(authStatus) {
  case Status.login:
    print('로그인');
    break;
  case Status.logout:
    print('로그아웃');
    break;
}
```



## 컬렉션



- List: 같은 타입의 자료를 여러 개 담을 수 있고, 특정 인덱스로 접근 가능
- Map: 키와 값의 쌍으로 저장, 키를 통해 값 읽는 것이 가능
- Set: 중복을 허용하지 않고, 찾는 갓ㅂ이 있는지 없는지 판단하고자 할 때 사용



### Map

- 순서가 있는 컬렉션
- 인덱스는 0부터 시작
- 다트는 배열을 제공하지 않음



```dart
List<String> items = ['짜장', '라면', '볶음밥']; // var items = ['짜장', '라면', '볶음밥'];
  
items[0] = '떡볶이';	
print(items.length);
print(items[2]);
print(items[3]);	// 에러!

for (var i = 0;i < items.length;i++) {
  print(items[i]);
}
```



! dynamic

모든 타입을 나타내는 dynamic

```dart
List<dynamic> list = [1,2,4,'헬로']
```



### ...



- 컬렉션을 펼쳐주는 연산자



```dart
var items = ['짜장', '라면', '볶음밥'];

var items = ['떡볶이', ...items, '순대']; // 떡볶이, 짜장, 라면, 볶음밥, 순대
```



### Map



- 순서 없음
- 빠른 탐색 가능
- 키와 값의 쌍으로 구성됨
- 키에 대한 값이 없으면 null 반환



```dart
// Map<String, String> citiMap 과 같음
var cityMap = {
  '한국':'부산',
  '일본':'도쿄',
  '중국':'북경'
};

cityMap['한국'] = '서울';

print(cityMap.length);	// 3
print(cityMap['중국']);	// 북경
print(cityMap['미국']);	// null

cityMap['미국'] = '워싱턴';	// 추가
print(cityMap['미국']);	// 워싱턴
```



### Set



- add(): 추가
- remove(): 삭제
- contains(): 자료가 있는지 확인
- 중복 안됨
- 집합에 요소가 있는지 검사할 때 사용



```dart
var citySet = {'서울', '수원', '오산', '부산'};

citySet.add('안양');
citySet.remove('수원');

print(citySet.contains('서울'));	// true
print(citySet.contains('도쿄'));	// false
```



주의

```dart
var mySet = <String>{}; // Set<String>

var mySet = {}; // Map<dynamic, dynamic>
```

