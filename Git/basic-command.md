# basic command
> git 기본 문법 정리

## 초기 설정
- git을 설치 후 한 번만 실행
```bash
git config --global user.email <이메일>
git config --global user.name <이름>
```


## git 저장소 만들기

- `git init`
    - `.git directory`를 생성해주는 명령어
    - 관리하고 싶은 최상위 위치에서 실행 (git init을 한 위치를 기준으로 하위파일을 전부 저장하므로, 어디서 git init을 하는지 주의)


## git 상태 체크 

- `status`
    - `git status`
    - 현재 git으로 관리되고 있는 파일/폴더의 상태를 출력


## 코드 수정하고 저장소에 저장하기

- `add`
    - `git add <파일/폴더이름>` 
    - `working directory`에서 `staging area`로 추가
    - 모든 파일, 폴더를 추가하기 위해 일반적으로 아래의 코드를 사용
        - `git add .`

- `commit`
    - `git commit -m "메시지"`
    - `staging area`에 올라간 파일들의 스냅샷을 찍어서 `.git directory`에 저장
    - 일반적으로 `-m` 옵션을 넣어 메시지를 추가하여 등록


## 원격저장소에 업로드하기

- `remote add`
    - `git remote add <원격저장소이름> <URL>`
    - 일반적으로 `git remote add origin <URL>`
    - 원격저장소 주소를 origin이라는 이름으로 저장 (한 번만 등록해두면 됨)

- `push`
    - `git push <원격저장소이름> <브랜치이름>`
    - 일반적으로 `git push origin main`
    - 원격저장소에 브랜치를 업로드
