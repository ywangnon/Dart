# 산술 연산자

```
- : 더하기
- - : 빼기
- * : 곱하기
- / : 나누기(double 타입 반환)
- ~/ : 몫(int 타입 반환)
- % : 나머지(int 타입 반환)
```

**assert()** 함수는 계산 결과가 참인지 검사

```swift
  assert(2 + 3 == 5);
  assert(5 - 2 == 3);
  assert(3 * 5 == 15);
  assert(5 / 2 == 2.5);
  assert(5 ~/ 2 == 2);
  assert(5 % 2 == 1);
```

모두 참이다

두 개의 문자열을 결합하는데도 쓰인다.
```swift
  assert('hello' + ' world' == 'hello world');
```
