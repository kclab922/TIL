# datastructure

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
- 리스트 안에 새로운 데이터 집어넣기
- 데이터 원본 자체를 바꿔주므로, 메소드 출력시 리턴은 `None`
```python
numbers = [1, 5, 2, 6, 2, 1]
print(numbers.append(10))
print(numbers)
```
```
None
[1, 5, 2, 6, 2, 1, 10]
```

2. `.extend(iterable)`
- 괄호 안에 iterable(반복가능한) 객체를 넣어야 함
- 데이터 원본 자체를 바꿔주므로, 메소드 출력시 리턴은 `None`
```python
numbers = [1, 5, 2, 6, 2, 1]
a = [99, 100]
print(numbers.extend(a))
print(numbers)
print(numbers + a)
```
```
None
[1, 5, 2, 6, 2, 1, 99, 100]
[1, 5, 2, 6, 2, 1, 99, 100, 99, 100]
```

3. `.insert(idx, x)`
- idx번째 자리에 x를 삽입
- 데이터 원본 자체를 바꿔주므로, 메소드 출력시 리턴은 `None`
```python
numbers = [1, 5, 2, 6, 2, 1]
print(numbers.insert(3, 3.5))
print(numbers)
```
```
None
[1, 5, 2, 3.5, 6, 2, 1]
```

4. `.remove(x)`
- 원본 데이터에 x가 없으면 에러 발생
- 데이터 원본 자체를 바꿔주므로, 메소드 출력시 리턴은 `None`
```python
numbers = [1, 5, 2, 6, 2, 1]
print(numbers.remove(6))
print(numbers)
```
```
None
[1, 5, 2, 2, 1]
```

5. `.pop()`
- 괄호 공란: 마지막 데이터 하나 빼내기
- 괄호 내 인덱스 기입: idx번째 숫자 빼내기
- 데이터 원본 자체를 바꿔주며, 메소드 출력시 리턴은 '어떤 데이터를 빼냈는지' 도출
```python
numbers = [1, 2, 3, 4, 5]

print(numbers.pop()) 
print(numbers)

print(numbers.pop(0)) 
print(numbers)
```
```
5
[1, 2, 3, 4]
1
[2, 3, 4]
```

6. `.sort()`
- 정렬
- 데이터 원본 자체를 바꿔주므로, 메소드 출력시 리턴은 `None`
```python
numbers = [1, 6, 2, 1, 3, 2, 7, 10]

# 오름차순 정렬
print(numbers.sort())
print(numbers)

# 내림차순 정렬
print(numbers.sort(reverse = True))
print(numbers)
```
```
None
[1, 1, 2, 2, 3, 6, 7, 10]
None
[10, 7, 6, 3, 2, 2, 1, 1]
```
- cf. `sorted`: 데이터 원본은 바꾸지 못하나, 함수 출력시 리턴되는 결과가 있음
```python
numbers = [1, 6, 2, 1, 3, 2, 7, 10]
print(sorted(numbers))
print(numbers)
```
```
[1, 1, 2, 2, 3, 6, 7, 10]
[1, 6, 2, 1, 3, 2, 7, 10]
```

7. `.reverse()`
- 역순 (정렬해주지는 않음)
```python
numbers = [1, 6, 2, 1, 3, 2, 7, 10]
print(numbers.reverse())
print(numbers)
```
```
None
[10, 7, 2, 3, 1, 2, 6, 1]
```

8. list copy

- `copy_list` 변경 시 `origin_list`도 같이 변경 

1. eg_1
```python
origin_list = [1, 2, 3]
copy_list = origin_list

copy_list[0] = 100 

print(origin_list)
print(copy_list)
```
```
[100, 2, 3]
[100, 2, 3]
```

2. eg_2 (깊이 있는 리스트)
```python
a = [1, 2, [99, 100]]
b = list(a)
b[2][1] = 1000

print(a)
print(b)
```
```
[1, 2, [99, 1000]]
[1, 2, [99, 1000]]
```

- `copy_list`를 변경해도 `origin_list`는 불변
1. eg_1
```python
a = [1, 2, 3]
b = list(a)

b[0] = 100

print(a)
print(b)
```
```
[1, 2, 3]
[100, 2, 3]
```

2. eg_2
```python
a = [1, 2, 3]
b = a[:] # a를 처음부터 끝까지 다 쪼개서 리스트로 만듦. 결국 그대로 할당한다는 의미. 

b[0] = 100

print(a)
print(b)
```
```
[1, 2, 3]
[100, 2, 3]
```

