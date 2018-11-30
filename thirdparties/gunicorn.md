# gunicorn
[공식문서](http://docs.gunicorn.org/en/latest/install.html)

## 사용법
`Gunicron(Green Unicorn)`은 `Unix` 시스템에서 구동되는 순수파이썬 `WSGI` 서버. 별도로 요구되는 의존성 이 없어 설치하기도 사용하기도 쉽다.

## 설치
```bash
pip install gunicorn
```

## gunicorn에서 제네릭 WSGI응용 어플리케이션으로 장고 실행하기
Gunicorn이 설치 되면 `gunicorn` 명령으로 `Gunicorn` 서버 프로세스를 실행 할 수 있다. 간단하게 `gunicorn`을 호출하기 위해서 `application` 이라는 이름을 가진 `WSGI`어플리케이션 객체가 있는 위치만 알려주면 된다.
```bash
gunicorn myproject.wsgi
```
이렇게 하면 하나의 스레드가 127.0.0.1:8000 주소로 리스닝을 시작하며 하나의 프로세스가 실행괸다. 이 명령은 파이썬 경로에 있어야 하는데 이를 쉽게 확인하는 방법은 `manage.py`파일이 있는 디렉토리에서 실행하는 것.

[Gunicorn 배포문서](http://docs.gunicorn.org/en/latest/deploy.html)
