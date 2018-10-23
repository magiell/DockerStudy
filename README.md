# DockerStudy

docker swarm study

  1.	설치
    1.	Swarm cluster 구성 방법 
      *	Docker swarm init –advertise-addr “HostIP” (manager node)
      *	Docker swarm join (worker node)
      *	해당 스웜 토큰은 유출 되면 안되는 키
      *	–rotate worker or manager 토큰을 선택 변경
    2.	Swarm node 삭제
      *	Manager 제거는 –force 옵션 사용
      *	Docker swarm leave를 해도 manager에 node가 남아 있으므로 docker node rm진행
      *	Fault tolerance 홀수 개 임계는 보통 manager / 2 개 이기 때문
  2.	Service 구성
    1.	생성
      *	Docker service create –name “이름” –replicas “갯수”
      *	Docker service ls 서비스 확인
      *	모든 노드에 하나씩 컨테이너를 할당해야만 하는 서비스가 있으면 –mode global
      *	컨테이너 수 늘리기는 docker service scale “서비스 이름”=”숫자”
    2.	삭제
      *	Docker service rm “서비스 이름”
