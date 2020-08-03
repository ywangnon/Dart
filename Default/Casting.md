# 형변환

- as 키워드 사용. 상위 개념으로 변환 가능

- int, double 은 num을 구현하는 타입이지만, 서로 관계가 없기 때문에 형변환 불가능

```Dart
  var c = 30.5;
  int d = c as int; // 에러
```

- int, double 모두 상위 개념인 num으로 형변환 가능

```Dart
  dynamic d = 30.5;
  num n = d; // as num; 생략 가능
```


