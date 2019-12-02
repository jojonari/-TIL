도커(Docker) Day 2: 도커 Swarm과 서비스
===================================

> * 유튜브 : https://youtu.be/p58k2_HMWRM
> * 강의 자료 : https://docs.docker.com/v18.03/get-started/

1. 도커 스왐과 서비스
  * swarm : 도커 스웜은 도커 컨테이너를 위한 클러스터링, 스케줄링 툴이다. 스웜을 이용하면 여러 개의 서버와 컨테이너 관리를 쉽게 할 수 있다. 수많은 컨테이너 오케스트레이션 도구 중의 하나로, 여러 대의 Docker 호스트들을 마치 하나인 것처럼 만들어주는 Orchestration 도구입니다.
    * 도커 스웜 노드 : 도커(1.12 버전 이후)나 스웜 모드에서 돌아가는 도커 서버를 말한다. 도커 스웜에는 manager 노드와 worker 노드가 있다.
    * 매니저 노드(manager node) : 클러스터의 상태를 유지, 스케쥴링, 스웜모드를 제공한다.
    * 작업자 노드(worker node) : 일반적으로 컨테이너를 실행하는 노드를 작업자 노드라고 한다.
    ![서비스구성](https://docs.docker.com/v18.03/engine/swarm/images/ingress-routing-mesh.png)

```
docker-machine create --driver virtualbox myvm1 # VM 생성 (Mac, Win7, Linux)
docker-machine env myvm1                # VM 머신에 직접 붙기
docker-machine ssh myvm1 "docker node ls"         # 머신내에 노드 리스트 보기
docker-machine ssh myvm1 "docker swarm join-token -q worker"   # 도커 조인 토큰 보기
docker-machine ssh myvm1   # 도커 머신에 ssh로 붙기
docker-machine ssh myvm2 "docker swarm leave"  # Swarm 종료
docker-machine ssh myvm1 "docker swarm leave -f" # 매니저 Swarm 종료
docker-machine ls # 도커 머신 리스트 보기
docker-machine start myvm1            # 도커머신 시작하기
docker-machine env myvm1      # 토커머신에 직접붙기
eval $(docker-machine env myvm1)         # 머신의 쉘 사용하기
docker stack deploy -c <file> <app>  # 로컬의 컴포즈 파일 사용하여 배포하기
docker-machine scp docker-compose.yml myvm1:~ # 머신으로 파일 복사
docker-machine ssh myvm1 "docker stack deploy -c <file> <app>"   # 복사된 컴포즈 파일 사용하여 배포하기
eval $(docker-machine env -u)     # 머신의 쉘에서 나와 로컬 쉘 사용하기
docker-machine stop $(docker-machine ls -q)               # 전체 머신 정지
docker-machine rm $(docker-machine ls -q) # 전체 머신 삭제
```

2. 정리
  * swarm은 도커 오케스트레이션을 도와주는 툴
  * 순서
    1. 가상 머신을 만들고
    2. swarm 매니저를 지정
    3. swarm worker를 조인
    4. compose.yml을 통해 배포
    5. node 확인
  * 쉽게 오케스트레이션이 가능하다.
  * But 관리/모니터링은 어떻게 하지?
    * 모니터링만 쉽게 되어도 좋을거 같다.
    * 다음장을 기대해봅니다.
