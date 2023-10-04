# Jupyter_Lab


## 설치/실행/종료
- 구글에 jupyter 검색 - jupyterlab 설치 
- 폴더 생성 - 폴더 내 git bash 창에 pip install jupyterlab 입력 
- jupyter lab 입력하여 제대로 설치됐는지 확인 및 실행
- 'notebook' 만들기
- ctrl+C + ctrl+X (종료 안될 시 작업관리자에서 jupyter 종료)
- 실행중에 terminal 끄면 안 됨 ★


## 동작
- ctrl + enter  : 지금 셀 실행
- shift + enter : 지금 셀 실행 + 아래로 이동
- alt + enter   : 지금 셀 실행+ 아래에 새로운 셀 추가
- enter : 셀 활성화 
- esc : 셀 이동 활성화 
- drag and drop : 셀 줄 이동 가능
- 이전 코드 전체 비활성화 : 상단 탭 - `Kernel`- `Restart Kernel and Clear Outputs of All Cells`


## 1. 변수

- 변수이름 `=` 값
    ```python
    a = 10
    a
    ```
    ```python
    10
    ```
- 변수 이름은 어떤 이름이든 상관 없음.
    - 그러나 가능하면 '영어, 숫자, _'를 이용하여 선언
- 키워드는 사용불가 
    - 사용불가한 키워드리스트 확인방법
        ```python
        import keyword
        keyword.kwlist
        ```

    ### 1.1 Number
    - int (정수)
        ```python
        a = 10
        type(a)
        ```
        ```python
        int
        ```
    - float (소수)
        ```python
        b = 1.1
        type(b)
        ```
        ```python
        float
        ```
    - complex (실수+허수)
        ```python
        c = 1 - 4j
        type(c)
        ```
        ```python
        complex
        ```

    ### 1.2 Boolean
    - `True` or `False`
    - `True = 1` / `False = 0`
    ```python
    a = True
    type(a)
    ```
    ```python
    bool
    ```
    
    ### 1.3 None
    ```python
    type(a)
    ```
    ```python
    NoneType
    ```
    - = null (?)
    ```python
    a = None
    a
    ```
    ```python
    (no reaction) 
    ```

    ### 1.4 String
    - 문자열은 `'`, `"`를 이용하여 표현
    - 이때 시작/끝 따옴표는 같아야 함
    - 둘 중 하나를 선택해 통일성 있게 사용해야 함
    ```python
    a = 'hello'
    type(a)
    ```
    ```python
    str
    ```
    - 
    - 

    ```python
    age = input()
        (input box) 11
    ```
    ```python
    age
    ```
    ```
    11
    ```





    
    #### string interpolation
    1. 
    2.
    3.



## 2. 연산자
### 2.1 산술연산자
### 2.2 비교연산자
### 2.3 논리연산자
### 2.4 복합연산자
### 2.5 기타연산자

## 3. 형변환
### 3.1 암시적 형변환(자동으로 알아서 바뀜)
### 3.2 

## 4. 시퀀스(sequence) 자료형
### 4.1 List
### 4.2 Tuple
### 4.3 range
### 4.4 string
### 4.5 시퀀스에서 사용 가능한 연산/함수

## 5. 시퀀스(sequence) 데이터가 아닌 자료구조
### 5.1 set
