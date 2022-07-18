[TOC]

# 220715 git 연습

## git init

새로운 git 저장소를 생성할 때 사용하는 명령어

- 사용후 : 폴더명 뒤에 (master)/ .git 폴더 생성

- git으로 관리 되는 파일 안에 git으로 관리 되는 파일을 또 설정하면 안됨.

## git status

- 파일 상태를 확인하는 명령어
  
  - working directory와 staging area 상태확인

## git add + 파일이름

- 다음 commit(변경)을 기록하기 전에 변경 분을 모아놓기 위한 명령어

- 폴더 전체를 add 할땐 `git add .`사용  

- staging area에 보관(git 보관소에 영향은 주지 않고 대기장소에 모아 두는 역할)

### staging area 사용이유

commit: version을 남긴다 /내 진행상황을 한눈에확인할 수 있도록

작업을 여러개 진행하고 commit을 하더라도 staging area를 활용하여 부분별로 묶어서 commit 가능

## git commit

- staging area에 있는것을 commit으로 등록

- `git commit -m 'commit message'` commit message에 변경사항 입력하여 관리

- `git commit`만 입력하면 VI에디터가 나옴
  
  - `i` 입력 후 commit message 작성하고 엔터 두번 누르면 본문 작성 가능
  - `esc`눌러 insert 작업을 마친 후 
  - `:wq`를 입력하여 VI에디터 종료

## git log

- commit을 남긴 기록을 확인하는 명령어

- `git log --oneline`입력 시 한줄로 commit기록 확인

- commit 오른쪽 끝에 다음과 같은 표시로 버전 확인
  
  - (HEAD -> master)`현재 로컬 상태`
  - (origin/master)`현재 git hub 상태` 

## git config

- git에 등록할 정보 입력(최초 1회)
  
  - git config --global user.name `user`
  - git config --global user.email `user@gamil.com`

- git에 설정한 정보 확인
  
  - git config --global -l
    user.name= `user`
    user.email=`user@gamil.com`

## git hub 연결하기

- git remote add origin `url`

- git push -u origin master`-u를 붙이고 입력하면 앞으로 git push만 입력해도 업데이트 됨`

## git clone 'url'

- git clone url
  
  - commit도 똑같이 나옴
  - git으로 관리되지 않는 깨끗한 폴더에서 진행
  - `git clone url`현재폴더 안에 repository 생성 후 그 안에 복사 `git clone url .` 현재폴더 안에 복사

- 이후에는 `git pull` 만 쳐도 업데이트 됨

## 로컬저장소(git)/원격저장소(github)

| 실제폴더 |
| ---- |
|      |

| working directory(git) | staging area(git) | commits(git) | commits(github) |
| ---------------------- | ----------------- | ------------ | --------------- |
|                        |                   |              |                 |

## git hub 등록하기

- `git init`(repository 등록) >> `git status`(변경사항 확인) >> `git add`(staging area에 입력) >> `git commit`(등록) 
- `git remote add origin url`(git hub와 연결) >> `git push -u origin master`(git hub 전송/이후엔 `git push`만 입력해도 가능)

## git hub 내려받기

- `git clone url`(git hub에서 복사/이후엔 `git pull`만 입력해도 가능) 

## .gitignore

- git에 공유하면 안되는 개인정보 등의 파일이 공유되지 않게 설정
  - git init 후에 바로 설정
  - .gitignore 안에 공유하지 않을 파일 이름 작성

## conflict

- 서로 다른 로컬에서 git hub로 push할 때 최신 commit이 달라서 충돌이 생겨서 문제발생
  - 해결법 : pull하여 작업하는 로컬을 git hub와 맞추고 merge한 후 작업 한 내용을 push하여 해결