# 상수 final, const

-final 키워드를 제일 앞에 붙이면 값이 수정되지 않는 상수로 사용

```Dart
  final String name = '홍길동';
  name = '임꺽정'; // 에러
```

- 타입 생략하고 작성

```Dart
  final name = '홍길동';
```

차이를 찾아봤는데

|const|final|
| :-: | :-: |
|런타임시에 정해진 값을 바꿀 수 없음|final은 런타임 이후라도 한번 정해진 값을 바꿀 수 없음|
|const는 const 타입 값만 줄 수 있음|모든 타입 값 가능|

참고 링크:[Dart2 훑어보기](https://brunch.co.kr/@genkino/118)
