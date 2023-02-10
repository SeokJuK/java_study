# 자바 API

- 자바에서 기본적으로 제공하는 라이브러리
- 프로그램 개발에서 자주 사용되는 클래스 및 인터페이스의 모음


# API Document

- 쉽게 API를 찾아 이용할 수 있도록 문서화한 것
- HTML 페이지로 작성되어 있어 웹브라우저로 바로 볼 수 있다


# java.lang
  - 자바 프로그램의 기본적인 클래스를 담고 있는 패키지
-  포함된 클래스와 인터페이스는 import없이 사용할 수 있다.

# java.lang의 주요 클래스

 1. Object   
> - 자바 클래스의 최상위 클래스로 사용

2. System
> - 표준 입력장치(키보드)로부터 데이터를 입력 받을 때
> - 표준 출력장치(모니터)로 출력하기 위해
> - 자바 가상 머신(JVM)을 종료시킬 때
> - Garbage Collector를 실행 요청할 때 사용


3. Class
> - 클래스를 메모리로 로딩할 때 사용


4. String
> - 문자열을 저장하고 여러가지 정보를 얻을 때


5. StringBuffer, StringBuilder
> - 문자열을 저장하고 내부 문자열을 조작할 때 사용


6. Math
> - 수학 함수를 이용할 때 사용


7. Wrapper(Byte, Short, Character, Integer, Boolean...)
> - 기본 타입의 데이터를 갖는 객체를 만들 때 사용
> - 문자열을 기본 타입으로 변환할 때 사용
> - 입력값 검사에 사용

# Object 클래스
- 자바의 최상위 부모 클래스
> 1. 다른 클래스를 상속하지 않으면 암시적으로 java.lang.Object클래스를 상속
> 2. Object의 메소드는 모든 클래스에서 사용할 수 있다.

# 객체 비교(equals())
- 기본적으로 == 연산자와 동일한 결과를 리턴(번지 비교)
> ```java
> Object obj1 = new Object();
> Object obj2 = new Object();
> boolean result = obj1.equals(obj2); //기준 객체.equals(비교객체);
> ```
- 논리적 동등을 위해 오버라이딩 필요
> - 논리적 동등 = 같은 객체이건 다른객체이건 상관없이 객체가 저장하고 있는 데이터가 동일
> - Object의 equals()메소드는 직접 사용되기 보다는 재정의하여 논리적 동등 비교할 때 이용
>  ex) String 클래스는 equals()를 재정의하여 String 객체간의 문자열을 비교한다. -> 객체의 주소가 아닌 데이터 값을 비교

# 객체 해시코드(hashCode())
- 객체를 식별할 하나의 정수값
- Object의 hashCode() 메소드는 객체의 메모리 번지를 이용해서 해시코드를 만들어서 리턴한다
- 컬렉션 프레임워크의 HashSet, HashMap, Hashtable과 같은 클래스는 두 객체가 동등한 객체인지 판단할 때 hashCode()의 오버라이딩이 필요하다
- 어떠한 객체를 동등하게 만들려면 hashCode(), equals()를 Overriding을 해줘야 한다

# 객체 문자정보(toString())
- 객체의 문자 정보란 객체를 문자열로 표현한 값을 말한다
- Object클래스의toString() 메소드는 객체의 문자 정보를 리턴한다
- 클래스명@해시코드로 구성된 문자 정보를 리턴
```java
Object obj = new Object();
System.out.println(obj.toString());
//결과값
//java.lang.Object@de6ced
```
- 일반적으로는 재정의해서 의미있는 문자정보가 나오도록 한다
- Date 클래스는 toString()메소드를 재정의하여 현재 시스템의 날짜와 시간 정보를 리턴
- String클래스는 toString()메소드를 재정의하여 저장하고 있는 문자열을 리턴
- System.out.println(Object) 메소드는 Object의 toString()의 리턴값을 출력한다
