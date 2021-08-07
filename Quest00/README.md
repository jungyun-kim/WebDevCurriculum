# Quest 00. 형상관리 시스템

## Introduction
* git은 2021년 현재 개발 생태계에서 가장 각광받고 있는 버전 관리 시스템입니다. 이번 퀘스트를 통해 git의 기초적인 사용법을 알아볼 예정입니다.

## Topics
* git
  * `git clone`, `git add`, `git commit`, `git push`, `git pull`, `git branch`, `git stash` 명령
  * `.git` 폴더
* GitHub

## Resources
* [Resources to learn Git](https://try.github.io)
* [Learn Git Branching](https://learngitbranching.js.org/?locale=ko)
* [Inside Git: .Git directory](https://githowto.com/git_internals_git_directory)

## Checklist
> https://www.atlassian.com/git/tutorials
> 
* Q. 형상관리 시스템은 왜 나오게 되었을까요?
  > 변경사항을 추적하고 통제하기 위함. 소프트웨어는 특히 변경이 잦은데, 변경사항을 추적/통제함으로써 형상을 관리함에 용이함으로 사용함.
  
   
* git은 어떤 형상관리 시스템이고 어떤 특징을 가지고 있을까요? 분산형 형상관리 시스템이란 무엇일까요?
  > 파일의 변경사항을 추적하고 여러명의 사용자간의 작업을 조율하기 떄문에 분산버전관리 시스템이라고 불림.

  > 분산형 형상관리 시스템은 나 혼자 작업하는게 아닌, 여러사람이 한 프로젝트를 개발을 할떄 각기 다른 기능들을 개발하여 합치는 작업을 도와줌

  * git은 어떻게 개발되게 되었을까요? git이 분산형 시스템을 채택한 이유는 무엇일까요?
  > 리눅스 커널을 개발할때 필요로 하게 되었으며, 커널 역시 여러사람들이 개발하다보니 분산형 형상관리시스템이 필수였었음

* git과 GitHub은 어떻게 다를까요?
  > git은 시스템의 이름이고, GitHub은 시스템을 서비스하는 가장 유명한 서비스회사 중 하나임

* git의 clone/add/commit/push/pull/branch/stash 명령은 무엇이며 어떨 때 이용하나요? 그리고 어떻게 사용하나요?
  > clone 레포지토리 복제(보통 작업을 최초에 시작할때 원격지에서 로컬로 가져올때 사용)

  > add 레포지토리에 파일을 추가

  > commit add 한 파일과 그에 대한 상세내역을 하나의 세이브포인트처럼 저장함

  > push 원격레포지토리에 커밋된 내역을 반영

  > pull 원격레포지토리에 추가된 내역을 로컬에 반영

  > branch 나무에서 가지가 뻗어나오듯이, 기능을 개발할때 브랜치를 생성하여 개발 후 반영하도록 구성함. 보통 gitflow 를 사용함

  > stash 로컬의 작업내용을 잠시 저장해두는 용도
  
* git의 Object, Commit, Head, Branch, Tag는 어떤 개념일까요? git 시스템은 프로젝트의 히스토리를 어떻게 저장할까요?
  > 저장소는 스냅샷 기반이며, 모든 변경이나 파일을 포함하는 대상은 오브젝트로 표현된다. 오브젝트는 Commit, Tree, BLOB, Tag가 있는데, BLOB은 leaf노드로 실제 관리되는 파일이 여기에 들어간다.

  > Object는 tree, parent, commit message 등을 가진 객체로 parent에는 링크드리스트처럼 연결되어져 있다.
  
  > Commit 이란 현재의 변경사항을 스냅샷으로 생성하는 것을 말합니다.

  > Head는 현재의 커밋을 말합니다.

  > Branch는 독립적인 개발 라인을 말합니다. 여기서 추가/수정한 파일이나 디렉토리를 커밋하여 분기에 기록후 이 독립적인 분기를 다시 합칠 수 있습니다.

  > Tag 는 git 기록의 특정 지점을 가리키는 참조입니다. 보통 릴리즈 이후 tag를 생성하여 관리할 수 있습니다.

* 리모트 git 저장소에 원하지 않는 파일이 올라갔을 때 이를 되돌리려면 어떻게 해야 할까요?
  > local의 내용을 remote에 강제로 덮어씌우는 작업이기 때문에 조심해야 한다.

  로컬에서 가장 최근 커밋을 취소하고 원하는 시점으로 돌아간 후에 다시 커밋을 한다.
  ```
  git reset HEAD^
  git reset {commit id}  
  git commit -m "Write commit messages"
  ```

  원격저장소에 강제로 push 한다.
  ```
  git push origin {branch name} -f





## Quest
* GitHub에 가입한 뒤, [이 커리큘럼의 GitHub 저장소](https://github.com/KnowRe-Dev/WebDevCurriculum)의 우상단의 Fork 버튼을 눌러 자신의 저장소에 복사해 둡니다.
* Windows의 경우 같이 설치된 git shell을, MacOSX의 경우 터미널을 실행시켜 커맨드라인에 들어간 뒤, 명령어를 이용하여 복사한 저장소를 clone합니다.
  * 앞으로의 git 작업은 되도록 커맨드라인을 통해 하는 것을 권장합니다.
* 이 문서가 있는 폴더 바로 밑에 있는 sandbox 폴더에 파일을 추가한 후 커밋해 보기도 하고, 파일을 삭제해 보기도 하고, 수정해 보기도 하면서 각각의 단계에서 커밋했을 때 어떤 것들이 저장되는지를 확인합니다.
* `clone`/`add`/`commit`/`push`/`pull`/`branch`/`stash` 명령을 충분히 익혔다고 생각되면, 자신의 저장소에 이력을 push합니다.

## Advanced
* Mercurial은 어떤 형상관리 시스템일까요? 어떤 장점이 있을까요?
> git 보다 다루기 간단

> git은 스냅샷을 저장하지만 머큐리얼은 바뀐 파일을 저장함

> 윈도우에서 머큐리얼의 성능은 빠름

* 실리콘밸리의 테크 대기업들은 어떤 형상관리 시스템을 쓰고 있을까요?
> MS는 Team Foundation Server

> Google은 Piper

## Add
* 하기쉬운 실수들(https://about.gitlab.com/blog/2018/08/08/git-happens/)