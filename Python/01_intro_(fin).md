# Python_intro

# 목차
1. 변수 (데이터 타입)
    1. Number
    2. Boolean
    3. None
    4. String
2. 연산자
    1. 산술연산자
    2. 비교연산자
    3. 논리연산자
    4. 복합연산자
    5. 기타연산자
    6. 연산자 우선순위
3. 형변환
    1. 암시적 형변환
    2. 명시적 형변환
4. 자료구조(1): 시퀀스(sequence) 자료형
    1. List(배열)
    2. Tuple
    3. Range
    4. String
    5. 시퀀스에서 사용 가능한 연산/함수
5. 자료구조(2): 시퀀스가 아닌 자료형
    1. set
    2. dictionary


## 1. 변수 (데이터 타입)

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
        ```
        int
        ```
    - float (소수)
        ```python
        b = 1.1
        type(b)
        ```
        ```
        float
        ```
    - complex (실수+허수)
        ```python
        c = 1 - 4j
        type(c)
        ```
        ```
        complex
        ```

    ### 1.2 Boolean
    - `True` or `False`
    - `True = 1` / `False = 0`
        ```python
        a = True
        type(a)
        ```
        ```
        bool
        ```
        ```python
        a = True
        a
        ```
        ```
        True
        ```
    
    ### 1.3 None
    ```python
    type(a)
    ```
    ```python
    NoneType
    ```
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
        ```
        str
        ```

    - input
        ```python
        age = input()
            (input box) 11
        age
        ```
        ```python
        11
        ```

    - using `quotation marks`
        1. listing
            ```python
            print('one', 'two', 'three')
            ```
            ```
            one two three
            ```
        2. `"` + `'`
            ```python
            print("Hi. I am 'Haeun'.")
            ```
            ```
            Hi. I am 'Haeun'.
            ```
        3. `'`+ `\'`
            ```python
            print('Hi. I am \'Haeun\'.')
            ```
            ```
            Hi. I am 'Haeun'.
            ```
        4. `'` + `'` (error)
            ```python
            print('Hi. I am 'Haeun'.')
            ```
            ```
            Cell In[26], line 1
                print('Hi. I am 'Haeun'.')
                        ^
            SyntaxError: invalid syntax. Perhaps you forgot a comma?
            ```
    
    - QnA ???
        ```python
        a = '''
        여기는 \n문자열입니다.'
        여러\t줄을 작성 할 수 있어요.
        '''
        ```

    - string interpolation
        ```python
        age = 100
        ```
        1. %-formatting
            ```python
            print('홍길동은 %살입니다.' % age)
            ```
            ```
            홍길동은 100살입니다.
            ```
        2. str.format()
            ```python
            print('홍길동은 {}살입니다.'.format(age))
            ```
            ```
            홍길동은 100살입니다.
            ```
        3. f-string
            ```python
            print(f'홍길동은 {age}살입니다.')
            ```


## 2. 연산자

### 2.1 산술연산자
```python
a = 2
b = 3
```
```python
print(a + b) 
print(a - b)
print(a * b)
print(a / b)
print(a ** b) #지수
print(a // b) #몫
print(a % b)  #나머지
print(divmod(a,b)) #몫+나머지
```
```
5
-1
6
0.6666666666666666
8
0
2
(0, 2)
```

### 2.2 비교연산자

1. comparing numbers
```python
a = 5
b = 10
```
```python
print(a > b)
print(a < b)
print(a >= b)
print(a <= b)
print(a == b) #양편이 같은지 비교
print(a != b) #양편이 다른지 비교
```
```
False
True
False
True
False
True
```
2. comparing strings
```python
print('hi' == 'hi')
print('hi' != 'hi')``
```
```
True
False
```

### 2.3 논리연산자


1. and
- 양쪽 모두 참일 때만 참 (양편 중 하나라도 거짓이면 거짓)
```python
print(True and True)
print(True and False)
print(False and True)
print(False and False)
```
```
True
False
False
False
```
- 단축평가
    - 0 = F / 1,2,3,4,... = T
```python
print(3 and 5) #뒤의 값
print(3 and 0) #뒤의 값
print(0 and 5) #앞의 값
print(0 and 0) #앞의 값
```
```
5
0
0
0
```

