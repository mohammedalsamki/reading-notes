# Class 41
## Pythonisms

### Dunder Methods

Magic methods in Python are the special methods that start and end with the double underscores. They are also called dunder methods. Magic methods are not meant to be invoked directly by you, but the invocation happens internally from the class on a certain action.

- Object Initialization: `__init__`
- Object Representation: `__str`__, `__repr__`
- Context Manager Support and the With Statement: `__enter__`, `__exit__`
- Operator Overloading for Comparing Accounts: `__eq__`, `__lt__`
- Operator Overloading for Merging Accounts: `__add__`
- Callable Python Objects: `__call__`
- Iteration: `__len`__, `__getitem__`, `__reversed__`
- Pickling: `__getstate__`, `__setstate__`
- Hashability: `__hash__`
- Comparison: `__cmp__`

### Python Iterators :

Iterator in python is an object that is used to iterate over iterable objects like lists, tuples, dicts, and sets. The iterator object is initialized using the iter() method. It uses the next() method for iteration. ... This method raises a StopIteration to signal the end of the iteration.

### Python Generators :

Python provides a generator to create your own iterator function. A generator is a special type of function which does not return a single value, instead, it returns an iterator object with a sequence of values. In a generator function, a yield statement is used rather than a return statement.