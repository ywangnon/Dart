# 함수와 메서드



- 최상위 함수: 클래스 밖에서 작성하는 함수, 어디에서나 호출할 수 있는 함수



```dart
// 최상위 함수
bool isEven(int number) {
  return number % 2 == 0;
}

void main() {
  print(isEven(10))
}
```



- 메서드: 클래스 내부에 작성하는 함수



```dart
class MyClass {
  // 메서드
  bool isEven(int number) {
    return number % 2 == 0;
  }
}

var myClass = MyClass();
print(myClass.isEven(10));
```



- 정적 메서드: static 키워드가 붙은 함수. 최상위 함수처럼 사용 가능



```dart
class MyClass {
  // 정적 메서드, 함수
  static bool isEven(int number) {
    return number % 2 == 0;
  }
}

print(MyClass.isEven(10));
```

