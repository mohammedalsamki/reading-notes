# Top highlight

Concepts of Functional Programming in Javascript
TK
TK
Follow

Nov 25, 2018 · 12 min read





After a long time learning and working with object-oriented programming, I took a step back to think about system complexity.
“Complexity is anything that makes software hard to understand or to modify." — John Outerhout
Doing some research, I found functional programming concepts like immutability and pure function. Those concepts are big advantages to build side-effect-free functions, so it is easier to maintain systems — with some other benefits.
In this post, I will tell you more about functional programming, and some important concepts, with a lot of code examples. In Javascript!
What is functional programming?
Functional programming is a programming paradigm — a style of building the structure and elements of computer programs — that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data — Wikipedia
Pure functions

“water drop” by Mohan Murugesan on Unsplash
The first fundamental concept we learn when we want to understand functional programming is pure functions. But what does that really mean? What makes a function pure?
So how do we know if a function is pure or not? Here is a very strict definition of purity:
It returns the same result if given the same arguments (it is also referred as deterministic)
It does not cause any observable side effects
It returns the same result if given the same arguments
Imagine we want to implement a function that calculates the area of a circle. An impure function would receive radius as the parameter, and then calculate radius * radius * PI:
