
l# Django-extentions

## Django-extentions runscript 스크립트 파일 실행

## 설치
```bash
pip install django-extensions
```

## 설정
```python
INSTALLED_APPS = (
    ...
    'django_extensions',
)
```
```bash
mkdir scripts
touch scripts/__init__.py
```

## 사용
```python
# script.py
def run():
    url = 'abce.io'
    ...
```
```bash
python manage.py runscript script
```

인자값을 전달할 경우
```python
def run(arg):
    print(arg)
```
```bash
python manage.py runscript script --script-args test
```

## 디버깅
```bash
python manage.py runscript script --traceback
```
