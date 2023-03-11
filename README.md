# task

## 과제방에 repo 주소로 업로드

1. task repository 포크로 본인 repository에 복사
2. 내려 받기해서 해당 README.md 문서 수정
3. 오늘까지 배운 git 내용 마크다운 형식으로 __잘__ 정리
  _markdown-cheetseat 참고_
4. 본인 repository에 업로드
5. 로컬 저장소 내용도 캡쳐해서 함께 업로드

이 아래로 내용 작성
-

## 깃(Git)

__깃은 개발자가 코드를 저장하고 관리할 수 있는 버전 관리 시스템__

    - 여러 명의 사용자들 간에 해당 파일작업을 조율하기 위한 버전관리를 위한 기록 저장소이다.
    - 로컬저장소와 온라인저장소를 동기화하여 사용하기때문에 장소의 구애를 받지 않고 파일작업이 가능하다.
    - 파일의 변경사항을 추적하기 위하여 파일수정시 메세지 작성, 저장관리가 매우 중요하다.
    - 파일작업시 기록(commit)을 남기는데 기록은 고유번호가 남기때문에 원하는 순간으로 돌아갔다 올 수 있다.
    - 메인 파일을 두고 브랜치를 만들어 각각 기록하고 합치고 삭제하는 등의 작업이 가능하다.
    - 깃은 파일을 생성하는 프로그램이 아니기 때문에 파일은 외부에서 만들어서 가져와야 한다.




_깃을 아주 잘 설명해주는 이미지:_

![git_image](https://git-scm.com/images/branching-illustration@2x.png)


## 깃허브(Github)

__온라인 상에서 협업을 통해 버전 관리를 할 수 있게 해주는 대표적인 깃 호스팅 업체__

    - Bitbucket, GitLab 등의 호스팅 업체도 있음
    - 현재 사용하는 깃허브 프로그램은 CLI 방식(명령어로 사용하는 방식)


## 배쉬(Bash)

__깃에서 사용할 수 있는 리눅스 쉘shell / 명령어__

주요 배쉬 명령어

| 명령어 | 설명 |
| --- | --- |
| ped | 현재 디렉토리 위치 |
| clear | 현재 콘솔창에 입력한 것들과 출력된 것들을 화면에서 지움 |
| repository | 기록공간 |
| branch | 기준 작업 라인 |
| main (=master) | 기본, main branch |
| init | 로컬 저장소에 깃을 만들때 입력, mian 저장소 생성 |
| swich 브랜치명 | 해당 브런치로 이동 |
| branch --list | 생성된 브랜치 리스트 확인 |
| merge 브랜치명 | 기준을 삼는 브랜치로 이동하여 명령어 입력하면  두브랜치 병합 |
| merge -d 브랜치명 | 브랜치가 병합이 되고 난 후 삭제 |
| merge -D 브랜치명 | 브랜치 강제 삭제 |
| cd (change directory) | 디렉토리 변경 |
| cd 폴더명 | 그 폴더로 이동 |
| cd /e | e 드라이브로 바로 이동 |
| cd .. | 현재 디렉토리에서 바로 상위 디렉토리로 변경 |
| cd - | 바로 이전 디렉토리로 이동 |
| ~ | 홈디렉토리 |
| touch 파일명 | 파일 생성 |
| add 파일명 | 생성된 파일을 git에 추가 |
| add . | 파일이 만을 경우 사용 |
| commit | 파일 생성과 작업, 수정시 타임라인에 기록을 남기는 것. (기록마다 소스코드 생성됨) |
| commit -m "파일 설명" | 파일을 설명을 구체적으로 작성해서 기록 |
| commit -am "기록, 수정 내용설명" | 두번째 커밋부터 사용 |
| push -u origin main(master) | 메인(=마스터)에 있던 파일들이 깃허브에 동기화(업로드) |
| status | 현재 상태 확인 |
| log | 모든 커밋 이력 확인 |
| log --oneline | 해당 라인 커밋 이력 확인 |
| git log --oneline --all | 현재까지 작업한 모든 내용을 간략하게 확인 가능 |


## 로컬저장소와 온라인저장소인 깃허브 연결하는 방법

__1) 로컬저장소를 만들고 내 정보등록하기__