2. or
- 양쪽 모두 거짓일 때만 거짓 (양편 중 하나라도 참이면 참)
```python
print(True or True)
print(True or False)
print(False or True)
print(False or False)
```
```
True
True
True
False
```
- 단축평가
    - 0 = F / 1,2,3,4,... = T
```python
print(3 or 5) #앞의 값
print(3 or 0) #앞의 값
print(0 or 5) #뒤의 값
print(0 or 0) #뒤의 값
print(None or 'index.html') #뒤의 값
print('login.html' or 'index.html') #앞의 값

```
```
3
3
5
0
'index.html'
login.html
```

3. not : 값을 반대로 전환
```python
print(True)
print(not True)
print(False)
print(not False)

a = True
print(not a)
```
```
True
False
False
True
False
```


### 2.4 복합연산자
```python
a = 2
b = 3

#오른쪽 값을 a에 할당하기
a = a + b 
a = a - b
a = a * b
a = a / b
a = a // b
a = a % b
a = a ** b
print(a)
```
```
0.0 
```
- 축약형
```python
a += b
a -= b
a *= b
a /= b
a //= b
a %= b
a **= b
print(a)
```
```
0.0 
```

### 2.5 기타연산자

1. concatenation (글자 연결)
- 글자데이터를 가지고 연산
- 연산자가 연결하는 데이터들은 같은 종류여야 함 (글자끼리, 숫자끼리 등)
```python
a = 'hi'
b = 'hello'
print(a + b)
print(a + 1) #error code
```
```
hihello
TypeError: can only concatenate str (not "int") to str
```

2. containment (포함 확인)
```python
print('a' in 'apple')
print('z' in 'apple')
print(1 in [1, 2, 3])
print(100 in [1, 2, 3])
```
```
True
False
True
False
```

3. is (양쪽 데이터의 위치가 같은지 확인)
```python
# 데이터들의 메모리 주소가 서로 다른 상황
a = 123123
b = 123123
print(a is b) 
# 데이터들의 메모리 주소가 같은 상황 (계산의 용이성을 위해 미리 할당해둔 숫자들이므로)
a = 256
b = 256
print(a is b)
```
```
False
True
```

### 2.6 연산자 우선순위
0. `( )`로 그룹핑한 연산
1. 산술연산자  `**`
2. 산술연산자 `*`, `/`
3. 산술연산자 `+`, `-`
4. 비교연산자 `is`, `in`
5. `not`
6. `and`, `or`


## 3. 형변환

### 3.1 암시적 형변환(자동으로 알아서 바뀜)
```python
a = True
b = False
c = 1

print(a + c)
print(b + c)
```
```
2
1
```

```python
int_num = 3
float_num = 3.3
complex_num = 3 + 3j

print(int_num + float_num)
print(int_num + complex_num)
```
```
6.3
(6+3j)
```

### 3.2 명시적 형변환

1. change to `int`
```python
a = 1
b1 = 'string'
b2 = '100'
c1 = True
c2 = False

print(int(a))
print(int(b1))
print(int(b2))
print(int(c1))
print(int(c2))
```
```
1
ValueError: invalid literal for int() with base 10: 'string'
100
1
0
```

2. change to `str`
```python
a = 1
b = 'string'
c1 = True
c2 = False

print(str(a))
print(str(b))
print(str(c1))
print(str(c2))
```
```
1
string
True
False
```

3. change to `bool`
```python
a1 = 1
a2 = 0
a3 = 100
b1 = 'string'
b2 = not 'string'
c1 = True
c2 = False

print(bool(a1))
print(bool(a2))
print(bool(a3))
print(bool(b1))
print(bool(b2))
print(bool(c1))
print(bool(c2))

print(bool(''))
print(boole([]))

print(bool('apple'))
print(bool([1, 2, 3]))
```
```
True
False
True
True
False
True
False

False
False

True
True
```

- eg 1-1
```python
a = 1
b = '번'
str(a) + b
```
```
1번
```

- eg 1-2 (error)
```python
a = 1
b = '번'
a + b
```
```
TypeError: unsupported operand type(s) for +: 'int' and 'str'
```

- eg 2
```python
age = int(input())
    (inputbox) 11

print(type(age))
```
```
<class 'int'>
```

- eg 3-1
```python
a = '3.3'

type(float(a))
```
```
float
```


- eg 3-2 (error)
```python
a = '3.3'

type(int(a))
```
```
ValueError: invalid literal for int() with base 10: '3.3'
```


