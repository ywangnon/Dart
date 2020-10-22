# 함수형 프로그래밍



- 자료처리를 수학적 함수의 계산으로 취급하는 프로그래밍 패러다임
- 상태와 가변 데이터 기피



## 일급 객체



- 함수를 값으로 취급.(변수에 다른 함수 대입 가능)



```dart
void greeting(String text) {
  print(text);
}

void main() {
  var f = greeting;
  f('hello');
}

void something(Function(int i) f) {
  f(10);
}

void myPrintFunction(int i) {
  print('내가 만든 함수에서 출력한 $i');
}

void main() {
  something((value) { // 익명 함수
    print(value);
  });
  
  something(myPrintFunction);						// 내가 만든 함수에서 출력한 10
  something((i) -> myPrintFunction(i));	// 내가 만든 함수에서 출력한 10
  something((i) => print(i));	//	10
  something(print);						//	10
}
```



## for 문과 forEach() 함수



```dart
final items = [1,2,3,4,5];

for (var i = 0;i < items.length;i++) {
  print(items[i]);
}

items.forEach(print);

items.forEach((e) {
  print(e);
});

items.forEach((e) => print(e));
```



- forEach() 함수는 (E element) {} 형태의 함수를 인수로 받음



## where



- 조건 필터링시 사용하는 함수



```dart
// 짝수
items.where((e) => e % 2 == 0).forEach(print);
```



## map



- 반복되는 값을 다른 형태로 변환하는 방법을 제공하는 함수



```dart
// 짝수 '숫자 i' 형태로
items.where((e) => e % 2 == 0).map((e) => '숫자 $e').forEach(print);
```





## toList



- 결과를 리스트 형태로 변환



```dart
final result = items.where((e) => e % 2 == 0).toList();
```



## toSet



- 리스트에서 중복이 제거된 리스트를 얻고 싶을 때 사용



```dart
final items = [1,2,2,3,3,4,5];

final result = items.where((e) => e % 2 == 0).toSet().toList();
```



## any



- 리스트에서 특정 조건을 충족하는 요소가 있는지 없는지 검사할 때 사용     



```dart
final items = [1,2,2,3,3,4,5];

print(items.any((e) => e % 2 == 0)); // true
```





## reduce



- 반복 요소를 줄여가면서 결과를 만들 때 사용하는 함수
- 연산 결과를 다음 요소와 연산



```dart
final items = [1,2,3,4,5];
print(items.reduce((e,v) => max(e, v))); // 5

final result = itmes.reduce(max);	// 5
```





