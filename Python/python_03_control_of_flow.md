# 제어문

## 목차

1. 조건문 
    1. if문
    2. elif
    3. 조건표현식

2. 반복문
    1. while문
    2. for문
    3. dictionary 반복
    4. break
    5. continue
    6. else
    7. pass
    8. match




## 조건문 

1. if문

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

2. elif

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
if 
```