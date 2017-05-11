클린 코더스 강의 14.2. LSP(Liskov Substitution Principle)
=============================

> * 유튜브 : https://www.youtube.com/watch?v=60lLSe1phks
> * 강의 자료 : https://github.com/msbaek/clean-coders-2013

1. LSP(리스코프 치환 원칙)
  * 자료형 S가 자료형 T의 하위형이라면 필요한 프로그램의 속성(정확성, 수행하는 업무 등)의 변경 없이 자료형 T의 객체를 자료형 S의 객체로 교체(치환)할 수 있어야 한다는 원칙이다.
  * OCP
    - 추상화, 다형성을 이용해서 구현
  * LSP
    - OCP를 받쳐주는 다형성에 관한 원칙을 제공
    - LSP가 위반되면 OCP도 위반됨
      * subtype이 추가될 때마다 클라이언트들이 수정된
