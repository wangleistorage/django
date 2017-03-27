# 搭建一个简单的django

1、新建一个django project

```
django-admin.py startproject myproject
```

2、新建一个app
```
python manage.py startapp myapp
```

3、同步数据库
```
python manage.py migrate
python manage.py makemigrations
```

4、设置myapp/views.py
```
from django.http import HttpResponse

def index(request):
    return HttpResponse('hello django!')
```

5、设置myproject/urls.py
```
from myapp import views as myapp_views

urlpatterns = [
    url(r'^$', myapp_views.index),
    url(r'^admin/', admin.site.urls),
]
```

6、设置myproject/setting.py
```
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'myapp',
]
```

```
ALLOWED_HOSTS = ['192.168.143.210']
```

7、运行django
```
python manage.py runserver 0.0.0.0:10000
```

8、浏览器访问

![access](static/access.png)
