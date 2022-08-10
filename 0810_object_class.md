## 클래스 만드는 법

```python
class Bicycle() :
  def __init__(self):
    self.wheel_size = input("바퀴사이즈 입력 :")
    self.color = input("자전거 색 입력 :")
  def move(self, speed) :
    print("자전거 : 시속 {}KM로 전진".format(speed))
  def stop(self):
    print("바퀴사이즈 {}이고 {}color 자전거 정지".format(self.wheel_size,self.color))

bicycle_1 = Bicycle()
bicycle_2 = Bicycle()

bicycle_1.move(30)
bicycle_1.stop()
bicycle_2.move(30)
bicycle_2.stop()
```

## 클래스 상속하는법
> class 자식클래스이름(부모클래스이름):

- 부모 클래스로부터 상속을 받으려면 클래스를 선언할 때 클래스 이름 소괄호 안에 부모 클래스의 이름을 넣음
- 부모클래스에서 정의한 함수와 자식 클래스에서 정의한 함수 이름이 가튼 경우 부모 클래스의 함수를 호출하려면 명시적으로 '부모클래스이름.함수명()'ㅇ로 호출하거나, 'super().함수명'을 사용
  - 초기화함수 __init__에서 많이 이용
  - super().__init__()
```python
class FoldingBicycle(Bicycle):
  def __init__(self):
    Bicycle.__init__(self)
    self.state = input("상태입력 :")
  def fold(self):
    self.state = 'folding'
    print("자전거 : 접기, state = {}".format(self.state))
  def unfold(self):
    self.state = 'unfolding'
    print("자전거 : 펴기, state = {}".format(self.state))

bicycle_3 = FoldingBicycle()

bicycle_3.fold()
bicycle_3.unfold()
```

```python
class Student_next(Student):
  def __init__(self,name,age):
    Student.__init__(self,name,age)
  def next(self):
    self.next = input("다음 과목 :")
    print("{}학생의 다음 시간 과목은 {}입니다.".format(self.name,self.next))

student_3 = Student_next('나송미',26)
student_3.next()
```