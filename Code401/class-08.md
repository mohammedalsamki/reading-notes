# class 8

Table of content 
    
- [class 8](#class-8)
  - [*List comprehension*](#list-comprehension)
  - [*Python Decorators*](#python-decorators)
    - [*First-Class Objects*](#first-class-objects)
    - [*Inner Functions*](#inner-functions)
    - [*Returning Functions From Functions*](#returning-functions-from-functions)
  - [*PySnooper*](#pysnooper)
    - [*Debugging*](#debugging)
    - [*debugging with pySnooper*](#debugging-with-pysnooper)

## <ins>*List comprehension*

List comprehension is a powerful and concise method for creating lists.

> new_list = [ *expression* for *item* in list ]

__notes__
- elegant way to create a managed list.
- more compact way of creating lists.
- more flexible than for loops , faster.

```py
letters = ['A','B','C']
lower_case = [ letter.lower() for letter in letters ]
upper_case = [ letter.upper() for letter in letters ]

print(*lower_case, sep="") # a b c 
print(*upper_case, sep="") # A B C
```

> new_list = [ *expression* for *item* in list if *condition*]

```py
hello , today is 123456

roll = [int(char) for char in line if char.isdigit()]

print(*roll, sep="") # 1 2 3 4 5 6
```

> <ins> making use of python advanced features saves time & improves productivity
> 
> <ins> makes the code managable and readable

## <ins>*Python Decorators*

&emsp;decorator is a function that takes another function and extends the behavior of the latter function without explicitly modifying it. where functions turns given arguments into value.

### *First-Class Objects*

> in python functions First-Class Objects, which means they can be passed around and used as arguments.

```py 
def say_hello(name):
    return f"Hello {name}"

def be_awesome(name):
    return f"Yo {name}, together we are the awesomest!"

def greet_mate(greeter_func,name):
    return greeter_func(name)
```
```py

greet_mate(say_hello,'Mate') # 'Hello Mate'
greet_mate(be_awesome,'Mate') # 'Yo Mate, together we are the awesomest!'

```

### *Inner Functions*

> define functions inside other functions.

### *Returning Functions From Functions*

> use functions as return values.

```py
def parent(num):
    def name():
        return "Parent Name"
    def age():
        return "Parent Age"
    
    if num == 'name':
        return name

    # returning name without the parentheses means returning a reference to the function.

    print(parent('name')) # <function parent.<locals>.name at 0xXXXXX>

    name = parent('name')
    print(name())  # Parent Name

```

> Python allows us to use decorators in a simpler way with the @ symbol  “pie” syntax

```py 
def my_decorator(func):
    def wrapper():
        print("Something is happening before the function is called.")
        func()
        print("Something is happening after the function is called.")
    return wrapper

@my_decorator
def say_whee():
    print("Whee!")
```
*define a decorator, typically define a function returning a wrapper function. The wrapper function uses *args and **kwargs to pass on arguments to the decorated function*



## <ins>*PySnooper*

### *Debugging*
    Debugging means the complete control over the program execution. We use debugging to overcome program from any bad issues.

### *debugging with pySnooper*
> PySnooper - Never use _print_ for debugging again

> PySnooper is a poor man's debugger. 

__PySnooper__ is a tool that allow us to debug our code without using print() As long as there is a decorator .

```py 
import pysnooper

@pysnooper.snoop()
def number_to_bits(number):
    if number:
        bits = []
        while number:
            number, remainder = divmod(number, 2)
            bits.insert(0, remainder)
        return bits
    else:
        return [0]

number_to_bits(6)
```
```bash
Source path:... I:\pysnooper\snoop.py
Starting var:.. number = 6
08:20:22.931922 call         3 def number_to_bits(number):
08:20:22.932865 line         4     if number:
08:20:22.932865 line         5         bits = []
New var:....... bits = []
08:20:22.933868 line         6         while number:
08:20:22.933868 line         7             number, remainder = divmod(number, 2)
Modified var:.. number = 3
New var:....... remainder = 0
08:20:22.933868 line         8             bits.insert(0, remainder)
Modified var:.. bits = [0]
08:20:22.934886 line         6         while number:
08:20:22.934886 line         7             number, remainder = divmod(number, 2)
Modified var:.. number = 1
Modified var:.. remainder = 1
08:20:22.934886 line         8             bits.insert(0, remainder)
Modified var:.. bits = [1, 0]
08:20:22.934886 line         6         while number:
08:20:22.935868 line         7             number, remainder = divmod(number, 2)
Modified var:.. number = 0
08:20:22.935868 line         8             bits.insert(0, remainder)
Modified var:.. bits = [1, 1, 0]
08:20:22.935868 line         6         while number:
08:20:22.936867 line         9         return bits
08:20:22.936867 return       9         return bits
Return value:.. [1, 1, 0]
Elapsed time: 00:00:00.004945
```