3. eg_3 (깊이 있는 리스트의 독립적인 복사)
```python
import copy
a = [1, 2, [99, 100]]
b = copy.deepcopy(a)

b[2][1] = 1000

print(a)
print(b)
```
```
[1, 2, [99, 100]]
[1, 2, [99, 1000]]
```

9. list comprehension
- 리스트를 만드는 기능. (리스트 안에 for문을 넣어버리는 방식)
- 권장하지 않으나, 타인의 코드 파악 목적으로 숙지.

```python
# 1. for문 이용

numbers = [1, 2, 3, 4, 5]
result = []

for number in numbers:
    result.append(number ** 3)
print(result)

# 2. list comprehension 이용
numbers = [1, 2, 3, 4, 5]

result2 = [number ** 3 for number in numbers]
print(result2)
```
```
[1, 8, 27, 64, 125]
[1, 8, 27, 64, 125]
```

- 예제_1: 짝수만 고르기
```python
# 1. for문 이용
numbers = range(1, 11)

even_list = []
for number in numbers:
    if number % 2 == 0:
        even_list.append(number)
        
print(even_list)

# 2. list comprehension 이용
even_list2 = [number for number in numbers if number % 2 == 0]
print(even_list2)
```
```
[2, 4, 6, 8, 10]
[2, 4, 6, 8, 10]
```

- 예제_2: 모음만 제하기
```python
words = 'my name is hong'
vowels = 'aeiou'

# 1. for문 이용
result = []
for word in words:
    if word not in vowels:
        result.append(word)
print(result)
print(''.join(result))

# 2. list comprehension 이용
result2 = [word for word in words if word not in vowels]
print(result2)
print(''.join(result2))

# 3. replace 이용
for vowel in vowels:
    words = words.replace(vowel, '')
print(words)
```

```
['m', 'y', ' ', 'n', 'm', ' ', 's', ' ', 'h', 'n', 'g']
my nm s hng

['m', 'y', ' ', 'n', 'm', ' ', 's', ' ', 'h', 'n', 'g']
my nm s hng

my nm s hng
```


## 1.3 딕셔너리 메소드
- 단순 밸류 변경
```python
info = {
    'name': 'choi',
    'location': 'incheon',
}
print(info['name'])

info['name'] = 'kim'
print(info)
```
```
choi
{'name': 'kim', 'location': 'incheon'}
```

1. `.pop(key[, default])`
- 특정 키와 밸류값 모두 제거
```python
info = {
    'name': 'choi',
    'location': 'incheon',
}

print(info)
print(info.pop('location'))
print(info)
```
```
{'name': 'choi', 'location': 'incheon'}
incheon
{'name': 'choi'}
```

2. `.update()`
- 수정
```python
info = {
    'name': 'choi',
    'location': 'incheon',
}

print(info.update(name = 'park'))
print(info)
```
```
None
{'name': 'park', 'location': 'incheon'}
```

3. `.get(key[, default])`
- 가져오기.
- 해당하는 키가 없으면 디폴트값 출력.
- 빈출 ★
```python
info = {
    'name': 'choi',
    'location': 'incheon',
}

print(info.get('name'))
print(info.get('phone'))
print(info.get('phone', '해당 키가 없습니다.'))
```
```
choi
None
해당 키가 없습니다.
```

4. dictionary comprehension

- 예제_1
    - {1: 1, 2: 8, 3: 9, ...} 도출하기
```python
# 1. for문 이용
result = {}
numbers = range(1, 11)

for number in numbers:
    result[number] = number ** 3

print(result)

# 2. dictionary comprehension
result2 = {number: number ** 3 for number in range(1, 11)}
print(result2)
```
```
{1: 1, 2: 8, 3: 27, 4: 64, 5: 125, 6: 216, 7: 343, 8: 512, 9: 729, 10: 1000}
{1: 1, 2: 8, 3: 27, 4: 64, 5: 125, 6: 216, 7: 343, 8: 512, 9: 729, 10: 1000}
```

- 예제_2
    - 밸류값 50 이상인 키와 밸류만 추출하기
```python
dust = {
    '서울': 100,
    '대구': 30,
    '부산': 50,
    '광주': 80,
    '제주': 20,
}

# 1. for문 이용
result = {}
for k, v in dust.items():
    if v >= 50:
        result[k] = v
print(result)

# 2. dictionary comprehension
result2 = {k: v for k, v in dust.items() if v >= 50}
print(result2)

# 3. dictionary comprehension 응용
result3 = {k: '나쁨' for k, v in dust.items() if v >= 50}
print(result3)
```
```
{'서울': 100, '부산': 50, '광주': 80}
{'서울': 100, '부산': 50, '광주': 80}
{'서울': '나쁨', '부산': '나쁨', '광주': '나쁨'}
```


