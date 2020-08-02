# 타입 추론

- 타입을 직접 명시하지 않고 **var**로 대체할 수 있는 타입 추론 지원

```Dart
void main() {
  var i = 10;         // int 타입
  var d = 10.0;       // double 타입
  var s = 'hello';    // 문자열 타입
  var s2 = "hello";   // 문자열 타입
  var b = true;       // 불리언 타입
  var b2 = i < 10;    // 불리언 타입
  var b3 = s.isEmpty; // 불리언 타입
}
```
