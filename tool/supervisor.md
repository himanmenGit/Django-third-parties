# Supervisor

## 정의
유닉스 계열의 시스템에서 동작하는 프로세스를 모니터링하고 관리하기 위한 클라이언트/서버프로그램

손쉽게 프로세스 상태를 보여주고, 죽은 프로세스도 자동으로 살려준다.

## 용도
* supervisor: 제품의 이름
* supervisord: supervisor 백그라운드 데몬 프로세스
* supervisorctl: supervisor로 구동되는 프로세스를 관리하기 위한 명령

## 설치
```bash
apt-get install supervisor
```

## 설정
/etc/supervisor 디렉토리 아래 supervisor.conf 설정파일을 찾는다. 아래는 gunicorn을 관리하는 프로세스로 지정한 경우 인데 `[program:프로그램명]`으로 기재후 스크립트 경로를 아래 `command`속성에 넣어 준다.
```yaml
[program:myapp]
command=/home/user/gunicorn_start.sh
```

```bash
# gunicorn_start.sh
# 정석이 아님
#!/bin/sh

# 파이썬 가상환경 활성화
source /home/user/.virtualenvs/my_venv/bin/activate

# 프로그램 디렉터리로 이동
cd /home/user/myapp

# 가상환경에 설치된 gunicorn 실행
exec /home/user/.virtualenvs/my_venv/bin/gunicorn -b 0.0.0.0:8081 myapp.wsgi:application
```

## 구동
1. `apt-get` 명령으로 설치 했을 경우 : `service supervisor restart`
2. `pip`로 설치했을 경우 : `supervisord -c <설정파일 위치>`

## 관리
앞서 보았던 `etc/supervisor` 디렉토리 하위에 `supervisord.conf` 설정파일 중 아래 항목을 주석 해제 후 적절한 포트와 아이피, 접속 허용할 계정정보를 입력.
```yaml
[inet_http_server] ; inet (TCP) server disabled by default
port=0.0.0.0:9001
username=admin
password=1234
```
위에 보이는 `restart`, `stop`등의 명령은 쉘에서 `supervisorctl`로도 똑같이 할 수 있다.
