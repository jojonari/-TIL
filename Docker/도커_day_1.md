도커(Docker) Day 1: Dockerfile로 도커 이미지 만들기
===================================

> * 유튜브 : https://www.youtube.com/watch?v=9tW0QSsrhwc&list=PLfI752FpVCS84hxOeCyI4SBPUwt4Itd0T
> * 강의 자료 : https://docs.docker.com/get-started/

1. 도커 기본 명령어
  * docker container ls : 실행중인 컨테이너 목록조회
    * docker container ls -a : 전체 컨테이너 목록 조회
  * docker image ls : 도커 이미지 목록조회

2. 도커 기초
  * docker ps = docker container ls
    * docker 명령어가 많아지고, 분류가 필요하여 Management Commands와 Commands로 분리하여 구분
    * Management Commands를 사용하는 것을 권장

3. 실습
  ```
docker build -t friendlyhello .  # 도커이미지 생성
docker run -p 4000:80 friendlyhello  # 4000번 포트로 포트포워딩해서 friendlyhello 이미지로 컨테이너 실행
docker run -d -p 4000:80 friendlyhello         # 백그라운드 모드로 실행
docker container ls                                # 실행중인 컨테이너 목록 조회
docker container ls -a             # 전체 컨테이너 목록 조회
docker container stop <hash>           # 컨테이너 정지
docker container kill <hash>         # 컨테이너 강제 정지
docker container rm <hash>        # 컨테이너 머신 삭제
docker container rm $(docker container ls -a -q)         # 전체 컨테이너 삭제
docker image ls -a                             # 전체 이미지 목록 조회
docker image rm <image id>            # 이미지 삭제
docker image rm $(docker image ls -a -q)   # 전체 이미지 삭제
docker login             # 도커 로그인
docker tag <image> username/repository:tag  # 레파지토리용 이미지 생성
docker push username/repository:tag            # 도커허브에 이미지 푸시
docker run username/repository:tag   # 생성된 이미지로 컨테이너 실행
  ```
4. 정리
  * 도커는 shell command로 관리한다.
  * public repository가 기본값
  * 어렵게 여겨졌는데 막상해보니까 별거 없음.  
