# 제어문 control of flow

# 목차

1. 조건문 
    1. if문
    2. elif
    3. 조건표현식

2. 반복문
    1. while문
    2. for문
        1. sequence형 데이터의 반복
        2. dictionary 반복
    4. break
    5. continue
    6. else
    7. pass
    8. match




## 조건문 

### 1. if문

- 형식

```python
if <조건식>: 
    if의 조건식이 참인 경우 실행하는 코드
else:
    if의 조건식이 거짓인 경우 실행하는 코드 
```

- 'if'문은 반드시 참/거짓을 판단할 수 있는 '조건식'과 함께 사용

- '조건식'이 참인 경우 `:` 이후의 문장을 실행
```python
my_string = input()

if my_string == '12/25':
    print('크리스마스')
else:
    print('크리스마스 아님')

(input_box) 12/25
```
```
크리스마스
```

- '조건식'이 거짓인 경우 `else:` 이후의 문장을 실행
```python
num = 122
num = int(num)

if num % 2 == 0:
    print('짝수')
else:
    print('홀수')
```
```
짝수
```

- 0 or 1이 나올 경우 자동으로 형변환이 발생하여 참/거짓 형태로 바뀜
```python
num = 122
num = int(num)

if num % 2:
    print('홀수')
else:
    print('짝수')
```
```
짝수
```

### 2. elif

- 형식
```python
if <조건식>:
    if조건이 참인 경우 실행
elif <조건식>:
    elif조건이 참인 경우 실행
...
else:
    위의 조건식들에 모두 부합하지 않는 경우 실행
```

- 예제
```python
# 90점이상 A (95이상이라면 good 추가)
# 80점이상 B
# 70점이상 C
# 나머지 F

score = int(input())
    (input_box) 95
if score >= 90:
    print('A')
    if score >= 95:
        print('good')
elif score >= 80:
    print('B')
elif score >= 70:
    print('C')
else:
    print('F')
```
```
A
good
```

### 3. 조건표현식
- 앞서배운 조건문을 좀더 짧게 표현하는 것이 조건표현식. 그러나 가독성이 떨어지는 면이 있음. 
- 형식: true_value if <조건식> else false_value

- eg_1

```python
# 조건표현식 ver.
print('True') if 1 < 0 else print('False')
print('True') if 1 < 2 else print('False')

# 조건문 ver.
if 1 < 0:
    print('True')
else:
    print('False')

if 1 < 2:
    print('True')
else:
    print('False')
```
```
False
True
False
True
```

- eg_2

```python
# 조건표현식 ver.
num = -5
value = num if num >= 0 else 0
print(value)

# 조건문 ver. 
num = -5
if num >= 0:
    value = num
else:
    value = 0
print(value)
```
```
0
0
```

- eg_3
```python
# 조건표현식 ver.
num = 10
result = '홀수' if num % 2 == 1 else '짝수'
print(result)

# 조건문 ver. 
num = 10
if num % 2 == 1 : 
    result = '홀수'
else:
    result = '짝수'
print(result)
```
```
짝수
짝수
```

## 반복문

### 1. while문

- 형식
```python
while <조건식>:
    실행할 코드 
```    
- 코드실행순서
    1. while문 내 조건식 먼저 실행 
    2. True일 때는 아래 실행할 코드 실행 >> 다시 while문으로 올라가 조건식 판별 
    3. 만약 False로 바뀐다면? >> 아래 코드로 넘어가지 못하고 while문 종료 (whilie문 탈출)
- 이때 코드가 무한루프에 빠지지 않도록 탈출코드를 넣어서 반복문을 작성해야 함. 

- eg_1

```Python
a = 0
while a < 5:
    print(a)
    a += 1
```
```
0
1
2
3
4
```

- eg_2
```python
greeting = ''
while greeting != 'hi':
    greeting = input('say hi : ')

(input_box) hello
(input_box) hi
```
```
say hi : hello
say hi : hi
```


### 2. for문
- 정해진 범위 내의 반복
- 형식
```python
for variable in sequence:
    실행할 코드 
    
# sequence : 순서로 만들어진 여러 개의 집합. (sequence 4가지 중 하나 아무거나 넣을 수 있음)
# variable : sequence 집합에서 꺼내온 데이터
```

#### (1) sequence형 데이터의 반복
1. list
```python
# numbers 집합에서 데이터들을 하나씩 꺼내오는 상황
numbers = [1, 2, 3, 4, 5]

for number in numbers: 
    print(number)
```
```
1
2
3
4
5
```

2. string
```python
word = input('단어를 입력하세요 : ')

for char in word:
    print(char)

(input_box) apple
```
```
a
p
p
l
e
```

3. range
```python
for i in range(5):
    print(i)
```
```
0
1
2
3
4
```

4. tuple
```python
for i in (1, 2, 3, 4, 5):
    print(i)
```
```
1
2
3
4
5
```

5. 예제_1
```python
# 1. 1~30까지 숫자 중 홀수만 출력
numbers = range(31)

for number in numbers:
    if number % 2 == 1:
        print(number)

# 2. 1~30까지 숫자 중 홀수만 모아서 리스트로 출력

numbers = range(31)
result = []

for number in numbers:
    if number % 2 == 1:
        result.append(number)

print(result)
```
```
1
3
5
7
9
11
13
15
17
19
21
23
25
27
29

[1, 3, 5, 7, 9, 11, 13, 15, 17, 19, 21, 23, 25, 27, 29]
```

6. 예제_2
```python
menus = ['라면', '김밥', '떡볶이']

for menu in menus:
    print(menu)

for i in range(3):
    print(menus[i])
```
```
라면
김밥
떡볶이

라면
김밥
떡볶이
```

7. 예제_3
```python
menus = ['라면', '김밥', '떡볶이', '돈까스', '튀김']

for menu in menus:
    print(menu)

for i in range(3):
    print(menus[i])

for i in range(len(menus)):
    print(menus[i])

for item in enumerate(menus):
    print(item)
```
```
라면
김밥
떡볶이
돈까스
튀김

라면
김밥
떡볶이

라면
김밥
떡볶이
돈까스
튀김

(0, '라면')
(1, '김밥')
(2, '떡볶이')
(3, '돈까스')
(4, '튀김')
```

#### (2) dictionary 반복

1. for key in dict:

```python
# eg_1

info = {
    'name': 'hauen'
    'location': 'incheon'
    'phone': '010-4728-8208'
}

for key in info:
    print(key)
    print(info[key])
```
```
name
location
phone

hauen
incheon
010-4728-8208
```

```python
# eg_2

blood_type = {
    'A': 5,
    'B': 4,
    'O': 2,
    'AB': 3,
}

print('bloodtype is as below')
for key in blood_type:
    print(key)
```
```
bloodtype is as below
A
B
O
AB
```

2. for key in dict.keys():
```python
blood_type = {
    'A': 5,
    'B': 4,
    'O': 2,
    'AB': 3,
}

print('bloodtype is as below')
for key in dict.keys():
    print(key)

print(blood_type.keys())
```
```
bloodtype is as below
A
B
O
AB

dict_keys(['A', 'B', 'O', 'AB'])
```

3. for value in dict.values():





4. for key, value in dict.items():
