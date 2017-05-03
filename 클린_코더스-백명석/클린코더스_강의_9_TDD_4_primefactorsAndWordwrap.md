클린 코더스 강의 9. TDD 4 - primefactors and wordwrap
=============================

> * 유튜브 : https://www.youtube.com/watch?v=60lLSe1phks
> * 강의 자료 : https://github.com/msbaek/clean-coders-2013

> 실습 -bowling game
> 준비
> 클론
> $git clone https://github.com/msbaek/bowling-game.git

1. 소인수 분해
  * 소수(prime number)
    - 1과 자기 자신 외의 정수로는 나누어 떨어지지 않는 정수. 예. 2, 3, 5, 7, 11, 13, 17, 19, ....
  * 소인수(prime factor)
    - 어떤 정수를 소수만의 곱으로 나타낼 때 그 인수가 되는 각각의 소수. ‘30=2×3×5’에서 ‘2’, ‘3’, ‘5’ 따위의 소수를 말한다.

2. Getting stuck
  * 현재 실패하고 있는 테스트를 성공시키기 위해 점진적으로 할 수 있는 일이 없고 테스트를 성공시키기 위해서는 아주 많은 양의 프로덕션 코드를 작성해야하고 근단적인 경우 전체 알고리즘을 다시 작성해야만 하는 경우를 일컫는 기술적 용어
  * getting stuck 발생징후
    - 잘못된 테스트 작성
    - 프로덕션 코드를 너무 구체적으로 작성
    - 위의 두 문제 모두 해당하는 경우
    

> 실습 코드
> https://github.com/jojonari/prime_number_generator.git
