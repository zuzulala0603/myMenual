


1. django host 설치

    + pip install django-hosts



2. Settings.py 설정



    ```
    INSTALLED_APPS = [

    '''
    'django_hosts',
    
    '''
    ]



    MIDDLEWARE = [
    #SHOULD BE FIRST
    'django_hosts.middleware.HostsRequestMiddleware',

    '''

    '''

    #SHOULD BE LAST
    'django_hosts.middleware.HostsResponseMiddleware',
    ]

    ROOT_URLCONF = 'benefit.urls'
    ROOT_HOSTCONF = 'benefit.hosts'
    DEFAULT_HOST = 'www'


    ```


3. ROOT DIR에 hosts.py 생성

    ```
    from django.conf import settings
    from django_hosts import patterns, host

    host_patterns = patterns('',
        host(r'www', settings.ROOT_URLCONF, name='www'),
        host(r'en', 'en.urls', name='en'),
    )
    ```