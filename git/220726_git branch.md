# git branch

- branch 
  
  - 작업공간
  
  - 하나의 repo를 branch로 나눠 commit을 서로 다르게 관리
  
  - master에서 branch로 나눠 commit 관리를 하다가 master로 합쳐서 merge
  
  - branch가 나뉘면 서로 다른 branch에서 무엇을 하는지 알수 없음
    
    (master도 하나의 branch)

- 브랜치 명령어
  
  - git branch 브랜치이름
    
    - branch 생성
  
  - git branch 
    
    - 현재 내가 어느 branch에 있는지 확인
  
  - git switch 브랜치이름
    
    - branch로 이동 ( git checkout과 같은 명령어(구버전) )
  
  - git merge '브랜치이름' 
    
    - 현재 내가 있는 branch(보통 master)에 '브랜치 이름'을 쓴 것을 합병함
  
  - git log --oneline --graph 
    
    git log --oneline -a --graph
    
    - branch의 이동과정을 그림으로 보여줌
  
  - git log --oneline -a --graph
    
    - 모든 것을 확인 가능
  
  - git pull (맨 처음은 git pull -u origin youngsik)
    
    - master에서 pull 하면 모두 받을 수 있음

- git branch 흐름
  
  1. git branch를 생성할 repo를 clone 받는다
  
  2. 나의 이름으로 이루어진 branch를 생성한다 :`git branch 브랜치이름`
  
  3. 해당 branch로 이동한다 : `git switch 브랜치이름`
  
  4. add, commit을 한다
  
     5. push 한다 : `git push origin 브랜치이름`
  
  6. github에 접속해서 pr을한다
     
     - compare%pr >> merge
  
  7. 여기까지 끝나면 remote에서 master로 merge된 상태
  
  8. `git switch master`로 master로 이동
  
  9. `git pull`로 master 최신화
  
  10. `git merge master`로 내 branch 최신화
      
      - 원래 pr이 완료된 branch는 지우는게 맞지만 실습을 위해 재활용
  
  11. 4번으로 이동하여 반복

- 추가적으로, master로 push되는 것을 막는다던가 pr에서 merge를 할 때 review를 강제하는 작업을 추가할 수 있습니다.
