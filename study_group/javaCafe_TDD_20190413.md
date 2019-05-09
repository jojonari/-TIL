정적 분석도구 소나큐브 사용하기
==================

1. 정적 분석 툴
  1. 의미
    * ```정적 프로그램 분석 (Static program analysis)은 실제 실행 없이 컴퓨터 소프트웨어를 분석하는 것을 말한다. 대부분의 경우에 분석은 소스 코드의 버전 중 하나의 형태로 수행되며, 가끔은 목적 파일 형태로 분석된다. 이에 반하여 실행 중인 프로그램을 분석하는 것을 동적 프로그램 분석이라고 한다```
    * 좋은 정적 분석도구란?
      * True Positive(결함이 있는 코드를 결함으로 탐지), False Negative(결함이 아닌 코드를 결함으로 미탐지)가 극대화되고
    * False Positive(결함이 없으나 결함으로 탐지), True Negative(결함이 있으나 결함을 못찾음)가 최소화
    * False Positive - 오탐지와 True Negative - 미탐지가 없어야 한다.
    * 소나큐브 - [위키](https://sonarqubekr.atlassian.net/wiki/)
      * 대표적인 정적 분석도구
        * 정적분석에 관한한 끝판왕
      * 심각도 레벨
        * Critical
        * Major
        * Minor
      * Quality Model
        * Bugs : 확실히 잘못되었거나, 예상치 못한 동작의 가능성이 높은 코드를 추적합니다.
        * Vulnerabilities : 해커들의 침입을 당할 수 있는 잠재적인 취약점을 가진 코드를 식별합니다.


1. 소나큐브 설치
  * 사전 조건
    * 자바8
    * MySQL 등의 DB (없으면 내장 DB가 사용되며 확장성 등의 제약 있음)
    * ```CREATE DATABASE sonar CHARACTER SET utf8 COLLATE utf8_bin;
GRANT ALL PRIVILEGES ON sonar.* TO 'sonar'@'localhost' IDENTIFIED BY 'sonar';```
  * 설치
    * 설치 : brew install sonarqube
    * 실행 : brew services start sonarqube
    * 접속 : http://localhost:9000
      * admin / admin
    * 소나 큐브 스캐너 설치
      * 설치 : brew install sonar-scanner
      * https://www.popit.kr/%EB%82%B4%EC%BD%94%EB%93%9C%EB%A5%BC-%EC%9E%90%EB%8F%99%EC%9C%BC%EB%A1%9C-%EB%A6%AC%EB%B7%B0%ED%95%B4%EC%A4%80%EB%8B%A4%EB%A9%B4-by-sonarqube/
