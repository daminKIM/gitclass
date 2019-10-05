  [#Github 강의](https://opentutorials.org/module/2676)

    ##1. Git 의 원리
    =====
      1.0  gistory 설치 
      1.1. git init 의 원리
      1.2. git status의 원리
      1.3. git add 의 원리
      1.4. git commit의 원리
      https://backlog.com/git-tutorial/kr/intro/intro1_1.html
    
    ##2. Git branch 원리
    =====
      2.1 git branch 만들기
      2.2 git branch 정보 확인
      
    ##3. git merge 과정
    =====
      3.1 git merge
      3.2 merge와 conflict의 원리

  #Git의 원리
  =====
  ##1.0 Gistory 설치
  =====
    1.0.1pip3 install gistory
    
  ###1.1 git init의 원리
  =====
    1.1.1 깃 저장소를 초기화한다. 저장소나 디렉토리 안에서 이 명령을 실행하기 전까지는 그냥 일반 폴더이다. 
          이것을 입력한 후에야 추가적인 깃 명령어들을 줄 수 있다.
    1.1.2 깃 명령어를 주기 위해 시작점을 알리는 명령어
  
  ###1.3 git add의 원리
  =====
    1.git에서 원하는 파일만을 stage area 에 올릴 수 있음
    2.stage area에 올라간 파일은 index와 그에 따른 objectId 그리고 지칭하는 실제 파일을 담는다.
    3.objectId는 SHA1이라는 함수에 의해 생성된다.
    4.object의 3형태<br>
      1.3.4.1파일의 내용을 담고 있는 object참조값(파일명)을 가지는 blob<br>
      1.3.4.2파일명과 내용을 담고 있는 object참조값(파일명)을 가지는 blob의 집합을 담고 있는 tree<br>
      1.3.4.3마지막으로 commit<br>
  =====
  ![image_add][add](https://milooy.files.wordpress.com/2019/06/git-github.014.jpeg?w=768)"explain of git add"



  ###1.4 git commit의 원리
  =====
    1.4.1.git commit을 하면 commit 한 모든 objects에 대한 정보를 tree객체로 만든다.<br>
    1.4.2.tree객체는 commit할때의 index를 스냅샷찍어서 저장한다.<br>
    1.4.3.commit객체는 tree객체명과 Author, Date, Committer를 저장한다.<br>
    1.4.4.2번째 commit객체부터는 parent라고 이전 commit객체명을 저장한다.<br>
  =====
  ![image_commit][commit](https://milooy.files.wordpress.com/2019/06/git-github.014.jpeg?w=768)"explain of git commit"
  ![image_push][push](https://milooy.files.wordpress.com/2019/06/git-github.016.jpeg?w=768)"explain of git push"

  ###2.0 git branch의 원리
  =====
    2.0.1 branch는 독립적으로 작업하기 위한 영역
    2.0.2 branch 내부를 보자면 ref/HEAD/(branch), 처음 만들었을 경우 master branch가 초기 설정
    2.0.3 branch 안에는 최신 commit id를 포함하고 있으며, 최신 commit은 parent와 tree를 포함(앞에 설명과 유사)
    2.0.4 git log 기능에서 최신 commit한 사용할 수 있는 이유는 branch 내부 안에, 최신 commit 한 commitId를 갖고 있기 때문이다.
    ![image_branch][branch](https://backlog.com/git-tutorial/kr/img/post/stepup/capture_stepup1_1_1.png)"explain of git branch"
  ###2.1 git branch 정보 확인
  =====
    2.1.1 git branch 만들기 -> git branch "branch 이름"
    2.1.2 내가 만든 branch로 들어가고 싶을 경우 -> git checkout "내가 만들 branch 이름"
    2.1.3 내가 만든 branch를 삭제 하고 싶을 경우 -> git branch -d "내가 만든 branch 이름
    2.1.4 내가 만든 branch로 생성하고 바로 옮겨가고 싶을 경우 -> git checkout -b "생성하고 전환할 브랜치 이름"
    2.1.5 본인이 더 branch 기능에 대해 공부 하고 싶을 경우 -> git branch --help
  
  ###3.1 branch 병합(merge)<https://backlog.com/git-tutorial/kr/stepup/stepup2_7.html>
  =====
    3.1.1 branch는 분기를 만드는 것이라고 했다. 즉 다른 작업을 진행하던 중 서로 다르게 코드 작업 했던 것을 merge 하고 싶다.
    3.1.2 이 때 사용하는 것이 merge 작업
    3.1.3 내가 작업하고 있는 branch가 두 개라고 가정하자, master와 exp 그 둘을 합치고자 한다. exp에서 작업하던 것을 master로 넘기고 싶다.<br>
          일단 첫 번째 , master branch로 옮겨간다.
    3.1.4 여기서 git merge exp로 넘어가면 끝이다.
    3.1.5 병합 되는 branch들을 자세히 보고 싶을 경우, git log --branches --graph --decorate
  ###3.2 merge & conflict
  =====
    3.2.1 간혹, 병합 충돌이 일어나는 경우가 있다. 대표적으로 파일 명이 같은데, 같은 행에 오류가 날 경우 병합 충돌이 일어난다.
    3.2.2 자동 병합이 되지 않는다는 오류 메세지가 터미널에서 나타나고, 이 때 우리가 쓰는 vscode에서 충돌 해결 방법은 git 메뉴로 들어가서
          changes를 확인하며, 어떠한 변경 사항을 넣을 것인지 체크만 해주면 된다.<https://www.youtube.com/watch?v=kBIMGOxqqnk>
    3.2.3 아니면 본인이 원하는 내용을 현재 로컬에서 수정해주어 파일을 저장시키는 방법이 있다.(필자 경험)
    3.2.4 자세한 과정은 영상을 참고하길 바란다. <https://opentutorials.org/module/2676/15275>

  ###4.0 참고자료
  =====
    4.0.1 git add와 commit 그리고 push에 대해 쉽게 설명한 자료 <https://milooy.wordpress.com/2019/06/08/git-add-commit/>
    4.0.2 git 공부를 위한 참고자료 <https://backlog.com/git-tutorial/kr/intro/intro1_1.html>
    






