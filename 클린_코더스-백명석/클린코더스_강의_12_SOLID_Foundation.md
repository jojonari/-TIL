클린 코더스 강의 12. SOLID Foundation
=============================

> * 유튜브 : https://www.youtube.com/watch?v=60lLSe1phks
> * 강의 자료 : https://github.com/msbaek/clean-coders-2013

> 작업순서

1. 소스코드가 디자인이다.
  * 소스코드가 산출물이자, (설계)문서이다.
  * 잘못된 설계의 징후
    -  Rigidity
      * 시스템의 의존성으로 인해 변경하기 어려워 지는 것
    - Fragility
      * 한 모듈이 수정이 다른 모듈에 영향을 미칠 때
    - Immobility
      * 모듈이 쉽게 추출 되지 않고 재사용 되지 않는 경우
  * Viscosity(점성)
    - 빌드/테스트 같은 필수 오퍼레이션들이 오래 걸려 수행이 어렵다면 그 시스템은 역겨운 것
    - 개발자의 무책임한 용인이 원인이다.
    - 디펜던시는 유지한체 결합도를 낮춰야 한다.
  * OO의 핵심
    - IoC를 통해 상위 레벨의 모듈을 하위 레벨의 모듈로 부터 보호하는 것
  * 의존성관리에 대한 중요한 규칙 - SOLID
    - SRP
    - OCP
    - LSP
    - ISP
    - DIP
