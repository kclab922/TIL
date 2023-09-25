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

- `git status`
    - 현재 git으로 관리되고 있는 파일/폴더의 상태를 출력
## 코드 수정하고 저장소에 저장하기

- `add`

