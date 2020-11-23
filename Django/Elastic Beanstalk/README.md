


1. 가상 환경 활성화

    + %HOMEPATH%\env\venv37\Scripts\activate
    + [virtualenv --python=python3.7 venv37]
    + [pip3 install django,pip3 install gunicorn]


2. 장고 환경 설정

    + django-admin startproject myDjango3
    + pip3 freeze > requirements.txt
    + python manage.py runserver


3. eb 환경 설정

    +   mkdir .ebextensions
        폴더 안에 01_python.config파일 만들기


    ```
    option_settings:
    aws:elasticbeanstalk:container:python:
        WSGIPath: [[APP]].wsgi:application
    aws:elasticbeanstalk:environment:proxy:staticfiles:
        /static: static
    ```

    + deacitvate 가상환경 종료

    + eb init -p python-3.7 [[APP NAME]] --region ap-northeast-2
    + eb create [[APP NAME ENV]]--elb-type application --region ap-northeast-2

    + ALLOWED_HOSTS 수정

    + eb deploy