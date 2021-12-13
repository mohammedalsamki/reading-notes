# class 28

## <ins>*Django Forms*

Django provides a Form class which is used to create HTML forms. It describes a form and how it works and appears. Each field of the form class map to the HTML form __`<input>`__ element and each one is a class itself, it manages form data and performs validation while submitting the form.


 
### create a form in django.

```py
from django import forms  
class StudentForm(forms.Form):  
  firstname = forms.CharField(label="Enter first name",max_length=50)  
  lastname  = forms.CharField(label="Enter last name", max_length = 100)  
  ```
when the above is rendered , it will produce : 

```py
<label for="id_firstname">Enter first name:</label>  
<input type="text" name="firstname" required maxlength="50"id="id_firstname" />
<label for="id_lastname">Enter last name:</label> <input type="text" name="lastname" required maxlength="100" id="id_lastname" />  

```

### <ins>Commonly used fields :

BooleanField	class __BooleanField(**kwargs)__	CheckboxInput	<br>
CharField	class __CharField(**kwargs)__	TextInput	<br>
ChoiceField	class __ChoiceField(**kwargs)__	Select	<br>
DateField	class __DateField(**kwargs)__	DateInput	<br>
DateTimeField	class __DateTimeField(**kwargs)__	DateTimeInput	<br>
DecimalField	class __DecimalField(**kwargs)__	NumberInput	<br>
EmailField	class __EmailField(**kwargs)__	EmailInput	<br>
FileField	class __FileField(**kwargs)__	ClearableFileInput	<br>
ImageField	class __ImageField(**kwargs)__	ClearableFileInput	<br>


### <ins>Building a Form in Django:
__`forms.py`__
```py
from django import forms  
class StudentForm(forms.Form):  
  firstname = forms.CharField(label="Enter first name",max_length=50)  
  lastname  = forms.CharField(label="Enter last name", max_length = 100)  
  ```

### <ins> Instantiating Form in Django

__`views.py`__
```py
from django.shortcuts import render  
from myapp.form import StudentForm  
  
def index(request):  
    student = StudentForm()  
    return render(request,"index.html",{'form':student})  
```
__`index.html`__
```html
<!DOCTYPE html>  
<html lang="en">  
<head>  
    <meta charset="UTF-8">  
    <title>Index</title>  
</head>  
<body>  
<form method="POST" class="post-form">  
        <!--%  %  
         form.as_p   -->
        <button type="submit" class="save btn btn-default">Save</button>  
</form>  
</body>  
</html>  
```
__`urls.py`__

```py
from django.contrib import admin  
from django.urls import path  
from myapp import views  
urlpatterns = [  
    path('admin/', admin.site.urls),  
    path('index/', views.index),  
]  
```

