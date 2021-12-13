# class 6

## *Random Module*

> The random module provides access to functions that support many operations
 
 the most important usage for the random module is that we can generate random numbers.


### Random functions

- Randint
- Random
- Choice
- Shuffle
- Randrange


**Randint**

Randint accepts two parameters: a lowest and a highest number. Generate integers

```py
import random
print random.randint(0, 5) # will be between 0 -> 5
```

**Random**


```py
import random
print random.random() *100 # will be between 0 -> 100
```
**Choice**

Generate a random value from the sequence .

```py
import random
myList = [True,False]

random.choice(myList) # can be True OR False
```
**Shuffle**
shuffles the elements in list in place, so they are in a random order.



```py
from random import shuffle
x = [[i] for i in range(10)]
shuffle(x)

# print x  : [[1], [3], [7], [0], [4], [5], [9], [2], [8], [6]]
```

**Randrange**
Generate a randomly selected element from range(start, stop, step)

```py
import random
for i in range(3):
    print random.randrange(0, 100, 5)
```

## *Risk Analysis*

    The process of identifying the risks in applications or software that you built and prioritizing them to test. 
 
- Identify and notice the risk magnitude indicators: high, medium, low. 

High risk means the company might face loss Medium risk can be tolerated but may cost the company money. 

Low risk is tolerable with little consequence. 


- Risk assessment: 
    - effect. > the impact
    - cause. > the cause
    - likelihood. > the probability

## *Test Coverage*  
__CODE COVERAGE__

>  Test coverage is a useful tool for finding untested parts of a codebase. 
> 
> Test coverage is of little use as a numeric statement of how good your tests are.   


Sufficiency of testing is much more complicated attribute than coverage can answer. 

I would say you are doing enough testing if the following is true:

- You rarely get bugs that escape into production.

- You are rarely hesitant to change some code for fear it will cause production bugs.


## *Big O*

> essentially an equation that describes how the run time scales with respect to some input variables

Rules : 
- add up different steps in given algorithm algorithm.
- constants are always droped.
- diffirent inputs > diffirent variables
- drop non dominate terms