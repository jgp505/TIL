# Description 
파이썬 데이터 엔지니어링 공부 정리 요약

# TIL Day 01
  
2023년 3월 9일 목요일

## Why study the Python
- 다른 프로그래밍 언어보다 상대적으로 배우기 쉽다.
- 데이터 전처리를 하는 데 적절하다.

## Git vs Github

### git
- 분산 버전 관리 프로그램
- 백업, 복구, 협업을 위해 사용
  
### github
- Git을 사용하는 프로젝트의 협업을 위한 웹호스팅 서비스
- 포트폴리오를 자랑할 수 있는 공간
- 1일 1커밋 하기

## MarkDown
### 제목 붙이기
`#`의 갯수에 따라 제목을 붙일 수 가 있다. 대신, 본문 내용 중 글씨를 크기를 키우고 싶어 `#`을 사용할 경우 문제가 발생되니 제목에만 사용하도록 한다.
```markdown
# 제목1
## 제목2
### 제목3
#### 제목4
##### 제목5
###### 제목6
```
### 목록
`1, 2 ,3`을 넣어 순서가 있는 목록을 생성할 수 있다. 그리고, `-, +, *`을 사용하여 순서가 없는 목록을 작성할 수 있다.

```markdown
# 목록
1. 순서가 있는 목록
2. 순서가 있는 목록
   1. tab을 통해 들여쓰기
   2. tab을 통해 들여쓰기
3. shift + tab을 통해 내어쓰기

- 순서가 없는 목록
- 순서가 없는 목록
  - tab을 통해 들여쓰기
- shift + tab을 통해 내어쓰기
+ 순서가 없는 목록 (+)
```

### 글꼴 
- `*`, `_` : 기울임
- `**`,`__` : 굵게

### CIL (Command Line Interface)
CIL은 터미널을 통해 사용자와 컴퓨터가 상호 작용하는 방식을 뜻한다.

