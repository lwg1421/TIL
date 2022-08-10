## 문자열 분리하기
### split()
- 문자열을 부분 문자열로 나누고 싶을 때는 split() 메서드를 이용
- split() 메서드 사용법
> str.split(sep = '')
> - str자리에 문자열을 넣고
> - sep의 ''안에는 무엇을 기준으로 분리할지 설정한다

```python
a = '안녕,하세요,저는,이원근,입니다.'
b = '안녕하세요 저는 이원근입니다.'
print(a.split(sep = ','))
print(b.split(sep = ' '))
```
> - ['안녕', '하세요', '저는', '이원근', '입니다.']
> - ['안녕하세요', '저는', '이원근입니다.']
- 설정한 기준으로 분리되어 리스트 형태로 반환되어 나온다.
- 문자열에 인자 없이 split()을 사용하면 문자열 사이의 모든 공백과 개행문자를 없애고 분리된 문자열을 반환
  - 단어 사이에 공백과 개행문자가 아무리 많더라고 split()을 이용하면 공백과 개행문자를 모두 없애고 문자열을 분리

### maxsplit
- 문자열을 분리할 때 인자 maxsplit을 추가하면 앞에서부터 원하는 횟수만큼만 문자열을 분리할 수 있음
> str.split(sep = '',maxsplit = 숫자)
- str 에는 문자열을 작성
- sep 안에는 분리할 기준을 작성
- 숫자 안에는 원하는 횟수를 작성
```python
"에스프레소 아메리카노 카페라테 카푸치노 바닐라라떼".split(maxsplit = 2)
```
> 출력
> - 에스프레소', '아메리카노', '카페라테 카푸치노 바닐라라떼'
> - 이런식으로 공백을 기준으로 두개까지 분리하고 그 뒤에는 그냥 출력됨.

### 실생활에 응용
```python
ph = "+82-01-6776-1421"
ph_split = ph.split(sep = "-", maxsplit = 1)
ph_real = ph_split[1]
print("고객 전화번호 : {}".format(ph_real))
```
> - 고객 전화번호 : 01-6776-1421

### strip()
- 문자열에서는 앞두 공백 혹은 개행문자와 같이 불필요한 부분을 지워야할 때 strip() 메서드를 사용한다
- 문자열의 중간에 있는것까지 제거하는 것이 아닌 문자열의 앞 혹은 뒤에서부터의 문자만 제거함
- 문자열의 앞뒤 공백과 개행문자는 모두 삭제되지만 문자열 중간의 공백과 개행문자는 삭제되지 않음
> str.strip([chars])
> - str자리에는 문자열 입력
> - chars자리에는 제거할 문자 입력
```python
text = "##  @@@##*안녕하세요# #@ @@**@"
text_fix = text.strip("# @*")
print(text_fix)
 ```

### lstrip() & rstrip()
- strip()메서드는 문자열의 앞과 뒤 양쪽을 검색해 지정한 문자를 삭제하는 역할
- 앞이나 뒤 중에서 한쪽만 삭제하고싶으면 lstrip() 또는 rstrip()를 사용

### 실생활에 응용
```python
coffee_menu = "  에스프레소, 아메리카노,   카페라테   , 카푸치노  "
coffee_menu_list = coffee_menu.split(sep = ",")
print(len(coffee_menu_list))
coffee_menu_list_real = []
for i in range(len(coffee_menu_list)):
  coffee = coffee_menu_list[i].strip(" ")
  coffee_menu_list_real.append(coffee)
print(coffee_menu_list_real)
```

## 문자열 연결하기 
### join()
- 리스트의 모든 항목을 연결하여 하나의 문자열로 만듦
- join() 메서드 사용방법
> str.join(seq)
> - str자리에는 항목들을 연결할 내용을 넣음
> - seq 자리에는 리스트를 넣음
> 예시
 ```python
address_list = ["서울시","서초구","반포대로","201(반포동)"]
a = " "
a.join(address_list)
```
- 출력 : 서울시 서초구 반포대로 201(반포동)

```python
introduce = "안녕하세요. 저는 26살 이원근입니다. 현재 멀티캠퍼스에서 코딩 공부를 하는 중입니다."
introduce_list = introduce.split(" ")
print(introduce_list)
introduce_new = "-".join(introduce_list)
print(introduce_new)
```