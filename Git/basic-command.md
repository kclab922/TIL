# basic command
> git 기본 문법 정리

## 초기 설정
- git을 설치 후 한 번만 실행
```bash
git config --global user.email <이메일>
git config --global user.name <이름>
```
- gitignore
    - git으로 관리하는 경우, 폴더 만들자마자 바로 
    1. VScode 실행하여 `.gitignore` 파일 만들기
    2. `gitignore.io` 사이트 접속
    3. `windows`, `mac`, `vscode`로 검색
    4. 복사
    5. `.gitignore` 파일에 붙여넣기
    6. (기타) git에 업로드 하지 않을 파일의 파일명 적기

## git 저장소 만들기

- `git init`
    - `.git directory`를 생성해주는 명령어
    - 관리하고 싶은 최상위 위치에서 실행 (git init을 한 위치를 기준으로 하위파일을 전부 저장하므로, 어디서 git init을 하는지 주의)


## git 상태 체크 

- `status`
    - `git status`: 현재 git으로 관리되고 있는 파일/폴더의 상태를 출력
    - `git log`: 커밋 내역


## 코드 수정하고 저장소에 저장하기

- `add` ★
    - `git add <파일/폴더이름>` 
    - `working directory`에서 `staging area`로 추가
    - 모든 파일, 폴더를 추가하기 위해 일반적으로 아래의 코드를 사용
        - `git add .`

- `commit` ★
    - `git commit -m "메시지"`
    - `staging area`에 올라간 파일들의 스냅샷을 찍어서 `.git directory`에 저장
    - 일반적으로 `-m` 옵션을 넣어 메시지를 추가하여 등록


## 원격저장소에 업로드하기

- `remote add`
    - `git remote add <원격저장소이름> <URL>`
    - 일반적으로 `git remote add origin <URL>` 사용
    - 원격저장소 주소를 origin이라는 이름으로 저장 (한 번만 등록해두면 됨)

- `push` ★
    - `git push <원격저장소이름> <브랜치이름>`
    - 일반적으로 `git push origin main` 사용
    - 원격저장소에 브랜치를 업로드


## 원격저장소에서 다운로드하기

- `pull`
    - `git pull <원격저장소이름> <브랜치이름>`
    - 일반적으로 `git pull origin main` 사용
    - 원격저장소에서 브랜치로 다운로드

- `clone`
    - 다운로드할git접속-초록색Code버튼-URL복사
    - 저장할 폴더에서 마우스오른쪽-Open Git Bash Here클릭-pwd로 위치확인-`git clone <URL>붙여넣기`입력-종료
    - 폴더 들어가서 생성된 파일로 VSCode 열기 

- `fork`
    - 상대방의 원격저장소에 들어가 `Fork`하기

## 코드 공유하기
- 상대방의 원격저장소에 들어가 `Fork`하기
- 만들어진 내 원격저장소에 들어가 `clone`하여 폴더 생성
- 폴더에서 vscode 실행 후 작업
- `add, commit, push`
- 상대방의 원격저장소에 들어가 `Pull Request` 클릭

-- `git stash` - `git stash pop` : 작업하던 것 잠시 보관


    ## vscode에서 파일상태
    - `U`: untrack
    - `A`: add 됨

    
    ## vscode 명령어
    - `git status`
    - `git log`: 전체 커밋 내역
    - `git log -n`: 최근 n개 커밋만 보기  
    - `git log--oneline` : 각 커밋을 한 줄 요약해서 전체 커밋 내역 
    - `git restore README.md`: 수정 전 저장해둔 커밋상태로 돌아가는 명령어
    - `git commit --amend` : 커밋한 것을 수정할 때 사용 (ex.커밋메시지 변경시) 
                            > 이미 push까지 했다면 사용 불가한 명령어

    ## 브랜치 쓰는법
    1. 작업 전 브랜치를 만든다.   
    2. 브랜치에서 개발을 하고, 완료되면 커밋한다.
    3. 개발이 완료되면 원하는 브랜치에 병합시킨다. 
    - 로컬: master에 병합
    - GitHub으로 pull request를 보내고, merge를 GitHub에서 하는 작업흐름
    - 명령어
        - 브렌치 만들기 `git checkout -b <브렌치 이름>`
        - 브렌치로 이동 `git checkout <브렌치 이름>`
        - 브렌치 병합: `git merge <브렌치 이름>`
        - 브렌치 삭제 `git barnch -d <브렌치 이름>`

    ## `commit`은 새로운 버전을 만드는 것이므로 중요.
    - `restore`: 작업중인 내용 날리고 최신 커밋된 내용으로 돌아가기
    - `reset`: 커밋 버전 자체를 삭제 (커밋을 잘못 썼을 때). 삭제 후 되돌리기 어려우므로 주의요망.
    - `revert`: 커밋을 되돌림. 되돌렸다는 커밋을 새로 생성


## git 으로 협업하기
1. 조장: organization 생성 및 조원 초대
2. 조장: repository 생성하고 기본 폴더구조 만든 후 add commit push / 조원들 role owner로 변경
3. 조원: code 에서 git clone
4. 다같이
- clone한 폴더에서 vscode 열기
- 브랜치 생성 및 스위치: `git branch -c <내 저장소명>` >> `git switch <내 저장소명>`
5. 작업루틴
- github 최신데이터 가져오기: `git switch master` >> `git pull origin master` >> `git switch <내 저장소명>` >> `git merge master`
- 작업 진행
- 작업 후 `git switch <내 저장소명>` >> `add/commit/push`
- github 창에서 pull request 및 merge 
