## 3. Linux & Shell Command

### 1. Linux

- 개발자, 특히 서버와 관련된 직군은 linux를 많이 접하게 됨
- 서버에서 자주 사용
  - 오픈 소스로, 무료 서비스 가능
- 안정성, 신뢰성이 높음

>**CLI**
>
>- Command Line Interface
>- terminal
>
>**GUI**
>
>- Graphic User Interface
>- desktop

linux는 다양한 배포판이 있음

- Debian
  - 온라인 커뮤니티에서 제작해 배포
- Ubuntu
  - 초보자들이 쉽게 접근할 수 있도록 제작
- Redhat
- CentOS
  - Red Hat이 공개한 버전을 브랜드와 로고를 제거하고 배포한 버전

쉘 커맨드, 쉘 스크립트 위주의 학습





### 2. Shell

- 사용자가 문자를 입력해 명령할 수 있도록 하는 프로그램

- bash

  - Linux 표준 쉘

- 용도

  - 서버에 접속해 사용하는 경우
  - Linux의 내장 기능을 활용하는 경우
  - 데이터 전처리
  - Docker
  - 수백대의 서버를 관리할 때
  - jupyter notebook에서 !를 붙이면 쉘 커맨드
  - Test Code실행
  - 배포 파이프라인 실행

- 쉘 커맨드

  - `man`
    - 대부분 커맨드의 manual을 보여줌
  - `mkdir`
    - make directory
    - 폴더를 생성하는 명령어
  - `ls`
    - List Segments
    - 아무것도 입력하지 않으면 현재 폴더, 폴더를 작성하면 해당 폴더 기준
    - `-a`: .으로 시작하는 파일, 폴더를 포함해 전체 파일 출력
    - `-l`: 퍼미션, 소유자, 만든 날짜, 용량까지 출력
    - `-h`: 사람이 읽기 쉬운 형태로 출력
  - `pwd`
    - Print Working Directory
    - 현재 경로
  - `cd`
    - change directory
    - 경로 변경하기
  - `echo`
    - python의 `print`와 같이 출력하는 기능
    - \`를 사용하면 \`사이의 기능이 실행되고 결과가 출력
  - `vi`
    - vim 편집기로 진입
    - Insert모드에서만 수정할 수 있음
    - ESC누르고 `:wq`  (저장하고 나가기)
    - 강제로 저장하려면 뒤에 !
  - `sudo`
    - 최고 관리자 권한으로 실행
  - `cp`
    - copy
  - `mv`
    - move
  - `cat`
    - concatenate
    - \> : ovewrite
    - \>\> : append  
  - `clear`
    - 쉘 커맨드 정리
  - `history`
    - 쉘 커맨드에 입력한 커맨드 history 출력
    - !n 입력하면 n번 커맨드를 다시 활용
  - `find`
    - `find . -name "file"` 현재 폴더에서 file이라는 이름을 가진 파일 또는 폴더 검색
  - `export`
    - 환경변수 설정

  >  Shell에서는 띄어쓰기 주의

  - `alias`
    - 별칭 지정
    - ex) `ll`은 `ls -l`로 지정되어 있음
    - `alias 별칭='명령어'`
  - `head`, `tail`
    - 파일 앞/뒤 n행 출력
    - 파일의 형태를 보거나 최근 로그 확인 등
  - `sort`
    - `-r`:내림차순
    - `-n`:numeric sort
  - `uniq`
    - 연속된 중복행 제거
  - `grep`
    - `grep option pattern`식으로 사용
    - 파일 찾을 때 사용
  - `cut`
    - 파일의 특정 필드 추출
    - `-f`:잘라낼 필드 지정
    - `-d`:필드를 구분하는 구분자

  > 표준 스트림
  >
  > Unix에서 동작하는 프로그램은 커맨드 실행시 3개의 Stream이 생성
  >
  > stdin:0, 입력
  >
  > stdout: 1, 출력
  >
  > stderr: 2, 디버깅 정보나 에러

  - Redirection
    - Redirection: 프로그램의 출력을 다른 파일이나 스트림으로 전달
    - `>` : 덮어쓰기 또는 생성
    - `>>` : 맨 아래에 추가
  - Pipe
    - 프로그램의 출력을 다른 프로그램의 입력으로 사용하고 싶은 경우
  - `ps`
    - Process Status
    - `-e`: 모든 프로세스
    - `-f`: Full Format으로 자세히 보여줌
  - `curl`
    - Client URL
    - 웹 서버 작성 후 요청 확인
  - `df`
    - Disk Free
    - 용량 확인
  - `scp`
    - secure copy
    - `-r`: 재귀적으로 복사
    - `-P`: ssh 포트 지정
    - `-i`: ssh설정을 활용해 실행
  - `nohup`
    - 터미널 종료 후에도 계속 작업이 유지되도록 실행
    - 종료는 `ps ef|grep 파일명`으로 PID 찾은 후 `kill -9 pid`
    - 로그는 nohup.out에 저장
  - `chmod`
    - change mod
    - 파일의 권한을 변경하는 경우 사용



- 쉘 스크립트
  - 쉘 커맨드의 조합
  - .sh 파일을 생성해 쉘 커맨드를 추가
  - bash 명령어로 실행
