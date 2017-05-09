클린 코더스 강의 13. SRP(Single Responsibility Principle)
=============================

> * 유튜브 : https://www.youtube.com/watch?v=60lLSe1phks
> * 강의 자료 : https://github.com/msbaek/clean-coders-2013

1. SRP
  * Responsibility
    - 클래스는 하나의 책임을 가져야 한다.
    - Method를 추가해도 책임의 수는 변하지 않음
  * 책임
    - SW의 변경을 요청하는 특정 사용자들에 대해 클래스/함수가 갖는 것
    - '변경의 근원'으로 볼 수 있음
  * Fan Out을 제한 하는 것이 좋다.
  * 모듈은 하나/반드시 하나의 변경 사유를 가져야 한다
  * one and only one Responsibility
    - 동일한 이유로 변경되어야 하는 것들은 동일 모듈에,
    - 다른 이유로 변경되어야 하는 것들은 다른 모듈에
  * SRP는 시스템설계 시 적용
  * OOP에서 이런 의존성을 다루는 방법
    - 클래스를 인터페이스와 클래스로 분리

>정리해야 할것
  * Fan out
  * Facade
