# 객체지향 프로그래밍 (Object-Oriented Programming)


## 목차
1. 객체지향 프로그래밍
2. 클래스
    1. 클래스 선언
    2. 인스턴스화
3. 생성자와 소멸자
    1. 생성자
    2. 소멸자
4. 변수
    1. 클래스 변수
    2. 인스턴스 변수
5. 메소드
    1. 클래스 메소드
    2. 인스턴스 메소드
    3. 스테틱 메소드
6. 상속
    - 다중상속
7. 자체연습


## 1. 객체지향 프로그래밍


## 2. 클래스
### 1. 클래스 선언
### 2. 인스턴스화



## 3. 생성자와 소멸자
### 1. 생성자
### 2. 소멸자



## 4. 변수
### 1. 클래스 변수
### 2. 인스턴스 변수



## 5. 메소드
### 1. 클래스 메소드
### 2. 인스턴스 메소드
### 3. 스테틱 메소드



## 6. 상속
### 다중상속


## 7. 자체연습

```python
class Game_of_Thrones():
    
    def __init__(self, name):
        self.name = name
        self.level = 10
        self.hp = self.level * 5
        self.exp = 0

    def check_hp(self):
        if self.hp <= 0:
            True
        else:
            False

    def attack(self, opponent):
        damage = self.level * 2
        opponent.hp -= damage
        if opponent.check_hp():
            self.exp += 5

class Stark():
    house = 'stark'
    motto = 'winter is coming'
  
class Lanister():
    house = 'lanister'
    motto = 'hear me roar!'                     

class Targaryen():
    house = 'targaryen'
    motto = 'fire and blood'

class Stark_GOT(Game_of_Thrones, Stark):
    
    def say(self):
        return f'{self.name}: {self.house}가문의 구호는 "{self.motto}"입니다.'
    
    def needle_attack(self, opponent):
        pass

class Lanister_GOT(Game_of_Thrones, Lanister):
    
    def say(self):
        return f'{self.name}: {self.house}가문의 구호는 "{self.motto}"입니다.'
    
    def strategy_attack(self, opponent):
        pass

class Targaryen_GOT(Game_of_Thrones, Targaryen):
    
    def say(self):
        return f'{self.name}: {self.house}가문의 구호는 "{self.motto}"입니다.'
    
    def dragon_attack(self, opponent):
        pass



아리아 = Stark_GOT('arya stark')
티리온 = Lanister_GOT('tyrion lanister')
대너리스 = Targaryen_GOT('daenerys targaryen')

print(아리아.say())
print(티리온.say())
print(대너리스.say())
```