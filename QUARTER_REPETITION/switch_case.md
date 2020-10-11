# switch case



- 조건에 맞는 값이 여러 개일때
- 열거 타입과 함께 사용시 모든 케이스를 검사 강제



```dart
enum Status { Uninitialized, Authenticated, Authenticating, Unauthenticated }

void main() {
  var status = Status.Authenticated;
  switch (status) {
    case Status.Authenticated:
      print('인증됨');
      break;
      
    case Status.Authenticating:
      print('인증 처리 중');
      break;
      
    case Status.Unauthenticated:
      print('미인증');
      break;
      
    case Status.Uninitialized:
      print('초기화됨');
      break;
  }
}
```



