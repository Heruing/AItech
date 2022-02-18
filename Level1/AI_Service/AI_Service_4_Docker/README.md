## 4. Docker

#### 1. Docker 소개

1. 가상화란?
   - 개발을 진행한 Local 환경과 Production 서버 환경이 다른 경우
   - 다양한 설정을 README 등에 기록하고, 항상 실행하도록 하는 방법
     - Human Error 발생 가능
     - 매번 이러한 작업을 해야하는 과정이 귀찮음
   - 위 같은 문제 떄문에 서버 환경도 한 번에 소프트웨어화 하려는 방법
   - Docker 이전에는 Virtual Machine을 사용
     - GCP의 Compute Engine 또는 AWS EC2
   - Container
     - VM의 무거움을 덜어주며 경량화된 가상화 구현 도구

- Docker

  - Container 기술을 쉽게 사용할 수 있도록 나온 도구

  - 2013년 오픈소스로 등장

  - 컨테이너에 기반한 개발과 운영을 매우 빠르게 확장

  - PC방에서 기존 프로그램만 유지되듯 재부팅 시 Docker Image 상태로 실행

  - Docker Image
    - 컨테이너를 실행할 때 사용할 수 있는 템플릿
    - Read Only
  - Docker Container
    - Docker Image를 활용해 실행된 인스턴스
    - Write 가능
  - 다른 사람이 만든 소프트웨어(Docker Image) 활용 가능
    - OS, 설정을 포함한 실행 환경
  - 이미지를 만들어 공유 가능
    - 원격 저장소에 저장하면 어디서나 사용 가능



#### 2. Docker 실습하며 배워보기

1. `docker pull 이미지이름:태그`
2. `docker images`
   - 이미지 확인
3. `docker run`
   - `--name name`
     - 컨테이너 이름
   - `-e`
     - 환경변수 설정
   - `-d`
     - 백그라운드 실행(데몬)
   - `-p 로컬호스트:컨테이너포트`
     - 포트지정
   - `-v`
     - Volume Mount
     - Host와 Container의 폴더가 공유됨
4. `docker ps`
   - 실행한 컨테이너 확인
   - `-a`를 붙이면 작동이 멈춘 컨테이너도 확인 가능
5. `docker exec -it 컨테이너 이름 /bin/bash`
   - MySQL이 실행되고 있는지 확인하기 위해 컨테이너 진입
   - Compute Engine에서 SSH에 접속하는 것과 유사
6. `docker stop 컨테이너`
7. `docker rm`
   - 컨테이너 삭제
   - `-f` 실행중인 컨테이너도 삭제 가능하지만, 실수 방지를 위해 비추천





