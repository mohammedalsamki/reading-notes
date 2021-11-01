![test](https://files.realpython.com/media/Python_Exceptions_Watermark.47f814fbeced.jpg)

# Python Exceptions: An Introduction


A Python program terminates as soon as it encounters an error. In Python,
an error can be a syntax error or an exception. In this article,
you will see what an exception is and how it differs from a syntax error. 
After that, you will learn about raising exceptions and making assertions. 
Then, you’ll finish with a demonstration of the try and except block.

## Exceptions versus Syntax Errors

>>> print( 0 / 0 ))
  File "<stdin>", line 1
    print( 0 / 0 ))
                  ^
SyntaxError: invalid syntax
The arrow indicates where the parser ran into the syntax error. In this example,
  there was one bracket too many. Remove it and run your code again:

>>> print( 0 / 0)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ZeroDivisionError: integer division or modulo by zero
This time, you ran into an exception error. This type of error occurs whenever syntactically correct Python code results in an error. 
  The last line of the message indicated what type of exception error you ran into.
  
  ![new](https://files.realpython.com/media/try_except.c94eabed2c59.png)
  
  When an exception occurs in a program running this function, the program will continue as well as inform you about the fact that the function call was not successful.

What you did not get to see was the type of error that was thrown as a result of the function call. In order to see exactly what went wrong, you would need to catch the error that the function threw.

The following code is an example where you capture the AssertionError and output that message to screen:

try:
    linux_interaction()
except AssertionError as error:
    print(error)
    print('The linux_interaction() function was not executed')
