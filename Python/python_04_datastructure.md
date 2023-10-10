# 목차
1. 메소드
    1. 스트링 메소드
    2. 리스트 메소드
    3. 딕셔너리 메소드
    4. 세트 메소드
2. 기타 함수 
    1. map
    2. filter
    3. zip

# 1. 메소드
- 메소드 = 함수
- 메소드: 객체 안에 들어있는 함수 (vs 함수: 객체 밖에 있는 함수)
- dir(x): 글자/숫자 등인 x가 갖고 있는 기능(메소드)들을 출력
```python
dir('hello') # 이 문자열에서 수행 가능한 메소드의 목록 
```
```
['__add__',
 '__class__',
 '__contains__',
 '__delattr__',
 '__dir__',
 '__doc__',
 '__eq__',
 '__format__',
 '__ge__',
 '__getattribute__',
 '__getitem__',
 '__getnewargs__',
 '__getstate__',
 '__gt__',
 '__hash__',
 '__init__',
 '__init_subclass__',
 '__iter__',
 '__le__',
 '__len__',
 '__lt__',
 '__mod__',
 '__mul__',
 '__ne__',
 '__new__',
 '__reduce__',
 '__reduce_ex__',
 '__repr__',
 '__rmod__',
 '__rmul__',
 '__setattr__',
 '__sizeof__',
 '__str__',
 '__subclasshook__',
 'capitalize',
 'casefold',
 'center',
 'count',
 'encode',
 'endswith',
 'expandtabs',
 'find',
 'format',
 'format_map',
 'index',
 'isalnum',
 'isalpha',
 'isascii',
 'isdecimal',
 'isdigit',
 'isidentifier',
 'islower',
 'isnumeric',
 'isprintable',
 'isspace',
 'istitle',
 'isupper',
 'join',
 'ljust',
 'lower',
 'lstrip',
 'maketrans',
 'partition',
 'removeprefix',
 'removesuffix',
 'replace',
 'rfind',
 'rindex',
 'rjust',
 'rpartition',
 'rsplit',
 'rstrip',
 'split',
 'splitlines',
 'startswith',
 'strip',
 'swapcase',
 'title',
 'translate',
 'upper',
 'zfill']
```

## 1.1 스트링 메소드

1. `.capitalize()`
- 첫 글자만 대문자로 (string은 immutable 하므로 원본 데이터는 그대로)

```python
# 원본데이터는 못바꾼 채 대문자화
a = 'hello my name is haeun'
print(a.capitalize())
print(a) 

# 원본데이터 자체를 바꿔서 대문자화 하려면?
a = 'hello my name is haeun'
a = a.capitalize()
print(a)
```
```
Hello my name is haeun
hello my name is haeun

Hello my name is haeun
```

2. `.title()`
- 모든 단어의 시작을 대문자로 (string은 immutable 하므로 원본 데이터는 그대로)

```python
a = 'hello my name is haeun'
print(a.title())
print(a)
```
```
Hello My Name Is Haeun
hello my name is haeun
```

3. `.upper()`
- 모든 글자를 대문자로 (string은 immutable 하므로 원본 데이터는 그대로)
```python
a = 'hello my name is haeun'
print(a.upper())
print(a)
```
```
HELLO MY NAME IS HAEUN
hello my name is haeun
```

4. `.lower()`
- 모든 글자를 소문자로 (string은 immutable 하므로 원본 데이터는 그대로)
```python
a = 'HELLO MY NAME IS HAEUN'
print(a.lower())
print(a)
```
```
hello my name is haeun
HELLO MY NAME IS HAEUN
```

5. `''.join(x)`
- `''`기호 속 요소를 구분점으로 삼아 x(시퀀스 데이터)를 하나로 묶어줌 
```python
my_list = ['hi', 'my', 'name']
print(''.join(my_list))
print('??'.join(my_list))
```
```
himyname
hi??my??name
```

6. `.strip([chars])`
- 불필요한 공백이나 글자를 일괄 삭제해줌
- `[]`: 써도 되고 안 써도 되는 부분 (여기서는 list라는 의미 아님)

- 공백 삭제
```python
my_string = '   hello    '
print(my_string)
print(my_string.strip())

my_string2 = '      hi\n       '
print(my_string2)
print(my_string2.strip())
```
```
   hello    
hello
      hi
       
hi
```

- 글자 삭제
```python
my_string3 = 'hihihihihihellohihihihi'
print(my_string3.strip('hi')) # 좌우 모두에서 'hi'라는 문자열 삭제
print(my_string3.lstrip('hi')) # 좌측에서만
print(my_string3.rstrip('hi')) # 우측에서만
```
```
ello
ellohihihihi
hihihihihihello
```

7. `.replace(old, new[, count])`
- 데이터를 바꿔줌 (string은 immutable 하므로 원본 데이터는 그대로)
- 찾고 있는 데이터 x가 없으면? 결과값은 -1
```python
a = 'woooooooooow'
print(a.replace('o', '!'))
print(a.replace('o', '!', 3)) # 3개만 바꿈
print(a)
```
```
w!!!!!!!!!!w
w!!!ooooooow
woooooooooow
```

8. `.find(x)`
- 데이터 x가 가장 처음 등장하는 인덱스의 위치를 찾아줌
```python
a = 'apple'
print(a.find('a'))
print(a.find('p'))
print(a.find('z')) 
```
```
0
1
-1
```
- 동일한 기능을 반복문으로 표현해보면?
```python
# 'a'가 몇번째 인덱스인지 찾아보기
for i in range(len(a)):
    if 'a' == a[i]:
        print(i)
        break
    else:
        print(-1)
```
```
0
```


9. `.index(x)`
- 데이터 x가 가장 처음 등장하는 인덱스의 위치를 찾아줌 
- 찾고 있는 데이터 x가 없으면? 결과값은 에러

```python
a = 'apple'
print(a.index('a'))
print(a.index('p'))
print(a.index('z'))
```
```
0
1
ValueError: substring not found
```

10. `.split(x)`
- 기본적으로 문자열 간 공백을 기준하여 쪼갠 후, 각 파편을 리스트화 
- 공백이 아닌 특정 기준점으로 쪼개려면 x자리에 기준점 넣을 것

```python
a = 'my name is'
print(a.split())

b = 'my_name_is'
print(b.split('_'))
```
```
['my', 'name', 'is']
['my', 'name', 'is']
```

11. `.count(x)`
- `x`가 몇 개인지 세어 줌 
```python
print('wooooow'.count('o'))
```
```
5
```


## 1.2 리스트 메소드
1. `.append(x)`
2. `.extend(iterable)`
3. `.insert(idx, x)`
4. `.remove(x)`
5. `.pop()`
6. `.sort()`
    - cf. `sorted`
7. `.reverse()`
8. list copy
9. list comprehension

## 1.3 딕셔너리 메소드
1. `.pop(key[, default])`
2. `.update()`
3. `.get(key[, default])`
4. dictionary comprehension


## 1.4 세트 메소드
1. `.add(x)`
2. `.update({set})`
3. `.remove(x)`
4. `.pop()`

# 2. 기타 함수
## 2.1 map

## 2.2 filter
## 2.3 zip
