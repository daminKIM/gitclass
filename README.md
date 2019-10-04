  #Github 강의(생활 코딩 git 강의 참조)

    ##1. Git 의 원리
    =====
      1.0  gistory 설치 
      1.1. git init 의 원리
      1.2. git status의 원리
      1.3. git add 의 원리
      1.4. git commit의 원리
      
    
    ##2. Git branch 원리
    =====
      2.1 git branch 만들기
      2.2 git branch 정보 확인
      2.3 branch 병합gt
      
    ##3. git merge 과정
    =====
      3.1 reset과 checkout의 원리
      3.2 merge와 conflict의 원리
      3.3 3way merge 
    ##4. Github
    =====
      4.1 원격 저장소를 지역 저장소로 복제(Github)
      4.2 원격 저장소 만들기(Github)
      4.3 원격 저장소와 지역 저장소의 동기화 방법 (Github)
      -----

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


  ###1.4 git commit의 원리
  =====
    1.4.1.git commit을 하면 commit 한 모든 objects에 대한 정보를 tree객체로 만든다.<br>
    1.4.2.tree객체는 commit할때의 index를 스냅샷찍어서 저장한다.<br>
    1.4.3.commit객체는 tree객체명과 Author, Date, Committer를 저장한다.<br>
    1.4.4.2번째 commit객체부터는 parent라고 이전 commit객체명을 저장한다.<br>
    -----
    ![image_commit][commit]
    [commit]:https://milooy.files.wordpress.com/2019/06/git-github.013.jpeg?w=768 "explain of git commit"