## 4. 자료구조(1): 시퀀스(sequence) 자료형
- 시퀀스 : 데이터의 순서대로 나열된 자료구조 (순서대로 나열되어있다는 것은 정렬된 것과는 다르다.)
1. 리스트(list)
2. 튜플(tuple)
3. 레인지(range)
4. 문자열(string)

### 4.1 List
1. 선언 : 변수이름 = [value1, value2, value3]
2. 접근 : 변수이름[index]
- basic form
```python
l = []
print(l)
print(type(l))
```
```
[]
<class 'list'>
```

- 선언
```python
location = ['서울', '대전', '부산']

print(location)
print(type(location))
```
```
['서울', '대전', '부산']
<class 'list'>
```

- 접근_1
```python
location = ['서울', '대전', '부산']

print(location[0])
print(location[1])
print(location[2])

print(location[-3])
print(location[-2])
print(location[-1])
```
```
서울
대전
부산

서울
대전
부산
```

- 접근_2_(error)
```python
location = ['서울', '대전', '부산']

print(location[3])
print(location[-4])
```
```
IndexError: list index out of range
IndexError: list index out of range
```

- 접근_3_(value 수정)
```python
location = ['서울', '대전', '부산']
location[2] = 'LA'

print(location)
```
```
['서울', '대전', '제주']
```


### 4.2 Tuple
1. 선언 : 변수이름 = (value1, value2, value3)
2. 접근 : 변수이름[index]
3. List와 유사하지만 value가 수정불가능(immutable)하다.

- basic form
```python
t = (1, 2, 3)

print(t)
print(type(t))
print(t[2])
```
```
(1, 2, 3)
<class 'tuple'>
3
```

- eg_1_(error: occurring because tuple is immutable)
```python
t = (1, 2, 3)
t[2] = 100
```
```
TypeError: 'tuple' object does not support item assignment
```

- eg_2
```python
result = divmod(9, 4)

print(result)
print(type(result))
print(resutl[0])
print(resutl[1])
```
```
(2, 1)
<class 'tuple'>
2
1
```

<!-- QnA : `x, y`는 튜플 형태인데, 결과값이 왜 `(1, 2)`가 아니라 `1 2`와 같은 정수의 단순 나열로 나오나요? -->
- eg_3
```python
x, y = (1, 2)
print(x, y)
```
```
1 2
```

- eg_4
```python
x, y = (1, 2)
x, y = (y, x)
print(x, y)
```
```
2 1
```


### 4.3 range

1. 선언_1 : `range(n)` 0부터 n-1까지의 범위
```python
r = range(5)
print(r)
print(type(r))
```
```
range(0, 5)
<class 'range'>
```

2. 선언_2 : `range(n, m)` n부터 m-1까지의 범위
```python
r = range(0, 5)
print(r)
```
```
range(0, 5)
```

3. 선언_3 : `range(n, m, s)` n부터 m-1까지의 범위 (각 value가 +s 만큼 증가)
```python
r = range(0, 5, 2)
print(r)
```
```
range(0, 5, 2)
```

4. making list
```python
r = range(5, 15, 2)
print(list(r))
```
```
[5, 7, 9, 11, 13]
```

5. 접근
```python
r = range(5, 15, 2)
print(r[1])
```
```
7
```


### 4.4 string
- 기본 데이터 구조 참고


### 4.5 시퀀스에서 사용 가능한 연산/함수
1. indexing
- 형태: [n]
- 의미: n번째 데이터에 접근

```python
my_list = [1, 2, 3, 4, 5]
my_tuple = (11, 22, 33, 44, 55)
my_range = range(1, 10, 2)
my_string = '일이삼사오'

print(my_list[1])
print(my_tuple[1])
print(my_range[1])
print(my_string[1])
```
```
2
22
3
이
```

2. slicing
- 형태: [n:m] or [n:m:s]
- 의미: n번째 이상부터 m번째 미만까지 (s간격으로) 나열

```python
my_list = [1, 2, 3, 4, 5]
my_tuple = (11, 22, 33, 44, 55)
my_range = range(1, 10, 2) 
my_string = '일이삼사오'

print(my_list[1:3])
print(my_tuple[1:3])
print(my_range[1:3]) # QnA
print(my_string[1:3])

print(my_list[1:4:2]) 
print(my_range[2:7:2]) # QnA

print(my_list[ :3]) 
print(my_list[3: ]) 
```
```
[2, 3]
(22, 33)
range(3, 7, 2)
이삼

[2, 4]
range(5, 11, 4)

[1, 2, 3]
[4, 5]
```


