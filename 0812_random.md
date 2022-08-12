## 주사위놀이
### random 패키지를 활용

```py
import random
user1 = random.randint(1,6)
user2 = random.randint(1,6)
if user1 > user2 :
    print("USER 1이 이겼습니다!")
else :
    print("USER 2가 이겼습니다!")
```