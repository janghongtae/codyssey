# codyssey
코디세이1-1 프로젝트

# 개발 워크스테이션 구축 보고서

## 1. 환경 정보
- OS: Windows 11 pro(버전:26H2)
- 작성일: 2026-11-3

## 2. 설치 및 설정 과정

### 2-1. Git
- 확인 명령: `git --version`
- 출력 결과: `git version 2.56.0`
- 설명: Git이 이미 설치되어 있어 별도 설치 없이 버전만 확인함.
  
### 2-2. Docker Desktop 설치
- 설치 버전: Docker Desktop 4.97.0
- 설치 결과: Installation succeeded <img width="1043" height="729" alt="스크린샷 2026-11-03 162520" src="https://github.com/user-attachments/assets/1fdf9558-d316-40d1-88e5-1a0a81d962a7" />

- 확인 명령어: `docker --version`
- 출력 결과:
```
Docker version 29.9.2, build a82e528
```
- 설명: 공식 사이트에서 AMD64 버전을 받아 설치 완료함.
  
### 2-3. CPU 아키텍처 확인
- 명령어: `echo $env:PROCESSOR_ARCHITECTURE`
- 출력 결과: AMD64
- 설명: 내 PC는 AMD64 아키텍처이므로 Docker Desktop도 AMD64 버전을 설치함.

### 2-4. Docker 동작 테스트
- 명령어: `docker run hello-world`
- 출력 결과:
```
 Hello from Docker!

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.
```
- 설명:
  1. Docker 클라이언트가 데몬에게 요청
  2. 데몬이 Docker Hub에서 이미지 다운로드 (amd64)
  3. 그 이미지로 컨테이너 생성 및 실행
  4. 실행 결과를 터미널에 출력

### Docker란?
- 컨테이너를 쉽게 생성/실행/관리할 수 있게 해주는 도구
- 클라이언트(명령 입력) + 데몬(실제 작업)으로 구성됨
- Docker Desktop은 윈도우에서 Docker를 편리하게 쓰는 패키지

**✅ 정리**
- 컨테이너 🍱 = 프로그램을 담은 도시락
- Docker 🐳 = 그 도시락을 만들고 실행하는 전체 시스템/도구
- 클라이언트(주문) + 데몬(주방)으로 동작
- Docker Desktop = 윈도우에서 쉽게 쓰는 묶음 패키지

## 3. 깃허브 계정 생성 및 Git 설치

# GitHub 계정 만들기: github.com에서 회원가입
Git 설치하기: 내 컴퓨터의 파일을 깃허브에 올리려면 'Git'이라는 프로그램이 필요합니다. git-scm.com에서 본인의 운영체제(Windows/Mac)에 맞는 버전을 설치.

# 내 컴퓨터에 사용자 정보 설정하기
설치가 끝났다면 터미널(Windows는 CMD 또는 Git Bash)을 열고, 내가 누구인지 Git에게 알려줘야 합니다. 깃허브에 가입한 정보와 동일하게 입력하세요.

### 3-1. 사용자 정보 설정
사용자 이름과 이메일을 등록합니다. (GitHub 가입 정보와 동일하게)
```bash
git config --global user.name "username"
git config --global user.email "user.name@example.com"
```

### 3-2. 저장소 생성 및 업로드
```bash
git init                  # 현재 폴더를 Git 관리 대상으로
git add .                 # 모든 파일을 스테이지에 담기
git commit -m "첫 업로드"  # 버전 기록 남기기
git remote add origin https://github.com/아이디/저장소이름.git  # 원격 연결
git push -u origin main   # 온라인 저장소로 전송
```

  
## 4. 트러블슈팅

### 문제 1: 홈 디렉토리에 잘못 git init 함
상황: 터미널 경로가 ~ (홈 디렉토리) 인 상태에서 git init 실행함. 프롬프트에 (master)가 떠서 잘못된 위치임을 알게 됨.
원인: 작업 폴더로 이동하지 않고 홈에서 바로 초기화해서, 개인 폴더 전체가 Git 관리 대상이 되어버림.
해결: rm -rf .git 으로 잘못된 설정을 삭제하고, cd /c/test/작업실 로 이동한 뒤 다시 git init 함.
배운 점: git init은 반드시 '작업할 폴더 안'에서 실행해야 한다.

### 문제 2: Docker 버전 번호가 두 개라 헷갈림
- 상황: 설치 화면은 4.97.0인데 docker --version은 29.9.2가 나옴.
- 원인: 4.97.0은 Docker Desktop(앱), 29.9.2는 Docker 엔진 버전으로
         서로 다른 것을 가리키는 번호였다.
- 해결: 두 버전을 구분해서 보고서에 각각 기록함.
- 배운 점: 하나의 프로그램에도 여러 버전 번호가 있을 수 있다.

### 문제 3: Docker 데몬 연결 실패
- 상황: docker run hello-world 실행 시
         "failed to connect to the docker API ...
          check if the daemon is running" 오류 발생.
- 원인: Docker Desktop(데몬/엔진)이 꺼진 상태에서 명령을 입력함.
- 해결: Docker Desktop을 실행하고 고래 아이콘이 준비될 때까지
         기다린 뒤 다시 실행하니 정상 작동함.
- 배운 점: Docker 명령은 데몬(엔진)이 켜져 있어야 동작한다.

## 5. 느낀 점

- 처음엔 Docker가 막연히 어렵게 느껴졌지만, 컨테이너를
  '도시락'에 비유하니 개념이 잡혔다.
- 홈 디렉토리에 git init을 한 실수를 직접 겪으면서,
  명령어는 '어디서 실행하는지'가 중요하다는 걸 배웠다.
- 다음엔 작업 전에 현재 경로를 꼭 확인하는 습관을 들여야겠다.

