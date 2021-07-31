# ANONYMOUS FUNCTIONS  & FUNCTION EXPRESSIONS 
Expressions produce a value. They can be used where values are expected. 
If a function is placed where a browser expects to see an expression, 
(e.g., as an argument to a function), then it gets treated as an expression. 
FUNCTION DECLARATION 
A function declaration creates a function that you 
can call later in your code. It is the type of function 
you have seen so far in this book. 
In order to call the function later in your code, you 
must give it a name, so these are known as named 
functions. Below, a function called area() is 
declared, which can then be called using its name. 
function area (width, height) 
return width * height; 
}; 
var size= area (3, 4) ; 
As you will see on p456, the interpreter always 
looks for variables and function declarations before 
going through each section of a script, line-by-line. 
This means that a function created with a function 
declaration can be called before it has even been 
declared. 
For more information about how variables and 
functions are processed first, see the discussion 
about execution context and hoisting on 
p452 - p457. 
§ FUNCTIONS, METHODS & OBJECTS 
FUNCTION EXPRESSION 
If you put a function where the interpreter would 
expect to see an expression, then it is treated as an 
expression, and it is known as a function expression. 
In function expressions, the name is usually omitted. 
A function with no name is called an anonymous 
function. Below, the function is stored in a variable 
called area. It can be called like any function created 
with a function declaration. 
var ar ea = f unction(width, height) { 
r eturn width * height; 
} ; 
var size = area (3, 4) ; 
In a function expression, the function is not 
processed until the interpreter gets to that 
statement. This means you cannot call this function 
before the interpreter has discovered it. It also means 
that any code that appears up to that point could 
potentially alter what goes on inside this function.
