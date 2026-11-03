# codyssey
코디세이1-1 프로젝트

# 개발 워크스테이션 구축 보고서

1. 깃허브 계정 생성 및 Git 설치

GitHub 계정 만들기: github.com에서 회원가입
Git 설치하기: 내 컴퓨터의 파일을 깃허브에 올리려면 'Git'이라는 프로그램이 필요합니다. git-scm.com에서 본인의 운영체제(Windows/Mac)에 맞는 버전을 설치하세요.
2. 내 컴퓨터에 사용자 정보 설정하기
설치가 끝났다면 터미널(Windows는 CMD 또는 Git Bash)을 열고, 내가 누구인지 Git에게 알려줘야 합니다. 깃허브에 가입한 정보와 동일하게 입력하세요.
# 사용자 이름 설정
git config --global user.name "janghongtae"

# 사용자 이메일 설정
git config --global user.email "redsun3810.gmailcom"
# 1. 현재 폴더를 Git이 관리하도록 설정
git init

# 2. 올릴 파일들을 장바구니에 담기 (.은 모든 파일을 의미)
git add .

# 3. 장바구니에 담긴 파일들에 메모 남기기 (버전 생성)
git commit -m "첫 번째 업로드"

# 4. 내 컴퓨터와 온라인 저장소 연결 (주소 부분에 복사한 주소 붙여넣기)
git remote add origin https://github.com/아이디/저장소이름.git

# 5. 온라인 저장소로 실제로 보내기
git push -u origin main

redsun38100018@GNIA-C202-I05 UCRT64 ~ (master)
터미널 맨 앞을 보면 경로가 ~ (물결표)로 되어 있죠? 이것은 **사용자 홈 디렉토리(내 컴퓨터 전체의 개인 폴더)**를 의미합니다.
# 홈 디렉토리에 잘못 생성된 git 저장소 설정을 삭제합니다.
rm -rf .git
# 1. 작업할 프로젝트 폴더로 이동 (경로가 맞는지 확인하세요)
cd /c/test/작업실

# 2. 이동한 폴더에서 다시 git 초기화
git init

# 3. 브랜치 이름을 main으로 설정
git branch -M main
git add .
git commit -m "첫 번째 업로드"
git remote add origin https://github.com/아이디/저장소이름.git
git push -u origin main
redsun38100018@GNIA-C202-I05 UCRT64 /c/test/작업실 (main)

## 1. 환경 정보
- OS: Windows 11 pro(버전:26H2)
- 작성일: 2026-_11-3

## 2. 설치 및 설정 과정

### 2-1. Git
- 확인 명령: `git --version`
- 출력 결과: `git version 2.56.0`
- 설명: Git이 이미 설치되어 있어 별도 설치 없이 버전만 확인함.
- 
### 2-2. Docker Desktop 설치
- 설치 버전: Docker Desktop 4.97.0
- 설치 결과: Installation succeeded (<img width="1043" height="729" alt="스크린샷 2026-11-03 162520" src="https://github.com/user-attachments/assets/1fdf9558-d316-40d1-88e5-1a0a81d962a7" />
)
- 확인 명령어: `docker --version`
- 출력 결과: (Docker version 29.9.2, build a82e528)
- 설명: 공식 사이트에서 AMD64 버전을 받아 설치 완료함.

### 2-3. Docker 동작 테스트
- 명령어: `docker run hello-world`
- 출력 결과:
  (Hello from Docker!

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.)
- 설명:
- Docker 클라이언트가 Docker 데몬(엔진)에게 요청
데몬이 Docker Hub에서 hello-world 이미지를 다운로드 (amd64 버전!)
그 이미지로 컨테이너를 생성해서 실행
실행 결과를 터미널에 출력

### Docker란?
- 컨테이너를 쉽게 생성/실행/관리할 수 있게 해주는 도구
- 클라이언트(명령 입력) + 데몬(실제 작업)으로 구성됨
- Docker Desktop은 윈도우에서 Docker를 편리하게 쓰는 패키지

 ✅ 정리
컨테이너 🍱 = 프로그램을 담은 도시락
Docker 🐳 = 그 도시락을 만들고 실행하는 전체 시스템/도구
클라이언트(주문) + 데몬(주방)으로 동작
Docker Desktop = 윈도우에서 쉽게 쓰는 묶음 패키지

  
## 3. 트러블슈팅
### 문제 1: (제목)
- 상황:
- 원인:
- 해결:

## 4. 느낀 점

```
docker --version
```

![설명글](images/파일이름.png)

### CPU 아키텍처 확인
- 명령어: `echo $env:PROCESSOR_ARCHITECTURE`
- 출력 결과: AMD64
- 설명: 내 PC는 AMD64 아키텍처이므로 Docker Desktop도 AMD64 버전을 설치함.

- <img width="1043" height="729" alt="image" src="https://github.com/user-attachments/assets/46abe3ce-9cf0-41ba-b5c6-55e23c610373" />
