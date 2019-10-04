#Github 강의(생활 코딩 git 강의 참조)

  ##1. Git 의 원리
  =====
    1.0  gistory 설치 
    1.1. git init 의 원리
    1.2. git status의 원리
    1.3. git add 의 원리
    1.4. git commit의 원리
    1.5. git stage의 원리
   
   ##2. Git branch 원리
   =====
    2.1 git branch 만들기
    2.2 git branch 정보 확인
    2.3 branch 병합
    
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
  ### pip3 install gistory

  ###1.1 git init의 원리
  -----
  깃 저장소를 초기화한다. 저장소나 디렉토리 안에서 이 명령을 실행하기 전까지는 그냥 일반 폴더이다. 이것을 <str>입력한 후에야 추가적인 깃 명령어들을 줄 수 있다.</str>
  <u>깃 명령어를 주기 위해 시작점을 알리는 명령어</u>

  -----
  
  ###1.2 git add의 원리
  -----
  1.git add를 했을때 index(=stage area,tree구조)에 object이름과 실제파일이름이 추가되고(추적등록) objects에 blob타입으로 파일내용이 추가된다.
  2.git에서 원하는 파일만을 stage area

  ###1.3 git commit의 원리
  -----
  ![image_commit][commit]
  [commit]:https://milooy.files.wordpress.com/2019/06/git-github.013.jpeg?w=768 "explain of git commit"





