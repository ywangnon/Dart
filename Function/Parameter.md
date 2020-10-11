# 선택 매개변수

- {} 로 감싼 매개변수는 선택적으로 사용 가능
- 매개변수명을 값 앞에 써서 호출
- 이름 있는 매개변수(Named Parameter) 라고도 부름

```dart
void something({String name, int age}) {}

void main() {
  something(name: '홍길동', age: 10);
  something(name: '홍길동');
  something(age: 10);
  something();
}
```



- 필수 매개변수와 선택 매개변수를 함께 사용하고 싶다면 앞쪽에 필수 매개변수를 먼저 둠



```dart
void something(String, {int age}) {}

void main() {
  something(name: '홍길동', age: 10);
  something(name: '홍길동');						
  something(age: 10); 								// 에러
  something();												// 에러
}
```



- 선택 매개변수는 기본값 지정 가능



```dart
void something(String, {int age = 10}) {}

void main() {
  something(name: '홍길동', age: 10);
  something(name: '홍길동');
}
```

