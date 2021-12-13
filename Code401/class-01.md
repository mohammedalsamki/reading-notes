# class 1

## *Pain vs Suffering*

    No pain no gain.

## *Big O Notation*

its a notation that describes the limiting nature of a function when its argument heads to a a specific value or to maybe to infinity.

also we can classify algorithms by how their run time increases as the input size grows.

Big O can be used to grade different data structures 

Big O can help select the best method to suit required performance.

## *Names and Values in Python*

### **Python is simple**
• Works like other languages  ... until it doesn't.<br>
• Mechanisms are simple ... but the effects can be surprising
<br><br>
> Mutable and immutable are assigned the same


### **References can be more than just names**
- Object attributes.
- List elements.
- Dict values (and keys!).
- Anything on the left side of an assignment.


### **The for loop**
  Iterables in python can produces a stream of values and Assign stream values to name.
  Iterables can Execute statements once for each value in iterable

- *Iterable decides what values it produces* !!

**there is alot of diffrent types of iterable in py**
- Lists
- Strings
- Dicts
- Files

**python also uses iterables in another form , not just in for loops.**

```py
my_list = list(iterable)  # creates a list from any iterable
file = open("/usercode/files/books.txt", "r")
fl = list(file)  # solorlearn problem

results = [f(x) for x in file] # will call f(x) for each item in iterable
print(*results, sep='\n') # this is a cool way to print an iterable items
print([i for i in iterable])
total = sum(results) 

smallest = min(iterable)
largest = max(iterable)

combined = "".join(iterable) 
```

**Stdlib has interesting iterables**
```py
for match in re.finditer(pattern, string):

for root, dirs, files in os.walk('/dir'):

for num in itertools.count():
    # once for each integer... Infinite!
```
> **Stdlib** : the python standard library
> 
> describes the standard library that is distributed with Python. It also describes some of the optional components that are commonly included in Python distributions.



**index on iteration**

using the `enumerate()` function
```py
for index,value in enumerate(list):
	Print index,value
```

Or we can defind the starting index of our iteration 
```py
for index,value in enumerate(list, start=1):
	Print index,value
```

**Looping over more than one list , together!**

The `zip()` built-in function takes a pair of streams, and “zips” them together to produce a stream of pairs and laso can work with arbitrary iterables, not just lists.

The dict() function will accept a stream of key/value pairs, and construct a dictionary from them. 

```py
for item in meal:
    item = [x for i,j in zip(orders,menue) if if item in j["items"]]
    i["items"].append(item)
            
```

