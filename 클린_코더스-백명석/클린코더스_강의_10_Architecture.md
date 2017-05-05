클린 코더스 강의 10. Architecture
=============================

> * 유튜브 : https://www.youtube.com/watch?v=60lLSe1phks
> * 강의 자료 : https://github.com/msbaek/clean-coders-2013

1. Architecture
  * 전체적인 시스템 개발에 기반을 제공하는 변경 불가능한 초기 결정사항의 집합
  * 건축의 아키텍처가 해머, 못등이 아니듯, 툴, 프레임웤 등이 아니라 사용법에 대한 것
  * Use Case
    - 사용자(actor)와 시스템의 역할을 스텝별 상호작용을 나열한 것
    - 아키텍처를 use case에 집중
  * 좋은 아키텍처는 FW, WAS, UI 등과 같은 Stuff들에 대한 결정을 연기하는 것을 허용
  * 시간이 지날 수록 결정을 위한 정보가 풍부해짐
  * FW, WAS, UI 등을 먼저 정하면 설계의 운신 폭이 작아짐
  * DB를 먼저 기동하고 스키마를 개발해야한다는 생각을 버려야 한다
  * Test Double
    - 테스트용 대역
    - MOCK, subClass 등
  * 주요한 아키텍처 결정을 연기
    - 연기 할 수 있는 한 최대한 연기하는 것이 좋다
  * DB를 core abstraction이라고 생각(X)
    - DB가 동작하고 스키마가 준비되기 전에는 어떠한 생각도, 작업도 시작하지 않는다
  * 결정을 번복할 때 비용을 최소화 할 수 있어야 한다.