로컬저장소와 깃허브의 user.name 과 user.email이 동일하게 설정되어 있어야 한다.
어떤 파일이든 한 번은 커밋되어 있어야하기에 로컬 저장소에 내 정보를 등록해 준다.
내정보가 등록되어 있으면 이 부분은 생략, 수정이 가능하다.


    - 깃허브에 가입하여 user.name 과 user.email 을 만든다.
    - 로컬에 내 정보 등록하기
      git config --global user.name 깃허브유저네임 | git config --global user.name 깃허브유저

로컬에 저장된 정보 확인하기

    - git config --llist
    - 저장된 정보 수정시: 등록과 동일한 방법으로 등록된 정보를 변경
    - 저장된 정보를 삭제시
      git config --unset --global user.name | git config --unset --global user.email

- [x] 메인 로컬저장소에 저장한 내용을 깃허브에 push -u origin main(업로드)해야만 동기화 완성

__2) 로컬저장소와 동기화할 깃허브 저장소 만들기__

    - 깃허브에서 Repositories 탭에서 new 저장소를 만들면 해당 저장소의 링크주소가 생성된다.
    - 파일명이 동일하면 헷갈릴 위험이 줄어든다.

__3) 깃에 저장소의 링크주소를 입력한다.__

    - git remote add origin https://

__4) 팝업으로 뜨는 창의 Sign in with your browser 클릭__

![git_image](https://cafeptthumb-phinf.pstatic.net/MjAyMjA0MDRfMjAw/MDAxNjQ5MDU0MTYyOTUw.2R2WyhYMxDiyODUvlN_MpHKOUkdr-JbUpgnS89lMphkg.EIHJ9Zl0j9mXq9QZnxaROcxxFyLUx78jWSCQECHzBMgg.PNG/github_log.png?type=w1600)

__5) Repositories 옵션에서 전체 선택 후 Authorize 버튼 클릭(안뜨는 경우도 있음)__

![git_image](https://cafeptthumb-phinf.pstatic.net/MjAyMTEwMTFfMTQg/MDAxNjMzOTM0Mjg1ODQ3.JbIbdhK7cPFui3mTSUoFOos0Ke6uz1kvg7IkHJIELggg.oQidvKV-SbikYwpbQfevr53ElLWKecKsDh_tP7lunngg.PNG/06.png?type=w1600)

__6) 깃과 깃허브 동기화여 작업하기__

    - 깃에 명령어를 입력하여 작업 후, 커밋한다.
    - 커밋 후엔 git push -u origin main(업로드)해야만 동기화 완성


## 깃허브에서 로컬저장소로 자료를 다운받을때

다운받고자 하는 저장소에서 Code -> Clone -> HTTPS 에서 링크 복사하여 깃에 입력하면
로컬저장소에 자료가 다운받아진 것을 확인할 수 있다.

- [x] 폴더채로 다운받을때와 내용만 다운받을때 명령어가 다르다.

__1) 폴더채로 다운받을때__

    - git clone URL
    
__2) 만들어진 폴더에 내용만 다운받을때__

    - ​git clone URL .     주소 끝에 한 칸 띄어쓰기 후 마침표(.)

- [x] git 파일이 없어야 가능하다. 

## 깃허브에서 다른 사람의 파일을 나의 저장소로 옮길때

__원하는 파일을 발견하면 그 파일의 Fork를 눌러 나의 저장소로 옮길 수 있다__

- [x] 저장된 파일을 로컬저장소로 다운로드하여 자료를 수정할 수 있다.

## 깃허브 저장소 삭제

1. 해당 repository의 setting으로 들어가 제일 아래의 Delete this repository 선택
2. danger zone에서 Delete this repository

