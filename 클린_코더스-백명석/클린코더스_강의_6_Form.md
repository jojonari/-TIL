클린 코더스 강의 6. Form
=============================

> * 유튜브 : https://www.youtube.com/watch?v=PX5IUNdLSzg&list=PLagTY0ogyVkIl2kTr08w-4MLGYWJz7lNK&index=6
> * 강의 자료 : https://github.com/msbaek/clean-coders-2013

> Form

1. Coding Standeards
  * 코드가 Coding Standeards가 되어야 한다.
  * 코드가 잘되어 있으면 Coding Standeards가 필요없다.

2. Comments Standeards
  * 필요에 의해서 작성된 Comments만 유의미 하다.
  * 정작 필요한 Comments를 안보게 될수 있다.
  * Comments는 특별한 경우에만 작성해야한다.
  * programmer's intent를 위해 반드시 필요할때

3. Comments are Failures
  * 작성자의 의도가 잘 나타나게 프로그램을 작성한다면 커멘트 불필요
  * Assembly의 경우는 불가능
    - 커멘트가 필수
  * 루비, 자바, C# 등은 표현력이 뛰어남
  * 모든 커멘트는 당신의 코드가 Expressive하지 못하는 것을 나타내는 실패의 상징

4. Good Comments
  * legal Comments
  * informative Comments
    - 정규식 설명 등
  * Waming of Consequences
  * TODO Comments
    - 할일 관리가 된다.
  * Public API Documentation

5. Bad Comments
  * 중얼거림
    - 쓸데없이 길다.
  * 반복 설명
  * REdundant Explanations
  * Journal Comments
    - 변경 이력
  * Noways Comments
  * Big banner Comments
  * Closing Brace Comments
  * Attribution Comments
  * Html in Comments
  * Non-Local Information
    - 멀리 떨어진 곳의 코드를 설명하는 커멘트는 커멘트와 무관하게 변경될 수 있다.
    - 커멘트를 작성해야만 한다면 커멘트가 설명하는 코드와 밀접한 곳에 작성하라.

6. Vertical Formatting
   * 공란을 함으로 사용하지 말라.
    - 메소드 사이
    - private 변수들과 Public 변수들 사이
    - 변수선언과 메소드 실행의 나머지 부분 사이
    - if/while 블록과 다른 코드 사이
  * 서로 관련된 것들을 Vertical 하게 근접해야 한다.
    - Vertical한 거리가 그들간의 관련성을 나타낸다.
  * 관련된 정보를 나눈다.

7. Classes
  * private 변수들을 작성함으로써 클래스를 작성한다.
  * 그 private 변수들을 public 함수들로 조작한다.
  * 외부에서는 private 변수들이 없는 것 처럼 보인다.
    - 왜 변수를 private으로 선언하고 getter, setter를 제공하나?
    - 객체의 상태를 외부에서 사용할 수 있도록 하는 getter, setter, property 등을 제공하는 것은 나뿐 디자인이다.
  * TEll, Dont't Ask
    - 무엇을 하라고 시키기 쉽고 물어볼 필요가 없다.
  * max cohesive
    - 메소드가 모든 변수를 조작하는 경우
  * max cohesive Class
    - max cohesive 메소들로만 구성된 클래스
  * getter를 최소로 사용하라.
    - 추상화해서 제공해라. (다형성)
    - 가솔린, 디젤, 가스 를 묻지 말고 연료가 얼마나 남았니로 물어라
  * 다형성 - 독립적인 배포
    - 독립적 컴파일 가능
    - 독립적 개발 가능
    - 인터페이스만 유지되면 된다.
  * IOC를 통해 High level policy(클라이언트, 비지니스 로직)를 Low level Detail로 부터 보호 하는 것
    - 객체 지향의 핵심

8. data Structures
  * class와 반대되는 개념
  * public 변수의 집합
  * 기능의 추가에 대해서 자유로움
  * 변수의 추가에 취약하다.

9. boundaries
  * main 파티션을 app 파티션과 분리
  * IOC 컨테이너를 통해 DI로 분리
  * Boundary 사용시 항상 Concrete에서 Abstract로 소스 코드 의존성이 있어야 한다.
  * 의존성 역전

10. The Impedance Mismatch
  * OOP에서 RDB를 사용할때 발생하는 일련의 개념적/기술적 어려움
    - 객체나 클래스의 정의가 데이터베이스 테이블이나 관계 스키마에 직접 매핑될 때 발생
  * Data를 노출하고, 메소드는 없다.
  * DB Table은 DS이다.
    - Class와 반대
    - Db 테입이블은 너무나 concrete 해서 polymophic 할수 없다.
    - db는 도메인객체, 비지니스 객체, 어떤객체도 포함할수 없다.
  * ORM
    - 진정한 Object-relational mapper는 아니다.
    - DB row와 객체간의 직접적인 매핑이 없기 떄문이다.
  * DB는 특정 어플리케이션을 위해서가 아니라 엔터프라이즈를 위해서 최적화 된다.
