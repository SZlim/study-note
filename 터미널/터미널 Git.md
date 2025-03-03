## 터미널에서 git을 사용하지 말고 git desktop이용.
##### 초기화 git init

##### 사용자 정보설정
- git config --global user.name "내이름"
- git config --global user.email "you@example.com"
- 사용자 정보 확인
	- git config --list
	- 사용자이름 확인 git config user.name
	- 사용자 이메일 확인 git config user.email
	- 전역확인 git config --global --list
	- 로컬확인 git confgi --local --list

##### 줄바꿈 문제 lf cnlf
- git config core.autocrlf false - windows 내 linux등 다른 저장소 사용시 위 명령어 사용.

##### git hub과 로컬 연결방법
- GitHub에서 새 리포지토리 생성
- 로컬 폴더를 Git 리포지토리로 초기화
	- git init
	- git remote add origin 복사한_리포지토리_URL => 로컬 repository와 github repository 연결
	- git add . => 모든 파일 스테이징 영역에 추가
	- git commit -m "commit문구" => 변경사항 commit
	- git push -u origin master => github repository로 push
