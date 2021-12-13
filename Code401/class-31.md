# class 31

## <ins>*Docker*

> Docker is an open source containerization platform. It enables developers to package applications into containers—standardized executable components combining application source code with the operating system (OS) libraries and dependencies required to run that code in any environment.

 Docker images contain all the dependencies needed to execute code inside a container, so containers that move between Docker environments with the same OS work with no changes. Docker uses resource isolation in the OS kernel to run multiple containers on the same OS.

Django REST Framework works alongside the Django web framework to create web APIs. We cannot build a web API with only Django Rest Framework; it always must be added to a project after Django itself has been installed and configured.

> Django creates websites containing webpages, while Django REST Framework creates web APIs which are a collection of URL endpoints containing available HTTP verbs that return JSON.


## Django REST Framework
```py 
poetry add djangorestframework
```

- add `'rest_framework'` to `INSTALLED_APPS` in setting.py

we will need a new URL route, a new view, and a new serializer file

the approach is to create a dedicated `api` app so in future if we add more apps each app can contain the models,views,templates and urls needed for dedicated webpages , but all api-specific files for the project will live in a dedicated api app. 

```py
python manage.py startapp api
```
- add `'api'` to `INSTALLED_APPS` in setting.py
- setup urls.py ,views.py 
- in the views , a Serializers must be used 

### Serializers

> A serializer translates data into a format that is easy to consume over the internet, typically JSON, and is displayed at an API endpoint.

```py
touch ./api/serializers.py

```
```py
# api/serializers.py
from rest_framework import serializers

from appmodel.models import Model


class AppSerializer(serializers.ModelSerializer):
    class Meta:
        model = Model
        fields = ('title', 'subtitle', 'author', 'isbn')

```

We want to see what our API endpoint looks like.

Browser : http://127.0.0.1:8000/api/ after running the server

or use postman,thunder to check that api.





