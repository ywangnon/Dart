# 함수 형태



- 입력 받는 문자: 매개변수, 파라미터(parameter)
- 반환되는 값: 반환값
- 실제 입력 받는 값: 인수, 아규먼트(argument)



```dart
int f(int x) {
  return x + 10;
}

void main() {
  var result = f(10);
}

int f(int x, int z) {
  return x + z + 10;
}

String f() {
  return '안녕하세요';
}

void f(int x) {
  print(x);
}
```



- 반환 타입도 타입 추론으로 생략 가능



```dart
void greeting(String greet) {
  print('hello $greet');
}

// 위 코드와 동일함
greeting(String greet) {
  print('hello $greet');
}
```



- print() 함수는 반환값이 void인 대표적인 함수
- 변수 앞에 $ 기호를 붙여 문자열 내에 변수를 삽입 가능
- $ 기호 뒤에 {} 로 둘러싸 수식을 포함한 각종 표현식을 사용 가능



```dart
String _name = '홍길동';
int _age = 20;

void main() {
  print('$_name은 $_age살입니다.');
  print('$_name은 ${_name.length}글자입니다.');
  print('10년 후에는 ${_age + 10}살입니다.');
}
```



