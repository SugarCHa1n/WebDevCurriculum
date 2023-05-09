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
* 형상관리 시스템은 왜 나오게 되었을까요?
- 형상관리를 하지 않게 된다면 더 힘들어지는 복잡한 코드를 덜 복잡하게 관리하고, 협업할 수 있도록 하기 위해 나오게 된 것 같다.

* git은 어떤 형상관리 시스템이고 어떤 특징을 가지고 있을까요? 분산형 형상관리 시스템이란 무엇일까요?
- git은 분산형 버전 관리 시스템으로, CVS, SVN등 다른 형상관리 시스템처럼 레파지토리를 활용하여 다수의 End Point에서 중복된 작업 없이 버전 관리를 가능하게 한다.

  * git은 어떻게 개발되게 되었을까요? git이 분산형 시스템을 채택한 이유는 무엇일까요?
  - git은 소스코드를 효과적으로 관리하기 위해 개발된 형상관리시스템이며, 분산형 시스템을 채택한 이유는 분산버전관리시스템은 중앙서버에 문제가 생겨도 변경기록들과 함께 서버를 복원시킬 수 있기 때문입니다.

* git과 GitHub은 어떻게 다를까요?
- git은 본인의 코드와 이력을 기록하고 관리하도록 돕는 버전 관리 시스템입니다. github는 git저장소를 관리하는 클라우드 기반 호스팅 서비스이며, 개인의 로컬서버 밖에서 git버전 프로젝트를 공유하고 기록하는 온라인 데이터베이스입니다.

* git의 clone/add/commit/push/pull/branch/stash 명령은 무엇이며 어떨 때 이용하나요? 그리고 어떻게 사용하나요?
- clone:원격저장소의 파일들을 내 컴퓨터에 복제하는 명령어
  add: 커밋하기 전에 변경된 사항들을 staging area에 추가하는 명령어
  commit: staging area에 add된 파일을 local repository에 추가하는 명령어
  push: commit된 local repository에 있는 파일을 원격 서버에 전송하는 명령어
  pull: 원격에 저장된 git 파일 변경내용을 현재 위치의 브랜치로 합치는 명령어
  branch: 새 branch를 생성하는 명령어
  stash: 작업했던 모든 내용을 임시저장하는 명령어

* git의 Object, Commit, Head, Branch, Tag는 어떤 개념일까요? git 시스템은 프로젝트의 히스토리를 어떻게 저장할까요?
- object: git이 파일을 관리할 때 만드는 파일들. blob, tree, commit, tag 4개의 파일로 구성되어있다.
  commit: git commit을 할때 생성되는 파일. author, committer, message를 기록한다.
  head: 커밋을 가르키는 포인터
  branch: 작업 tree를 나타냄
  tag: 특정 커밋에 tag를 달아주는 역할

* 리모트 git 저장소에 원하지 않는 파일이 올라갔을 때 이를 되돌리려면 어떻게 해야 할까요?
- git reset 명령어를 이용해 커밋을 취소한다.

## Quest
* GitHub에 가입한 뒤, [이 커리큘럼의 GitHub 저장소](https://github.com/KnowRe-Dev/WebDevCurriculum)의 우상단의 Fork 버튼을 눌러 자신의 저장소에 복사해 둡니다.
* Windows의 경우 같이 설치된 git shell을, MacOSX의 경우 터미널을 실행시켜 커맨드라인에 들어간 뒤, 명령어를 이용하여 복사한 저장소를 clone합니다.
  * 앞으로의 git 작업은 되도록 커맨드라인을 통해 하는 것을 권장합니다.
* 이 문서가 있는 폴더 바로 밑에 있는 sandbox 폴더에 파일을 추가한 후 커밋해 보기도 하고, 파일을 삭제해 보기도 하고, 수정해 보기도 하면서 각각의 단계에서 커밋했을 때 어떤 것들이 저장되는지를 확인합니다.
* `clone`/`add`/`commit`/`push`/`pull`/`branch`/`stash` 명령을 충분히 익혔다고 생각되면, 자신의 저장소에 이력을 push합니다.

## Advanced
* Mercurial은 어떤 형상관리 시스템일까요? 어떤 장점이 있을까요?
* 실리콘밸리의 테크 대기업들은 어떤 형상관리 시스템을 쓰고 있을까요?
