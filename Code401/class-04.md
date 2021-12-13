# class 4

*Classes and Objects*

Objects are an encapsulation of variables and functions into a single entity. Objects get their variables and functions from classes. Classes are essentially a template to create your objects.

```py
class MyClass:
    variable = "blah"
    def function(self):
        print("This is a message inside the class.")
 
 ```

 *Accessing Object Variables*

 To access the variable inside of the newly created object "myobjectx" you would do the following

 i can create multiple different objects that are of the same class

 To access a function inside of an object :

 ```py
 class MyClass:
    variable = "blah"
    def function(self):
        print("This is a message inside the class.")
myobjectx = MyClass()
myobjectx.function()
 
 ```
 *Thinking Recursively in Python*

 Recursive function is a function will continue to call itself and repeat its behavior until some condition is met to return a result. All recursive functions share a common structure made up of two parts: base case and recursive case. 


>Behind the scenes, each recursive call adds a stack frame (containing its execution context) to the call stack until we reach the base case. Then, the stack begins to unwind as each call returns its results:
 

*Recursive Data Structures in Python*

A data structure is recursive if it can be deﬁned in terms of a smaller version of itself. A list is an example of a recursive data structure. Let me demonstrate. 


*Python Testing with pytest*

**Fixtures**
we define fixtures using a combination of the pytest.fixture decorator, along with a function definition. For example, say you have a file that returns a list of lines from a file, in which each line is reversed: 

```py
def reverse_lines(f):
   return [one_line.rstrip()[::-1] + '\n'
           for one_line in f]
```



**Coverage**

they are objects available to all of our tests. Those objects might contain data you want to share across tests, or they might involve the network or filesystem.

```py
def reverse_lines(f):
   return [one_line.rstrip()[::-1] + '\n'
           for one_line in f]
```