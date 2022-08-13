## random 패키지
### 주사위놀이

```py
import random
user1 = random.randint(1,6)
user2 = random.randint(1,6)
if user1 > user2 :
    print("USER 1이 이겼습니다!")
else :
    print("USER 2가 이겼습니다!")
```

### 로또번호 추천
>random.randint()
```py
import random
print("---- 추천 로또 번호 ----")
lotto = []
for i in range(6) :
  i = random.randint(1,45)
  lotto.append(i)
print("이번주 추천 로또 번호는\n{}입니다.".format(lotto))
```


### 묵찌빠 추천 
> random.choice()
```py
import random
print("--- 묵찌빠 추천 ---")
recommend = random.choice(["묵","찌","빠"])
if (recommend == "찌") or (recommend == "빠") :
  print("이번에 당신은 {}를 내시는것을 추천합니다.".format(recommend))
else :
  print("이번에 당신은 {}을 내시는것을 추천합니다.".format(recommend))
```