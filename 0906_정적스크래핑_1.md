# 정적 페이지 스크롤링
## metacritic의 pc game top100 목록 추출하기
```py
# requests import하기
import requests

# metacritic pc game ranking url
url = "https://www.metacritic.com/browse/games/score/metascore/year/all/filtered"

# error가 발생하여 headers를 설정해줌
headers = {
    'Accept-Encoding': 'gzip, deflate, sdch',
    'Accept-Language': 'en-US,en;q=0.8',
    'Upgrade-Insecure-Requests': '1',
    'User-Agent': 'Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/605.1.15 (KHTML, like Gecko) Chrome/79.0.3945.130 Safari/605.1.15',
    'Accept': 'text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8',
    'Cache-Control': 'max-age=0',
    'Connection': 'keep-alive',
}
# 오류해결을 위해 headers = headers,allow_redirects = False 를 설정한 후 url html파일 텍스트로 가져오기
a = requests.get(url,headers = headers,allow_redirects = False).text
a

# BeautifulSoup import하기
from bs4 import BeautifulSoup as bs

# 저장한 텍스트파일 BeautifulSoup을 이용하여 lxml로 저장
soup = bs(a,"lxml")
soup

# 제목만 가져오기 위해 find_all로 a태그의 class = title인 항목들을 모두 가져옴
tit = soup.find_all("a",{"class":"title"})

# find_all은 결과를 리스트로 반환하므로  get_text() 이용이 불가하므로 for문을 만들어 텍스트만 추출
tit_li = []
for i in tit :
    tit_li.append(i.get_text())

# 추출한 결과 확인
tit_li
```