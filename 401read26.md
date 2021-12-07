# class 26

## <ins>*Django*

Django is a high-level Python web framework that enables rapid development of secure and maintainable websites. 

#### Intro to Django
 * Object-relational mapper.

meaning that data models are defined entirely in pyhon & by writing SQL if needed.

* URLs and views.
django uses URL dispatcher to design URLs for an app `URLconf`

How Django processes a request

1- django determines the root URLconf module to use , specified in settings as ROOT_URLCONF , unless the incomming request object has a urlconf attribute.

2 - Django loads the configurations and look for the variable `urlpatterns` . 

3 - django runs through each url pattern in order and stops at the first match requested url.

4 - Django imports and calls the given view.

5- in case of exception raised or there is no match , django invokes appropriate error-handling.

* Templates.
Django’s template language is designed to strike a balance between power and ease.

```html
  <body>
    <h1>All Bands</h1>
    <ul>
    {% for band in bands %}
      <li>
        <h2><a href="{{ band.get_absolute_url }}">{{ band.name }}</a></h2>
        {% if band.can_rock %}<p>This band can rock!</p>{% endif %}
      </li>
    {% endfor %}
    </ul>
  </body>
```
* Templates.

Django provides a range of tools and libraries to help you build forms to accept * input from site visitors, and then process and respond to the input.

Building a form
```html
<form action="/your-name/" method="post">
    <label for="your_name">Your name: </label>
    <input id="your_name" type="text" name="your_name" value="{{ current_name }}">
    <input type="submit" value="OK">
</form>
```
Building a form in Django

forms.py
```py
from django import forms

class NameForm(forms.Form):
    your_name = forms.CharField(label='Your name', max_length=100)
```

rendered ->
```html
<label for="your_name">Your name: </label>
<input id="your_name" type="text" name="your_name" maxlength="100" required>

```
* Authentication.

Django comes with a full-featured and secure authentication system that handles user accounts, groups, permissions and cookie-based user sessions. 

* Admin.

django has an automatic admin interface that reads metadata in models to provide a production ready interface.


* Internationalization.

allow a single Web application to offer its content in languages and formats tailored to the audience.


* Security.

Django provides multiple protections against Clickjacking,Cross-site scripting,Cross Site Request Forgery (CSRF),SQL injection,Remote code execution