3. in
- 어떤 글자가 해당 범위에 들어있는지 확인

```python
my_list = [1, 2, 3, 4, 5]
my_tuple = (11, 22, 33, 44, 55)
my_range = range(1, 10, 2) 
my_string = '일이삼사오'

print(11 in my_list)
print(11 in my_tuple)
print(1 in my_range)
print('일' in my_string)
```
```
False
True
True
True
```

4. not in
- 어떤 글자가 해당 범위에 들어있지 '않은지' 확인
```python
my_list = [1, 2, 3, 4, 5]
my_tuple = (11, 22, 33, 44, 55)
my_range = range(1, 10, 2) 
my_string = '일이삼사오'

print(11 not in my_list)
print(100 not in my_tuple)
print(1 not in my_range)
print('구' not in my_string)
```
```
True
True
False
True
```

5. concatenation (연결)
```python
my_list = [1, 2, 3, 4, 5]
my_tuple = (11, 22, 33, 44, 55)

print(my_list + [6, 7, 8, 9, 10])
print(my_tuple + (66, 77, 88))
```
```
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
(11, 22, 33, 44, 55, 66, 77, 88)
```



6. `*` (반복)
```python
my_list = [1, 2, 3, 4, 5]
my_string = '일이삼사오'

print(my_string * 3)
print(my_list * 3)

print([0] * 3)
print([[0] * 3] * 3)
```
```
일이삼사오일이삼사오일이삼사오
[1, 2, 3, 4, 5, 1, 2, 3, 4, 5, 1, 2, 3, 4, 5]
[0, 0, 0]
[[0, 0, 0], [0, 0, 0], [0, 0, 0]]

```

7. len (길이: 전체 데이터의 개수)
```python
my_list = [1, 2, 3, 4, 5]

len(my_list)
```
```
5
```


8. count (특정 데이터의 개수)
```python
my_list = [1, 2, 3, 4, 5]

my_list.count(1)
```
```
1
```


9. min
```python
my_tuple = (11, 22, 33, 44, 55)

min(my_tuple)
```
```
11
```


10. max
```python
my_range = range(1, 10, 2) 

max(my_range)
```
```
9
```


## 5. 자료구조(2): 시퀀스(sequence) 데이터가 아닌 자료구조

### 5.1 set

- 선언: 변수이름 = {value1, value2}
- 수학의 집합과 동일하게 처리 
```python
my_set_a = {1, 2, 3, 4, 5}
my_set_b = {1, 3, 5, 7, 9}

print(my_set_a - my_set_b) # 차집합
print(my_set_a | my_set_b) # 합집합
print(my_set_a & my_set_b) # 교집합
```
```
{2, 4}
{1, 2, 3, 4, 5, 7, 9}
{1, 3, 5}
```

- 중복되는 값이 없음
```python
my_list = [1, 2, 3, 1, 4, 1, 2, 3, 5, 2]
print(set(my_list))
```
```
[1, 2, 3, 4, 5]
```


### 5.2 dictionary
- 선언 : 변수이름 = {key1: value1, key2: value2, key3: value3}

- 접근 : 변수이름[key]
```python
my_dict = {'서울': '02', '경기': '031'}
my_dict['서울']
```
```
'02'
```

- dictionary는 key와 value의 쌍
    1. key: immutable한 모든 값을 사용 가능. (불변값인 string, integer, ..)
    2. value: 모든 데이터 사용 가능. (list, dict도 가능)

```python
dict_a = {
    'name': 'changhee',
    'age': 10,
    'location': 'seoul',
    'numbers': [1, 2, 3, 4, 5],
    'friends': {
        'a': 10,
        'b': 11,
    },
}

print(dict_a['age'])
print(dict_a['numbers'][3])
print(dict_a['friends']['b'])

print(dict_a.keys())
print(dict_a.values())
```
```
10
4
11

dict_keys(['name', 'age', 'location', 'numbers', 'friends'])
dict_values(['changhee', 10, 'seoul', [1, 2, 3, 4, 5], {'a': 10, 'b': 11}])
```
