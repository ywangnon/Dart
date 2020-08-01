# 기본 문법



## 주석



```dart
// 이것은 주석. 한 줄 주석

/**
*	이것도 주석. 여러 줄 주석
**/

/// 이것도 주석. 문서 주석
```

- /// 를 메서드나 클래스 정의 위에 작성하면 dartdoc과 같은 문서 생성 ㄷ구를 통해 문서를 자동으로 생성
- dart.dev/tools/dartdoc



## 문장



```dart
void main() {
  //여기에 작성
  print("Hello world!") // 에러! 끝에 세미콜론 표시
    print("Hi");
}
```



## 변수



### 기본 타입

- int : 정수
- double : 실수(소수점)
- String : 문자열
- bool : 불리언



```swift
String name; // 변수 선언
name = '홍길동'; // 값 할당
name = "홍길동"; // 작은 따옴표, 큰 따옴표 모두 사용 가능

// bool 타입
bool b = true;
bool b2 = i < 10;
bool b3 = s.isEmpty;

// int와 double 타입
int i = 10;
double d = 10.0;

// int와 double은 num 타입에 포함
num a = 10;
num b = 20.0;

// 자동 형변환  지원 안함
int a = 10;
double b = a; // 에러

// num 타입에 int와 double 타입 모두 대입 가능
int a = 10;
double b = 20.0;

num c = a;	// ok
c = b; 			// ok

// 변수에 언제나 값을 재할당 가능
String s = 'hello';
s = 'world';
```

