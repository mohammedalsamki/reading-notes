# class 34

## <ins>*API Deployment*

###  Django Settings Best Practices

- Issues
    - Different environments.
    - Sensitive data.
    - Sharing settings between team members.
    - Django settings are a Python code. (instead of key-value pairs)

## Different Approaches

There is no built-in universal way to configure Django settings without hardcoding them.

some of common approaches

### <ins>settings_local.py

extend all environment-specific settings in the `settings_local.py` file, which is ignored by VCS. example:

`settings.py` file:

```py
ALLOWED_HOSTS = ["example.com"]

DEBUG = False

DATABASES = {
    "default": {
        "ENGINE": "django.db.backends.postgresql",
        "NAME": "production_db",
        "USER": "user",
        "PASSWORD": "password",
        "HOST": "db.example.com",
        "PORT": "5432",
        "OPTIONS": {"sslmode": "require"},
    }
}
...
```
`settings_local.py` file:

```py

ALLOWED_HOSTS = ["localhost"]
DEBUG = True
DATABASES = {
    "default": {
        "ENGINE": "django.db.backends.postgresql",
        "NAME": "local_db",
        "HOST": "127.0.0.1",
        "PORT": "5432",
    }
}
```
### Pros:

-   Secrets not in VCS.

### Cons:

-   `settings_local.py` is not in VCS, so you can lose some of your Django environment settings.
-   The Django settings file is a Python code, so `settings_local.py` can have some non-obvious logic.
-   You need to have `settings_local.example` (in VCS) to share the default configurations for developers.

### <ins>Separate settings file for each environment

In this case, you make a `settings` package with the following file structure:
```
settings/
   ├── __init__.py
   ├── base.py
   ├── ci.py
   ├── local.py
   ├── staging.py
   ├── production.py
   └── qa.py
```

`settings/local.py`
```py
from .base import *

ALLOWED_HOSTS = ["localhost"]

DEBUG = True

DATABASES = {
    "default": {
        "ENGINE": "django.db.backends.postgresql",
        "NAME": "local_db",
        "HOST": "127.0.0.1",
        "PORT": "5432",
    }
}
```
To run a project with a specific configuration, you need to set an additional parameter:

```bash
python manage.py runserver --settings=settings.local
```
### Pros:

-   All environments are in VCS.
-   It’s easy to share settings between developers.

### Cons:

-   You need to find a way to handle secret passwords and tokens.
-   “Inheritance” of settings can be hard to trace and maintain.

### Environment variables

To solve the issue with sensitive data

```py
import os

SECRET_KEY = os.environ["SECRET_KEY"]

DATABASES = {
    "default": {
        "ENGINE": "django.db.backends.postgresql",
        "NAME": os.environ["DATABASE_NAME"],
        "HOST": os.environ["DATABASE_HOST"],
        "PORT": int(os.environ["DATABASE_PORT"]),
    }
}

```



This is the simplest example using Python `os.environ` and it has several issues:

1.  You need to handle `KeyError` exceptions.
2.  You need to convert types manually 

### Pros:

-   Configuration is separated from code.
-   Environment parity – you have the same code for all environments.
-   No inheritance in settings, and cleaner and more consistent code.


### Cons:

-   You need to handle sharing default config between team member.




## <ins>*SSH Secure Shell*
is a remote administration protocol that allows users to control and modify their remote servers over the Internet. The service was created as a secure replacement for the unencrypted Telnet and uses cryptographic techniques to ensure that all communication to and from the remote server happens in an encrypted manner.


The SSH command consists of 3 distinct parts:

```ssh
ssh {user}@{host}
```

