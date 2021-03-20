# Github 특강

2021-03-16 멀티캠퍼스 강동주 강사님

## 1. 4차 산업혁명 소프트웨어와 프로그래밍



> **'프로젝트'** 중심의 자기소개서

* **자기를 소개하는 것이 아닌, 자기가 한 것을 소개하는 것**

* **<학습 공식>** 

  * 공고 - 내가 가진 것

    = 내가 없는 것
    = 학습해야 할 것

    

____



## 2. 프로젝트 진행을 위한 git 설치

> Github == 개발자들의 구글 드라이브
>
> Github == 개발자들의 이력서
>
> Github == 개발자들의 메모장



[git 다운로드 링크](https://git-scm.com/)



1. 다운로드가 완료된 후 default 설정으로 설치 실행

2. git bash를 찾아 실행

   ![git bash](C:\Users\power\Desktop\1.png)

3. ```shell
   $ git --version
   ```

   명령어를 통해 git version을 확인

   -> 결과 : `git version 2.31.0.windows.1`

____



## 3. 쉽고 편리한 마크다운 편집기 Typora 설치



[typora 다운로드 링크](http://support.typora.io/Typora-on-Windows/)



____



## 4. git과 github



> **git과 github 창시자가 같다? -> X**

* git의 개발자 -> 리누스 토발즈(Linus Torvalds)

* 많은 양의 코드를 관리하기 위해 SCM(Source Code Management, 코드 관리 도구) 개발

* VCS(Version Control System) : 버전 관리 도구라고도 함 -> How manage? 개념

  -> **Git은 버전을 통해 코드를 관리하는 도구**



> 버전이란?
>
> 1. 언제든지 과거의 특정 시점으로 돌아갈 수 있음
> 2. 매 작업 시점마다 변경 사항을 알 수 있음



## 5. GUI vs CLI

* GUI(Graphic User Interface) : 그래픽으로 인터렉션 할 수 있음

* CLI(Command Line Interface) : 명령어로 인터렉션 할 수 있음
  * GitHub Desktop



### CLI 명령어

* `pwd(print working directory)` : 현재 작업중인 폴더(디렉토리)
* `ls(list)` : 현재 폴더의 내용물을 출력
* `cd(change directory)` [폴더명] : 폴더를 변경
  * `cd ..` : 상위 폴더로 이동
  * `cd ~` : 홈 폴더로 이동
  * `cd .` : 현재 폴더로 이동(. 현재 폴더)
  * `cd /` : 루트 폴더로 이동(/ 루트 폴더, 최상위 폴더)
  * `cd` : 홈 폴더(기본값)로 이동
* `mkdir(make directory)[폴더명]` : 새로운 폴더 생성
* `rm -r [폴더명]` : 폴더 삭제
  * `rm -rf /` : 루트로부터 모든 폴더/파일 삭제(절대로 위험)
  * `-r` : recursive(재귀적)
* `touch [파일명]` : 새로운 파일 생성
* `rm [파일명]` : 파일 삭제
* `cp(copy) [파일명] [위치]` : 파일 복사
* `cp -r [폴더명] [위치]` : 폴더를 복사
* `mv(move) [파일/폴더명] [바꿀파일/폴더명]` : 파일/폴더명 변경
  * `mv [파일/폴더명] [위치]` : 파일 또는 폴더를 이동



### Git 명령어

`git [명령어]`



#### (1) `git init`

-> Git으로 코드 관리를 시작

* 코드 관리 단위(기준) : **폴더**
* `(master)` : 현재 브랜치 명
* `.git/` 폴더 생성 : Git으로 관리되는 폴더



#### (2) `git status` 

Git에게 상태를 물어봄 / 현재 상태를 출력

* `git init` 직후 : 

  ```shell
  On branch master
  -> master라는 브랜치 위에 있어요.
  
  No commits yet
  -> 아직 commit이 없어요.
  
  nothing to commit (create/copy files and use "git add" to track)
  -> commit할 것이 없어요.
  ```



* `test.txt` 파일 생성 후

  ```shell
  On branch master
  
  No commits yet
  
  Untracked files:
    (use "git add <file>..." to include in what will be committed)
          test.txt
  
  -> 추적되지 않은 파일이 있어요.
  	(파일명)
  
  nothing added to commit but untracked files present (use "git add" to track)
  
  -> commit 하기 위해 add된 것이 없어요. 그러나 추적되지 않은 파일은 있어요.
  ```

  

* `git add test.txt`한 후 `git status`

  ```shell
  On branch master
  
  No commits yet
  
  Changes to be committed:
    (use "git rm --cached <file>..." to unstage)
          new file:   test.txt
  
  -> commit할 변경들이 있어요.
  	(파일명)
  ```



#### (3) `git commit`

* 처음으로 commit 명령어를 실행할 경우

  ```shell
  Author identity unknown
  -> 작자 미상
  
  *** Please tell me who you are.
  -> 당신이 누군지 알려주세요.
  
  Run
  -> 아래의 명령어를 실행해주세요.
  
    git config --global user.email "you@example.com"
    git config --global user.name "Your Name"
  
  to set your account's default identity.
  Omit --global to set the identity only in this repository.
  
  fatal: unable to auto-detect email address (got 'power@DESKTOP-J2GHRPD.(none)')
  
  ```



#### (4) `git config`

configuration/

Git에 관한 설정

* `git config --global user.email "이메일"` : 전역(global)으로 user의 email을 설정

  ```shell
  $ git config --global user.email "powerover310@gmail.com"
  ```

* `git config --global user.email "이메일"` : 전역(global)으로 user의 name을 설정

  ```
  $ git config --global user.name "osori"
  ```



* `git config` 설정 후(vim 에디터 창),

  ```shell
  # Please enter the commit message for your changes. Lines starting
  -> 변경사항에 대한 commit message를 입력해주세요.
  # with '#' will be ignored, and an empty message aborts the commit.
  -> #로 시작하는 라인은 무시합니다. 아무것도 없는 메시지는 종료됩니다.
  #
  # On branch master
  #
  # Initial commit
  #
  # Changes to be committed:
  #       new file:   test.txt
  #
  
  ```

  



#### (5) `git commit -m "commit message"`

* `git commit` 이후,

  ```shell
  On branch master
  nothing to commit, working tree clean
  
  -> commit 할 것이 없어요.
  ```

  

* `commit`이란 하나의 버전을 만드는 것.
* 현재 상태의 스냅샷 촬영



#### (6) `git log`

현재까지의 commit을 출력

* `git log` 출력 화면

  ```
  commit f71358f31d1bc6c37f2aa35da4d8d211fb9513c2 (HEAD -> master)
  
  Author: osori <powerover310@gmail.com>
  -> 작성자
  
  Date:   Tue Mar 16 15:55:08 2021 +0900
  -> 날짜
      first commit
  	-> commit message
  ```

  

#### (7) 코드 편집기로 코드 편집 실행

```
$ code .
-> 현재 폴더를 VS Code로 실행
```

* 파일 수정 후, `git status`

  ```shell
  On branch master
  Changes not staged for commit:
  -> commit하기 위해 stage 되지 않은 변경사항이 있어요.
  
    (use "git add <file>..." to update what will be committed)
    (use "git restore <file>..." to discard changes in working directory)
          modified:   test.txt
  
  no changes added to commit (use "git add" and/or "git commit -a")
  
  ```

  

* ```
  $ git add test.txt
  ```

* ```
  $ git commit -m "Add title"
  ```

* ```
  $ git log --oneline # 한줄로 log 출력
  > ee50f06 (HEAD -> master) Add title
  > f71358f first commit
  ```



-> 과거버전 검색

~~~
$ git checkout f71358f
~~~

-> 현재버전으로 돌아오기

```
$ git checkout master
```

-> 뭐가 변했는지 물어보기

```
$ git diff test.txt
```





#### (8) `git remote`

* `git remote add origin [저장소이름] [저장소주소]`

  * git에게 원격저장소(remote) 추가를 명령 

* 저장소이름 : `origin`

* 브랜치이름 : `master`

  -> `git remote add origin https://github.com/osori310/basic_git`

  -> 확인 : `git remote`

* `git remote -v` (verbose)



```
$ git push origin master
```

```
$ git pull origin master # 차이가 있는 부분에 대해서 가져옴
```



#### (9) `git branch`

* 모든 branch 출력



#### (10) `git branch [new branch name]`

* 새로운 branch 생성



#### (11) `git checkout [branch name]`

* branch 이동
* 새로운 branch(Sandbox)에 Head를 두고 변경한 사항들에 대해서는 master branch에 적용되지 않음



#### (12) `git merge [branch name]`

* 누가 누구를 합병하는가? -> 중요!
* 주어(Merger) -> 목적어(mergee)
* ex) master가 test를 병합하는 경우
  1. 주어 branch 'master'로 이동
  2. `git merge test` 

Merge(**FF** / **Auto-merge** / **Merge Conflict**)



# Github TIL

## 1. TIL?

> * TIL은 **T**oday **I** **L**earn의 줄임말로 개발자 사이에서 매일 자신이 학습한 내용을 commit(기록)하는 것
> * github, bitbucket, gitlab과 같은 원격 저장소에서 제공하는 1commit-1grass의 흥미 요소 제공



## 2. TIL 세팅

### (1) Git으로 프로젝트 관리 시작 : `git init`

* 자신이 앞으로 학습한 내용을 기록할 `TIL` 폴더를 하나 생성한다. 이 때 해당 폴더는 최상단에 생성한다.

* `git bash`에서 `TIL` 폴더로 이동한 이후에 아래의 명령어로 `git` 관리를 시작한다.

  ```shell
  $ git init
  ```



### (2) Commit을 위한 Staging : `git add`

* 현재 코드 상태의 스냅샷을 찍기 위한 파일 선택(== Staging Area에 파일 추가)

  ~~~shell
  $ git add [파일 이름] # .은 모든 변경 사항을 staging area로 올림
  ~~~



### (3) 버전 관리를 위한 스냅샷 저장 : `git commit`

* 현재 상태에 대한 스냅샷을 `commit`하여, 버전 관리를 진행한다.

  ~~~shell
  $ git commit -m "commit message"
  ~~~



### (4) 원격 저장소 정보 추가 : `git remote`

* Github 원격(remote) 저장소(repository)를 생성하고 `TIL` 폴더와 연결한다.

* 새로운 원격 저장소가 추가될 때만 입력한다.

  ```shell
  $ git remote add origin [gitub 원격 저장소 주소]
  ```



### (5) 원격 저장소로 코드 `git push`

* 최종적으로 Github 원격 저장소에 push 한다.

  ```shell
  $ git push origin master
  ```



### (6) 그 외 명령어

* 현재 `git`의 상태를 조회 `git status`

  ~~~shell
  $ git status
  ~~~

* 버전 관리 이력을 조회

  ~~~shell
  $ git log
  ~~~

* `git` 설정 (user.name & user.email) : 최초 1회 설정

  ~~~shell
  $ git config --global user.name "osori"
  $ git config --global user.email "powerover310@gmail.com"
  ~~~



## 3. `README.md`

> 원격(remote) 저장소(repository)에 대한 정보를 기록하는 마크다운 문서. 일반적으로 해당 프로젝트를 사용하기 위한 방법 등을 기재한다.



### (1) `README.md` 파일 생성

* `README.md` 파일을 `TIL` 폴더(최상단)에 생성한다. 이름은 반드시 README.md로 설정한다.

  ~~~shell
  $ touch README.md
  ~~~



### (2) (자신만의) TIL 원칙에 대한 간단한 내용 추가

* 마크다운 작성법 pdf에서 배우고 실습한 내용을 토대로 `README.md` 파일을 작성한다.
* 형식은 자유롭게 작성하되 마크다운 문법(의미론적)을 지켜서 작성한다.



### (저장 후 버전 관리) : `add`, `commit`, `push`

* 작성이 완료되면 아래의 명령어를 통해 commit 이력을 남기고 원격 저장소로 push한다.

  ~~~shell
  $ git add README.md
  $ git commit -m "add README.md"
  $ git push origin master
  ~~~



## 4. 추가 학습 내용 관리

### (1) 추가 내용 관리

* `TIL` 폴더 내에서 학습을 원하는 내용의 폴더를 생성하고 파일들을 생성한 후 작업을 진행한다.

  ~~~shell
  $ mkdir python
  ~~~



### (2) 변경 사항을 저장하고, 원격 저장소로 옮긴다.

* 업데이트가 완료되면 아래의 명령어를 통해 commit 이력을 남기고 원격 저장소로 push한다.

  ~~~shell
  $ git add .
  $ git commit -m "학습 내용 추가"
  $ git push origin master
  ~~~

  



____

#### # 협업의 원칙

* 독재(master & slave)



1. Pull & Push (sync)
   - 장점 : 간단함
   - 단점 : 동시에 일할 수 없음 / 권한을 부여해야함
2. Branch & PR (Git Flow)
3. Fork & PR (Github Flow)



\ github : hphk-john



**Git**

> 코드 관리 도구
>
> 코드 협업 도구
>
> 코드 배포 도구





참고자료

생활코딩 CLI https://opentutorials.org/course/2598

Git 학습자료 (Backlog) https://backlog.com/git-tutorial/kr/intro/intro1_1.html

생활코딩 GIT(introduce) [https://opentutorials.org/course/3837](https://opentutorials.org/course/3837/22434)

생활코딩 GIT 전체 https://opentutorials.org/course/3838