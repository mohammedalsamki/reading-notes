# Class 3
## FileIO & Exceptions

*Read & Write Files*

A file is a set of bytes used to store data on storage media and they are organized in a specific *format* . 

these bytes are then translated into a *stream* of characters that can be read or written.

on most modern file systems , files are composed of three parts:
    
    1- header.  => contain a header with metadata about the file
    2- data.  =>   contains the actual data of the file as bytes
    3- EOF - End Of FIle. => marks the location of end of the file

Files have path or the location of the file either locally or online. 

To open a file in python use the built-in function `open()` .

> its preferred to open a file in python inside a try-except block to avoid errors. and close the file with the `close()` method. in try-except finally block.

opening a file in reading mode is done by using  `r` or writing with 'w' or 'rb' or 'wb' for binary modes. 

Text,json files are the most common in python. 

```py
reader = open('example.txt')
try:
    # file is open , process data
finally:
    reader.close()
```

**another way to open a file is using the with statement**

its highly recommended to use the with statement when opening a file.

because it allow a cleaner code & makes handling any unexpected errors easier.


awhen `with` exit, the file will be closed without using the close() method.

```py
with open('example.txt') as reader:
    # Further file processing goes here
```

## *Exceptions*

python Interpreter stops the interpretation process if an error is encountered. ( program termination )

> error can be a syntax error or an exception.

*syntax error*

occurs when the parser detects an incorrect statement.

```py
>>> a = 5)
  File "<stdin>", line 1
    a = 5)
         ^
SyntaxError: unmatched ')'
```
**Exception Error**

errors occur when there is a with the code that isn't syntax.

```py
print( 0 / 0)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ZeroDivisionError: integer division or modulo by zero
```
  *- Python details what type of exception error was encountered.*

> We can create our own exception errors too. 

*Raising an Exception*

`raise` to throw an exception if a condition occurs.

```py
username = 'Sanad'
password = '3042018'

usrname_input = input('username: ')
password_input = input('password: ')

if username_input != username and password_input != password:: 
    raise Exception('{} - Incorrect username\\password !'.format(username_input))
```

> if you intered an incorrect username or password, the program will throw an exception.

The program comes to a halt and displays the exception we created to screen.

```py
Traceback (most recent call last):
  File "<input>", line 4, in <module>
Exception: username - Incorrect username/password !
```

*Assertions* 

> its something like fail checks that i can place in my program. 

assert that a condition is met. 

If this condition returned True, then The program can continue. 

If this condition returned False, then he program throws an `AssertionError` `exception`.

> the most common way or place we use `assert' is in our project / program tests.

we can use `assert` to check that a condition is met. using different inputs and assert if that the result is as expected.

```py
expected_results = 2
assert lucas(0) == expected_results
```
if `lucas(0)` returns `2` then the program will continue. as the test will pass.

if if `lucas(0)` did not returned what exactly expected then the program will throw an `AssertionError` `exception`. which will cause a test failure.
 

 we can use the `try` `except` `block` & `finally` .
 
 **Try except blocks**
 
 As mentioned above , A Python program terminates as soon as it encounters an error.
 
    But if we want to handle any type of exception in a program, we can use the `try` `except` & `finally` with `else` blocks .
 
 can be used to catch and handle exceptions. 
 
 > The code will try the first block and if it fails or threw and exception, it will run the except block. 
 
 ```py
usrname_input = 'guest'
tries = 0
def start():
    """Some functions """
    print('started')
    
def login(username_input,password_input):
    username = 'Sanad'
    password = '3042018'
    if username_input != username and password_input != password:
        raise Exception('{} - Incorrect username\\password !'.format(username_input))


try: # will start the excution of this block first
    usrname_input = input('username: ')
    password_input = input('password: ')
    login(usrname_input,password_input)
    start()
except Exception as error:
    # in case of exceptions , the program will run this block
    # -print(error)
    if tries == 3:
        print('you have exceeded the number of tries')
    else:
        print('you have {} tries left'.format(3 - tries))
        usrname_input = input('username: ')
        password_input = input('password: ')
        login(usrname_input,password_input)
    tries += 1
finally:
    # this statement will always be printed 
    print('this code lives 👋')

```