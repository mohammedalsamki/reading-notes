# class 33

## <ins>*Authentication & Production Server*


### JSON Web Tokens

What is JSON Web Token?
> a compact and self-contained way for securely transmitting information between parties as a JSON object. This information can be verified and trusted because it is digitally signed. JWTs can be signed using a secret (with the HMAC algorithm) or a public/private key pair using RSA or ECDSA. 
 

JSON Web Tokens are useful in :
 - Authorization.
 - Information Exchange.

#### Structure:  `xxxxx.yyyyy.zzzzz`
-   Header
-   Payload
-   Signature
<br>
<br>



___

### JWT Authentication with Django REST Framework

How JWT Works?

The JWT is just an authorization token that should be included in all requests:

```bash
curl http://127.0.0.1:8000/hello/ -H 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ0b2tlbl90eXBlIjoiYWNjZXNzIiwiZXhwIjoxNTQzODI4NDMxLCJqdGkiOiI3ZjU5OTdiNzE1MGQ0NjU3OWRjMmI0OTE2NzA5N2U3YiIsInVzZXJfaWQiOjF9.Ju70kdcaHKn1Qaz8H42zrOYk0Jx9kIckTn9Xx7vhikY'
```

#### <INS>Installation & Setup

```bash
poetry add djangorestframework_simplejwt
```

**settings.py**

```python
REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES': [
        'rest_framework_simplejwt.authentication.JWTAuthentication',
    ],
}
```

**urls.py**

```python
from django.urls import path
from rest_framework_simplejwt import views as jwt_views

urlpatterns = [
    # with URLS
    path('api/token/', jwt_views.TokenObtainPairView.as_view(), name='token_obtain_pair'),
    path('api/token/refresh/', jwt_views.TokenRefreshView.as_view(), name='token_refresh'),
]
```

#### <INS> Obtain Token

```bash
http post http://127.0.0.1:8000/api/token/ username=admin password=admin@123
```
```json
{
    "access": "eyJ0eXViOiJKV1QiLCJhbGciOiJIyMobXzxlAVh_IAgqyvzCE.eyJ0b2tlbl90eXBlIjoiYWNjZXNzIiwiZXhwIjoxNTQ1MjI0MjU5LCJqdGkiOiIyYmQ1NjI3MmIzYjI0YjNmOGI1MjJlNThjBddjMTdlMSIsInVzZXasdweKHjnKM.D92tTuVi_YcNkJtiGGHtcn6tBcxLCBxz9FKD3qwedas",
    "refresh": "eyeE0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ0b2tlbl90eXBlIjoicmVmcmVzasdIDmV4cCI6MTU0NTMxMDM1OSwianRpIjoiMjk2ZDc1ZDA3Nzc2NDE0ZjkxYjhiOTY4MzI4NGRmOTUiLCJ1cMGQxZDY2MjE5ODc0ZTY3.rA-mnGRg71NEW_ga0VJoaMODS5ABjE5HnxJDb0R5DS0x"
}
```

You can use this **access token** for the next five minutes.

#### <INS>Refresh Token

To get a new **access token**, you should use the refresh token endpoint `/api/token/refresh/` 

The return is a new **access token** that you should use in the subsequent requests.

The **refresh token** is valid for the next 24 hours. When it finally expires too, the user will need to perform a full authentication again using their username and password to get a new set of **access token** + **refresh token**.


#### What’s The Point of The Refresh Token?

 it is necessary to make sure the user still have the correct permissions. 
 
 If your **access token** have a long expire time, it may take longer to update the information associated with the token.
___

### Django Runserver

If you want to run Django in production, be sure to use a production-ready web server like `Nginx`, and let your app be handled by a WSGI application server like `Gunicorn`.

### Gunicorn

Three common building blocks when deploying a Python web application to production are:

- A web server (like nginx)
- A WSGI application server (like Gunicorn)
- Your actual application (written using a developer-friendly framework like Django)

The `web server` accepts `requests`, takes care of general domain logic and takes care of handling https connections. 

Only requests which are meant to arrive at the application are passed on toward the `application server` and the application itself. 

The application code does not care about anything except being able to process single `requests`.


### application server

Gunicorn 🦄 is a `WSGI` server

Gunicorn is built so many different web servers can interact with it. 

It also does not really care what you used to build your web application - as long as it can be interacted with using the WSGI interface.

Gunicorn takes care of everything which happens in-between the `web server` and your web `application`. This way, when coding Django application you don’t need to find your own solutions for:

-   communicating with multiple web servers
-   reacting to lots of web requests at once and distributing the load
-   keepiung multiple processes of the web application running