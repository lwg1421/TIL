# git & github


## **GIT 기초 사용법**

### 파일 추가
- touch
  - touch practice.txt 처럼 작성하여 파일 추가가 가능
  

### GIT 코드 작성 순서
1. git init 
  - 처음 한번만 작성
  - 같은 폴더에 절대 두번 사용하면 안됨
2. git add 파일명
  - git add day1.txt
  - git add practice.md 등으로 작성하면 됨
3. git commit -m "설명작성"
  - 쌍따옴표안에 설명을 작성하여주면 됨
- **파일에 내용을 추가한 후 add와 commit을 진행할 때에는 무조건 먼저 파일을 저장해 준 후 진행해야함**
  
### 상태 확인  
- status
  - git status라고 작성하여 확인 가능
  - Working Directory와 Staging Area에 있는 파일의 현재 상태를 알려주는 명령어
  - 어떤 작업을 시행하기 전에 수시로 status를 확인하면 좋습니다.

### 기록 확인
- log
  - git log로 작성하여 확인 가능
  - 커밋의 내역(ID, 작성자, 시간, 메세지 등)을 조회할 수 있는 명령어
  



## **GIT HUB 기초**

### 원격 저장소
>여태 까지는 내 컴퓨터라는 한정된 공간에 있는 로컬 저장소에서만 버전 관리를 진행했습니다.
이제는 Github의 원격 저장소를 이용해 내 컴퓨터의 로컬 저장소를 다른 사람과 공유해봅시다.
Git의 주요 목적 중 하나인 협업을 위해 로컬 저장소와 원격 저장소의 연동 방법을 학습합니다.

### Github에서 원격 저장소 생성
- GitHub 페이지 화면 오른쪽 상단 더하기(+) 버튼을 누르고 New repository를 클릭합니다.
- Repository name을 설정하고 확인 하면 됩니다. (나머지는 건드리지 않아도 됨.)

### 로컬 저장소와 원격 저장소 연결
1. 원격 저장소가 잘 생성되었는지 확인 후, 저장소의 주소를 복사합니다.
2. 기존에 실습 때 만들었던 홈 디렉토리의 TIL 폴더로 가서 vscode를 엽니다.
3. git init을 통해 TIL 폴더를 로컬 저장소로 만들어줍니다.
4. **git remote**
  >로컬 저장소에 원격 저장소를 `등록, 조회, 삭제`할 수 있는 명령어
   -  **등록**
    
    `git remote add <이름> <주소>` 형식으로 작성합니다.
    
    $ git remote add origin https://github.com/edukyle/TIL.git
    [풀이]
    git 명령어를 작성할건데, remote(원격 저장소)에 add(추가) 한다.
    origin이라는 이름으로 https://github.com/edukyle/TIL.git라는 주소의 원격 저장소를
    

   -  **조회**
    
    `git remote -v` 로 작성합니다.
   - **삭제**
    
    `git remote rm <이름>` 혹은 `git remote remove <이름>` 으로 작성합니다.


### 원격 저장소에 업로드
- 실습 때 작성했던 TIL 파일을 Github 원격 저장소에 업로드 해보겠습니다.
- 정확히 말하면, 파일을 업로드하는 게 아니라 커밋을 업로드 하는 것입니다!
- 따라서 먼저 로컬 저장소에서 커밋을 생성해야 원격 저장소에 업로드 할 수 있습니다.
- **git push**
- 로컬 저장소의 커밋을 원격 저장소에 업로드하는 명령어
- git push <저장소 이름> <브랜치 이름> 형식으로 작성합니다.
- -u 옵션을 사용하면, 두 번째 커밋부터는 저장소 이름, 브랜치 이름을 생략 가능합니다.

```bash
$ git push origin master

[풀이]
git 명령어를 사용할건데, origin이라는 이름의 원격 저장소의 master 브랜치에 push 한다.

------------------------------------------------

$ git push -u origin master
이후에는 $ git push 라고만 작성해도 push가 됩니다.
```
