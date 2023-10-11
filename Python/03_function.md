# 함수


# 목차
0. 함수의 의의 
1. 함수의 선언과 호출
    1. 함수의 선언
    2. 함수의 호출
    3. 함수의 return
2. 함수의 인수 (어떻게 선언하는가)
    1. 위치인수
    2. 기본값
    3. 키워드 인자
    4. 가변 인자 리스트
    5. 정의되지 않은 키워드 인자 처리하기
3. unpacking: dictionary를 인자로 넣기
4. lambda 표현식
5. 타입힌트
6. scope 이름공간
7. recursive 재귀
    1. 피보나치 수열

---

> 단어 사용 규칙
- snake_case
    - 단어와 단어 사이에 _(언더바)
    - `변수`와 `함수`에 사용
- PascalCase
    - 모든 단어들을 시작할 때마다 대문자로 
    - `class` 에 사용
---


## 0. 함수의 의의
```python
height = 10
width = 20

height2 = 50
width2 = 100

area = height * width
perimeter = (height + width) * 2
print(f'직사각형의 면적은 {area}, 둘레는 {perimeter}입니다.')

area2 = height2 * width2
perimeter2 = (height2 + width2) * 2
print(f'직사각형의 면적은 {area2}, 둘레는 {perimeter2}입니다.')

...
```
```
직사각형의 면적은 200, 둘레는 60입니다.
직사각형의 면적은 5000, 둘레는 300입니다.
```

- 사각형의 개수가 계속 늘어난다면? 
위의 함수를 반복해서 쓰기 불편할 것. >> 함수 필요.

- dry: 
코드를 한 번 작업을 해놓고 그것을 계속해서 사용 가능하면
코드를 반복해서 쓰지 말라는 뜻. 




## 1. 함수의 선언과 호출
- 선언: `y=x+1`이라는 함수를 만드는 것
- 호출: x에 1을 넣어 2를 도출하는 것

### 1. 함수의 선언
- 형식
```python
def fun_name(parameter1, parameter2):
    code1
    code2
    ...
    return value
```
- eg
```python
def rectangle(height, width):
    area = height * width
    perimeter = (height + width) * 2
    print(area, perimeter)
```
```
(none)
```
- 함수 이름짓기
    - snake_case, PascalCase 사용
    - 다음 목록은 파이썬이 이미 만들어놓은 함수이므로, 해당 이름으로 함수를 만들지 않도록 유의!
    ```python
    dir(__builtins__)
    ```
    ```
    ['ArithmeticError',
    'AssertionError',
    'AttributeError',
    'BaseException',
    'BaseExceptionGroup',
    'BlockingIOError',
    'BrokenPipeError',
    'BufferError',
    'BytesWarning',
    'ChildProcessError',
    'ConnectionAbortedError',
    'ConnectionError',
    'ConnectionRefusedError',
    'ConnectionResetError',
    'DeprecationWarning',
    'EOFError',
    'Ellipsis',
    'EncodingWarning',
    'EnvironmentError',
    'Exception',
    'ExceptionGroup',
    'False',
    'FileExistsError',
    'FileNotFoundError',
    'FloatingPointError',
    'FutureWarning',
    'GeneratorExit',
    'IOError',
    'ImportError',
    'ImportWarning',
    'IndentationError',
    'IndexError',
    'InterruptedError',
    'IsADirectoryError',
    'KeyError',
    'KeyboardInterrupt',
    'LookupError',
    'MemoryError',
    'ModuleNotFoundError',
    'NameError',
    'None',
    'NotADirectoryError',
    'NotImplemented',
    'NotImplementedError',
    'OSError',
    'OverflowError',
    'PendingDeprecationWarning',
    'PermissionError',
    'ProcessLookupError',
    'RecursionError',
    'ReferenceError',
    'ResourceWarning',
    'RuntimeError',
    'RuntimeWarning',
    'StopAsyncIteration',
    'StopIteration',
    'SyntaxError',
    'SyntaxWarning',
    'SystemError',
    'SystemExit',
    'TabError',
    'TimeoutError',
    'True',
    'TypeError',
    'UnboundLocalError',
    'UnicodeDecodeError',
    'UnicodeEncodeError',
    'UnicodeError',
    'UnicodeTranslateError',
    'UnicodeWarning',
    'UserWarning',
    'ValueError',
    'Warning',
    'WindowsError',
    'ZeroDivisionError',
    '__IPYTHON__',
    '__build_class__',
    '__debug__',
    '__doc__',
    '__import__',
    '__loader__',
    '__name__',
    '__package__',
    '__spec__',
    'abs',
    'aiter',
    'all',
    'anext',
    'any',
    'ascii',
    'bin',
    'bool',
    'breakpoint',
    'bytearray',
    'bytes',
    'callable',
    'chr',
    'classmethod',
    'compile',
    'complex',
    'copyright',
    'credits',
    'delattr',
    'dict',
    'dir',
    'display',
    'divmod',
    'enumerate',
    'eval',
    'exec',
    'execfile',
    'filter',
    'float',
    'format',
    'frozenset',
    'get_ipython',
    'getattr',
    'globals',
    'hasattr',
    'hash',
    'help',
    'hex',
    'id',
    'input',
    'int',
    'isinstance',
    'issubclass',
    'iter',
    'len',
    'license',
    'list',
    'locals',
    'map',
    'max',
    'memoryview',
    'min',
    'next',
    'object',
    'oct',
    'open',
    'ord',
    'pow',
    'print',
    'property',
    'range',
    'repr',
    'reversed',
    'round',
    'runfile',
    'set',
    'setattr',
    'slice',
    'sorted',
    'staticmethod',
    'str',
    'sum',
    'super',
    'tuple',
    'type',
    'vars',
    'zip']
    ```
- 빌트인 함수와 똑같이 기능하는 함수 만들기
```python
# 빌트인 함수
max(1, 3, 5, 6)

# 직접 만든 함수

```

### 2. 함수의 호출
- 형식
```python
func_name(parameter1, parameter2)
```
- eg
```python
rectangle(100, 50) 
rectangle(10, 20)
rectangle(30, 90)
```
```
5000 300
200 60
2700 240
```

### 3. 함수의 return












## 2. 함수의 인수 (어떻게 선언하는가)
### 1. 위치인수
### 2. 기본값
### 3. 키워드 인자
### 4. 가변 인자 리스트
### 5. 정의되지 않은 키워드 인자 처리하기


## 3. unpacking: dictionary를 인자로 넣기

## 4. lambda 표현식

## 5. 타입힌트

## 6. scope 이름공간

## 7. recursive 재귀
### 1. 피보나치 수열