#### 예시
```bash
$ mkdir test

$ touch a.txt

$ ls
$ ls -a

$ cd ..
$ cd test

$ rm a.txt
$ rm -r test
```
## VScode로 Git 연동
1. 터미널을 연다. (Ctrl + `)
2. 화살표를 누르고 Select Default Profile을 클릭한다.
3. Git Bash를 선택한다.
4. 휴지통을 눌러서 터미널을 종료하고, 재시작한다.
   - 휴지통은 Kill Terminal 로써, 터미널 자체를 아예 종료한다.
   - 닫기는 Close Terminal 로써, 터미널을 종료하지 않고 창만 보이지 않게 만든다.
5. 기본 터미널이 Git Bash로 열리는지 확인한다.


# TIL Day 02 

2023년 3월 10일 금요일

## 오늘 공부 내용
- Profile 작성
- `clone`, `pull`, `.gitignore`
- Branch 만들고 합병하기
- Pullrequest 와 upstream

## Profile 작성
1. 홈폴더에서 `username` 폴더를 생성합니다.
2. `username` 폴더를 local 저장소로 초기화합니다.
3. README.md 파일 만들어서 자기소개 작성합니다.
4. 커밋하여, 변경사항을 기록합니다.
5. github 에서도 본인의 Github `username`으로 저장소를 생성합니다.
6. 원격 저장소를 로컬 저장소와 연결합니다.
7. 변경 사항을 push 합니다.
8. 본인 Github 프로필 사이트 접속해서 확인해 봅니다.

### 예시
[예시1](https://github.com/pifafu)<br>
[예시2](https://github.com/katmeister)<br>
[예시3](https://github.com/jlengstorfhttps://github.com/katmeister)

### 기타 도구
[Github Readme Stats](https://github.com/anuraghazra/github-readme-stats) <br>
[Badge 4 Github Profile](https://github.com/alexandresanlim/Badges4-README.md-Profile)

## Clone & Pull

### (1) git clone

- 원격 저장소의 커밋 내역을 모두 가져와서, 로컬 저장소를 생성하는 명령어
- clone은 `"복제"`라는 뜻으로, `git clone` 명령어를 사용하면 원격 저장소를 통째로 복제해서 내 컴퓨터에 옮길 수 있습니다.
- `git clone <원격 저장소 주소>`의 형태로 작성합니다.

```bash
$ git clone https://github.com/edukyle/TIL.git
Cloning into 'TIL'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 3 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.
```
### (2) git pull

- 원격 저장소의 변경 사항을 가져와서, 로컬 저장소를 업데이트하는 명령어
- 로컬 저장소와 원격 저장소의 내용이 완전 일치하면 git pull을 해도 변화가 일어나지 않습니다.
- `git pull <저장소 이름> <브랜치 이름>`의 형태로 작성합니다.
  
```bash
$ git pull origin master
From https://github.com/edukyle/git-practice
 * branch            master     -> FETCH_HEAD
Updating 6570ecb..56809a9
Fast-forward
 README.md | 1 +
 1 file changed, 1 insertion(+)


[풀이]
git 명령어를 사용할건데, origin이라는 원격 저장소의 master 브랜치의 내용을 가져온다(pull).
```
## .gitignore
특정 파일 혹은 폴더에 대해 Git이 버전 관리를 하지 못하도록 지정하는 것

### (1) .gitignore에 작성하는 목록

- 민감한 개인 정보가 담긴 파일 (전화번호, 계좌번호, 각종 비밀번호, API KEY 등)
- OS(운영체제)에서 활용되는 파일
- IDE(통합 개발 환경 - pycharm) 혹은 Text editor(vscode) 등에서 활용되는 파일
    - 예) pycharm -> .idea/
- 개발 언어(python) 혹은 프레임워크(django)에서 사용되는 파일

### (2) .gitignore 작성 시 주의 사항

- 반드시 이름을 `.gitignore`로 작성합니다. 앞의 점(.)은 숨김 파일이라는 뜻입니다.
- `.gitignore` 파일은 `.git` 폴더와 동일한 위치에 생성합니다.
- **제외 하고 싶은 파일은 반드시 `git add` 전에 `.gitignore`에 작성합니다.**

### (3) .gitignore 쉽게 작성하기

.gitignore의 내용을 쉽게 작성할 수 있도록 도와주는 두 개의 사이트를 소개합니다.
자신의 개발 환경에 맞는 것을 찾아서 `전체 복사, 붙여넣기`를 하면 됩니다.
[Toptal](https://www.toptal.com/developers/gitignore/)


## Branch

- Branch는 `나뭇가지`라는 뜻의 영어 단어입니다.
- 즉 `브랜치`란 나뭇가지처럼 여러 갈래로 작업 공간을 나누어 **독립적으로 작업**할 수 있도록 도와주는 Git의 도구입니다.
- **장점**
    1. 브랜치는 독립 공간을 형성하기 때문에 원본(master)에 대해 안전합니다.
    2. 하나의 작업은 하나의 브랜치로 나누어 진행되므로 체계적인 개발이 가능합니다.
    3. 특히나 Git은 브랜치를 만드는 속도가 굉장히 빠르고, 용량도 적게 듭니다.
- **그래도 브랜치 꼭 써야하나요?**
    1. 일단 master 브랜치는 상용을 의미합니다. 그래서 언제든 세상에 공개되어 있습니다.
    2. 만약 상용에 에러가 있어서 고쳐야 한다면 어떻게 해야할까요?
    3. 고객들이 사용하고 있는데, 함부로 버전을 되돌리거나 삭제할 수 있을까요?
    4. 따라서 브랜치를 통해 별도의 작업 공간을 만들고, 그곳에서 되돌리거나 삭제를 합니다.
    5. 브랜치는 완전하게 독립이 되어있어서 어떤 작업을 해도 master에는 영향을 끼치지 못하죠.
    6. 그리고 이후에 에러를 해결했다면? 그 내용을 master에 반영할 수도 있습니다!
    7. 이러한 이유 때문에 Git에서 브랜치는 정말 강력한 기능 중의 하나라고 할 수 있습니다.

### 예시
```bash
# 브랜치 목록 확인
$ git branch

# 원격 저장소의 브랜치 목록 확인
$ git branch -r

# 새로운 브랜치 생성
$ git branch <브랜치 이름>

# 특정 커밋 기준으로 브랜치 생성
$ git branch <브랜치 이름> <커밋 ID>

# 특정 브랜치 삭제
$ git branch -d <브랜치 이름> # 병합된 브랜치만 삭제 가능
$ git branch -D <브랜치 이름> # (주의) 강제 삭제 (병합되지 않은 브랜치도 삭제 가능)
```

### (3) git switch

현재 브랜치에서 다른 브랜치로 `HEAD`를 이동시키는 명령어
`HEAD`란 현재 브랜치를 가리키는 포인터를 의미합니다.

```bash
# 다른 브랜치로 이동
$ git switch <다른 브랜치 이름>

# 브랜치를 새로 생성과 동시에 이동
$ git switch -c <브랜치 이름>

# 특정 커밋 기준으로 브랜치 생성과 동시에 이동
$ git switch -c <브랜치 이름> <커밋 ID>
```

### (4) git merge
- 분기된 브랜치들을 하나로 합치는 명령어
- `git merge <합칠 브랜치 이름>`의 형태로 사용합니다.
- **Merge하기 전에 일단 다른 브랜치를 합치려고 하는, 즉 메인 브랜치로 switch 해야합니다.**

```bash
# 1. 현재 branch1과 branch2가 있고, HEAD가 가리키는 곳은 branch1 입니다.
$ git branch
* branch1
  branch2

# 2. branch2를 branch1에 합치려면?
$ git merge branch2

# 3. branch1을 branch2에 합치려면?
$ git switch branch2
$ git merge branch1
```
### (5) Merge의 세 종류
1. **Fast-Forward**
    - 브랜치를 병합할 때 마치 `빨리감기`처럼 브랜치가 가리키는 커밋을 앞으로 이동시키는 것
2. **3-Way Merge**
   - 브랜치를 병합할 때 `각 브랜치의 커밋 두개와 공통 조상 하나`를 사용하여 병합하는 것
   - 두 브랜치에서 `다른 파일` 혹은 `같은 파일의 다른 부분`을 수정했을 때 가능합니다.
3. **Merge Conflict**
    - 병합하는 두 브랜치에서 `같은 파일의 같은 부분`을 수정한 경우, Git이 어느 브랜치의 내용으로 작성해야 하는지 판단하지 못해서 발생하는 충돌(Conflict) 현상
    - 결국은 사용자가 직접 내용을 선택해서 Conflict를 해결해야 합니다.