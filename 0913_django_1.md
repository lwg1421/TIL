# Django
## MVT 코딩 순서
- 프로젝트 뼈대 만들기 : 프로젝트 및 앱 개발에 필요한 디렉토리와 파일
생성
- 모델 코딩하기 : 테이블 관련 사항을 개발(models.py, admin.py 파일)
- URLconf 코딩하기 : URL 및 뷰 매핑 관계를 정의(urls.py 파일)
- 템플릿 코딩하기 : 화면 UI 개발(templates/ 디렉토리 하위의 *.html 파
일들)
- 뷰 코딩하기 : 애플리케이션 로직 개발(views.py 파일)

## 프로젝트 뼈대 만들기 순서 명령
- django-admin startproject mysite // mysite라는 프로젝트를 생성함
- python manage.py startapp polls // polls라는 애플리케이션을 생성
- notepad settings.py //설정 파일을 확인 및 수정
- python manage.py migrate //데이터베이스에 기본 테이블을 생성
- python manage.py runserver //현재까지 작업을 개발용 웹 서버로
확인

## 기본 설치 순서

1. C드라이브에 MyTest 폴더 생성

2. `(base) C:\MyTest>pip install Django`

3. 장고는 파이썬 환경에서 동작하는 패키지이므로, 장고가 정상적으로 설치
되었는지 확인하기 위해서 아래와 같이 명령을 입력
`(base) C:\MyTest>python -m django --version`
버전이 출력되면 잘 설치 된 것임

4. mysite라는 프로젝트 만듬
`(base) C:\MyTest>django-admin startproject mysite`

5. mysite 디렉토리 이름 변경
`(base) C:\MyTest>move mysite projectsite`

6. 프로젝트 루트 디렉토리 projectsite으로 이동해서 polls라는 애플리케이션을 만드는 명령을 실행
   - `(base) C:\MyTest>cd projectsite`
   - `(base) C:\MyTest\projectsite>python manage.py startapp polls`

7. polls라는 애플리케이션 폴더 확인
`(base) C:\MyTest\projectsite\polls>dir`

8. 
   - 프로젝트에 필요한 설정 값들은 settings.py파일에 지정
   - settings.py 파일은 프로젝트의 전반적인 사항들을 설정해주는 곳으로,루트 디렉토리를 포함한 각종 디렉토리의 위치, 로그의 형식, 프로젝트에포함된 애플리케이션의 이름 등이 지정되어 있음
   - `(base) C:\MyTest\projectsite\mysite>notepad settings.py`

9. 메모장 파일이 열리면 다음 항목들을 수정
- ALLOWED_HOSTS 항목을 적절하게 지정
    - ALLOWED_HOSTS = ['192.168.35.61', 'localhost', '127.0.0.1’]
- 애플리케이션들은 모두 설정 파일에 등록(polls 애플리케이션도 등록)
    - INSTALLED_APPS =[ ~, 'polls.apps.PollsConfig’, ]
- 프로젝트에 사용할 데이터베이스 엔진
    - 장고는 디폴트로 SQLite3 데이터베이스 엔진을 사용하도록 설정
- 타임존 지정(기본은 세계표준시(UTC)로 되어 있음. 한국시간을 변경)
    - #TIME_ZONE = 'UTC'
    - TIME_ZONE = 'Asia/Seoul'

10. migrate 명령은 데이터베이스에 변경사항이 있을 때 반영해주는 명령
`(base) C:\MyTest\projectsite>python manage.py migrate`

11.  장고에서는 개발 과정 도중에 현재 상태를 확인해볼 수 있도록 runserver
라고 하는 간단한 테스트용 웹 서버를 제공
`(base) C:\MyTest\projectsite>python manage.py runserver`

12. runserver가 정상적으로 실행되었다면, 웹 브라우저를 열고 IP 주소는 runserver가 동작하는 서버 IP주소를 입력
웹 브라우저 주소창에 "http://127.0.0.1:8000/" 입력

