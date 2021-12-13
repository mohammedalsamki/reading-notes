# class 7

## *Python Scope*
 
 > Since Python is a dynamically-typed language, variables in Python come into existence when you first assign them a value.

Python resolves names using the so-called LEGB rule, which is named after the Python scope for names.

    LEGB stand for Local, Enclosing, Global, and Built-in.

**global**

Or *module* is the top-most scope in a Python . it contains all of the names defined at the top level. 

in this scope , names are visible everywhere.

**nonlocal**

is a special scope that only exists for nested functions. 

If the local scope is an inner or nested function, then the enclosing scope is the scope of the outer or enclosing function. 

contains the names that defind in the enclosing function. 

names are visible from the code of the inner and enclosing functions.