## 1.4 세트 메소드
- 세트: 집합 형태의 자료구조


1. `.add(x)`: 
- 세트는 데이터가 중복 존재할 수 없으므로, 같은 데이터를 두 번 추가해도 결과값은 그대로.
```python
fruits = {'apple', 'banana', 'melon'}

print(fruits.add('watermelon'))
print(fruits)
print(fruits.add('watermelon'))
print(fruits)
```
```
None
{'apple', 'banana', 'watermelon', 'melon'}
None
{'apple', 'banana', 'watermelon', 'melon'}
```

2. `.update({set})`
```python
fruits = {'apple', 'banana', 'melon'}

print(fruits.update({'grape', 'orange'}))
print(fruits)
```
```
None
{'grape', 'apple', 'banana', 'orange', 'melon'}
```

3. `.remove(x)`
```python
fruits = {'apple', 'banana', 'melon'}

print(fruits.remove('banana'))
print(fruits)
```
```
None
{'apple', 'melon'}
```

4. `.pop()`
- 여러 번 실행하면 랜덤(내부적으로 설정된 순서)으로 하나씩 지워짐.
```python
fruits = {'apple', 'banana', 'melon'}

print(fruits.pop())
print(fruits)
```
```
apple
{'melon', 'banana'}
```


# 2. 기타 함수
- 메소드가 아니라 함수.

## 2.1 map
- 각 데이터에 특정 함수를 적용시킬 때 사용.
- map(function, iterable)
- map(함수, 시퀀스형의 반복가능한 객체)
- map(적용시킬 함수, 적용대상 값)
- map으로 바꾼 다음 반드시 list로 바꿔줘야 함.

```python
a = [1, 2, 3]
number_str = map(str, a)

print(number_str)
print(list(number_str))
```
```
<map object at 0x00000277502294B0>
['1', '2', '3']
```

- 예제_1_세제곱 도출하기
```python
a = [1, 2, 3]

# 1. for문 이용
result = []
for number in a:
    result.append(number ** 3)

print(result)

# 2. map함수 이용
def cube(x):
    return x ** 3

result2 = map(cube, a)
print(list(result2))
```
```
[1, 8, 27]
[1, 8, 27]
```

- 예제_2
```python
a = '1 3 5 7 9'
numbers = list(map(int, a.split()))
# a라는 함수를 ()빈칸을 기준으로 쪼개고 + int로 바꾼 후 + list로 만들어줌.
print(numbers)
```
```
[1, 3, 5, 7, 9]
```

## 2.2 filter
- 형식: filter(function, iterable)
- 의미: 함수를 객체에 적용하여 결과값이 True인 데이터만 추출
- filter에 들어가는 function은 반드시 T/F를 반환해야 함 
```python
# 홀수여부 구분하는 함수 제작
def is_odd(x):
    if x % 2 == 1:
        return True
    else:
        return False   # return bool(x % 2)도 가능
print(is_odd(5))
print(is_odd(10))

# 1. for문 및 위 함수 이용하여 홀수 추출
numbers = [1, 2, 3, 4, 5]
result = []
for number in numbers:
    if is_odd(number):
        result.append(number)
print(result)

# 2. filter 및 위 함수 이용하여 홀수 추출
numbers = [1, 2, 3, 4, 5]
result2 = filter(is_odd, numbers)
print(result2) # lazy한 함수이므로 바로 출력 안 됨. 아래처럼 리스트로 바꿔줘야
print(list(result2))
```
```
True
False

[1, 3, 5]

<filter object at 0x0000020C225E7B80>
[1, 3, 5]
```

## 2.3 zip
- 형식: zip(x, y)
- 의미: x의 데이터와 y의 데이터를 짝지어서 데이터 zip을 만들어 줌.
- a와 b의 개수가 맞아야 함. (개수가 안 맞으면 적은 것을 기준으로 합쳐짐)
```python
a = [1, 2, 3]
b = [100, 200, 300]
result = zip(a, b)

print(result) # lazy한 함수이므로 바로 출력 안 됨. 아래처럼 리스트로 바꿔줘야
print(list(result))
```
```
<zip object at 0x0000020C22601B40>
[(1, 100), (2, 200), (3, 300)]
```