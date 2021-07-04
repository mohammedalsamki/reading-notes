# Expressions and operators

This chapter describes JavaScript's expressions and operators, including assignment, comparison, arithmetic, bitwise, logical, string, ternary and more.

A complete and detailed list of operators and expressions is also available in the reference.
![java](https://images.idgesg.net/images/article/2018/07/code_coding_javascript_laptop_by_clement_h_cc0_via_unsplash_1200x800-100763703-large.jpg)
## Operators
JavaScript has the following types of operators. This section describes the operators and contains information about operator precedence.

* Assignment operators
* Comparison operators
* Arithmetic operators
* Bitwise operators
* Logical operators
* String operators
* Conditional (ternary) operator
* Comma operator
* Unary operators
* Relational operators


Compound assignment operators

Name |	Shorthand operator	| Meaning
-------- |-------- |-------- |--------  
Assignment	| x = y | 	x = y
Addition assignment|	x += y	|x = x + y
Subtraction assignment	|x -= y|	x = x - y
Multiplication assignment|x *= y|	x = x * y
Division assignment|	x /= y	|x = x / y
Remainder assignment	|x %= y	|x = x % y
Exponentiation assignment	|x **= y 	|x = x ** y
Left shift assignment	|x <<= y|	x = x << y
Right shift assignment	|x >>= y	|x = x >> y
Unsigned right shift assignment	|x >>>= y	|x = x >>> y
Bitwise AND assignment|	x &= y	|x = x & y
Bitwise XOR assignment|	x ^= y|	x = x ^ y
Bitwise OR assignment|x = y	|x = x  y
Logical AND assignment	|x &&= y|	x && (x = y)
Logical OR assignment	|x = y	|x  (x = y)
Logical nullish assignment	|x ??= y|x ?? (x = y)

## JavaScript Functions
A JavaScript function is a block of code designed to perform a particular task.

![func](https://felixgerschau.com/static/9cce80bb6adff0a1d610db7fcd6691ef/5a190/measure-performance-js.png)
A JavaScript function is executed when "something" invokes it (calls it).

Example
function myFunction(p1, p2) {
  return p1 * p2;   // The function returns the product of p1 and p2
}
JavaScript Function Syntax
A JavaScript function is defined with the function keyword, followed by a name, followed by parentheses ().

Function names can contain letters, digits, underscores, and dollar signs (same rules as variables).

The parentheses may include parameter names separated by commas:
(parameter1, parameter2, ...)

The code to be executed, by the function, is placed inside curly brackets: {}

function name(parameter1, parameter2, parameter3) {
  // code to be executed
}
Function parameters are listed inside the parentheses () in the function definition.

Function arguments are the values received by the function when it is invoked.

Inside the function, the arguments (the parameters) behave as local variables.

A Function is much the same as a Procedure or a Subroutine, in other programming languages.

Function Invocation
The code inside the function will execute when "something" invokes (calls) the function:

When an event occurs (when a user clicks a button)
When it is invoked (called) from JavaScript code
Automatically (self invoked)
You will learn a lot more about function invocation later in this tutorial.