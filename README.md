# codyssey
코디세이1-1 프로젝트
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
