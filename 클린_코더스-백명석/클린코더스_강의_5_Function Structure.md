클린 코더스 강의 5. Function Structure
=============================

> * 유튜브 : https://www.youtube.com/watch?v=60lLSe1phks
> * 강의 자료 : https://github.com/msbaek/clean-coders-2013

> Function Structure

1. argument
  * argument
    - 인자가 많아지면 복잡도가 증가
    - 3개의 인자가 최대
    - 생성자에 많은 수의 인자를 넘겨야 할때는 java bean param을 써라.(getter, setter)
    - builder패턴을 적용하는 것이 더 좋은 방법이다.
  * boolean 인자 사용금지
    - 2가지 이상의 일을 하는 것
    - 2개의 함수로 분리하는 것이 좋다.
  * innies not Output
    - Output인자를 사용하지 말라.
    - argument는 함수로 전달되는 것이다. 함수로 부터 변경되어 나오는 것이라고 생각하지 않음.
  * the null defense
    - null을 전달/기대하는 함수는 boolean을 전달하는 것만큼 잘못 된것
    - null을 boolean처럼 쓰지 마라.
    - 코드를 null 에러체크로 더럽히지 마라.
    - null의 존재 자체가 무엇인가 잘 못 되었다는 단서
    - null 여부를 지속적으로 조사 할 것이 아니라 단위 테스트에서 검증해라.
    - public api의 경우는 defensive하게 프로그래밍 한다.

2. The Stepdown Rule
  * 모든 public은 위에, 모든 private은 아래에
  * public part만 사용자들에게 전달하면 됨
  * 중요한 부분은 위로, 상세한 부분은 밑으로
  * 위에서 밑으로 읽어나갈 수있게 짜야한다.

3. switch
  * 스위치 문장을 쓰지 마라.
  * OOP의 가장큰 이점 중 하나는 의존성 관리 능력이다.
  * 객체지향이 가능하게 하는것
    - run-time 의존성은 그대로 둔체로 source code 의존성을 역전시킴(DIP)
    - Interface를 사용
    - 소스코드 의존성은 런타임 의존성과 반대가 된다.
    - 스프링을 잘쓰면 좋은 구조를 갖게 된다.
    - 유닛테스트가 쉬워짐
  * 스위치 문장은 독집적 배포에 방해가 된다.
    - 각 케이스문장은 외부 모듈에 이존성을 갖는다.
    - 다수의 다른 모듈에 의존성을 갖을 수 있다.
    - fan-out problem이라고 한다.
      * 독립 배포가 불가능하게 된다.
  * 스위치 문장 제거 절차
    - 스위치 문장을 폴리모픽 인터페이스 호출로 변환
    - 케이스에 있는 문장들을 별도의 클래스로 추출하여 변경 영향이 발생하지 않도록 한다.
