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
bicycle_1.move(30)
bicycle_1.stop()
    ```