# class 29

## <ins>*Django Custom User Model*

> its highly recommended ti use a custom user mode linstead of the built in User model provided by django in a real world project

 
### implement.
[Custom user model ](https://learndjango.com/tutorials/django-custom-user-model)


### two ways to create a custom user model in django : 
- __AbstractUser__ 
- __AbstractBaseUser__


### Steps :
- update config/settings.py

```py
# config/settings.py
INSTALLED_APPS = [
  'django.contrib.admin',
  'django.contrib.auth',
  'django.contrib.contenttypes',
  'django.contrib.sessions',
  'django.contrib.messages',
  'django.contrib.staticfiles',
  'accounts', # new
]
...
AUTH_USER_MODEL = 'accounts.CustomUser' # new
```


- create a new CustomUser model
  
  `accounts/models.py`
```py
from django.contrib.auth.models import AbstractUser
from django.db import models

class CustomUser(AbstractUser):
    pass

    def __str__(self):
        return self.username
```
- create new UserCreation and UserChangeForm
  
  - ```touch accounts/forms.py```
```py
  # accounts/forms.py
from django import forms
from django.contrib.auth.forms import UserCreationForm, UserChangeForm
from .models import CustomUser

class CustomUserCreationForm(UserCreationForm):

    class Meta:
        model = CustomUser
        fields = ('username', 'email')

class CustomUserChangeForm(UserChangeForm):

    class Meta:
        model = CustomUser
        fields = ('username', 'email')
  ```
- update the admin
___admin.py___
```py

# accounts/admin.py
from django.contrib import admin
from django.contrib.auth.admin import UserAdmin

from .forms import CustomUserCreationForm, CustomUserChangeForm
from .models import CustomUser

class CustomUserAdmin(UserAdmin):
    add_form = CustomUserCreationForm
    form = CustomUserChangeForm
    model = CustomUser
    list_display = ['email', 'username',]

admin.site.register(CustomUser, CustomUserAdmin)

```

> perform makemigrations and migrate


### Superuser

(accounts) $ python manage.py createsuperuser