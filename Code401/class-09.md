# class 9


## <ins>*Dunder Methods*
 
set of predefined (builtin) methods you can use to enrich your classes.

they start and end with double underscores


```py 
__init__ or __str__.
```

dunder method design is known as the python data model and lets developers tap into rich language features like sequences,iteration .. attribute access.

**examples and usage** : 


```py

Object Initialization: __init__

Object Representation: __str__, __repr__

Iteration: __len__, __getitem__, __reversed__

Operator Overloading for Comparing Accounts: __eq__, __lt__

Operator Overloading for Merging Accounts: __add__

Callable Python Objects: __call__
```



## <ins>*Statistics - Probability*

**Mathematical Statistics Functions**


they are *functions for calculating mathematical statistics of numeric data*

Averages and measures of central location

| Syntax | Description |
| --- | ----------- |
| mean | Arithmetic mean |
| harmonic_mean | Harmonic mean of data. |
| median | Median (middle value) of data. |
| median_low | Low median of data. |
| median_high | High median of data. |
| median_grouped | Median, or 50th percentile, of grouped data. |
| mode | Mode (most common value) of data. |

<u>**Statistics.mean(data)**</u>

Returns sample arithmetic mean of data which can be sequence or iterator.

<u>**statistics.harmonic_mean(data)**</u>

Return the harmonic mean of data, a sequence or iterator of real-valued numbers.

<u>**statistics.median(data)**</u>

Return the median (middle value) of numeric data, using the common «mean of middle two» method. If data is empty, StatisticsError is raised. data can be a sequence or iterator.

<u>**statistics.median_low(data)**</u>

Return the low median of numeric data. If data is empty, StatisticsError is raised. data can be a sequence or iterator.

<u>**statistics.median_high(data)**</u>

Return the high median of data. If data is empty, StatisticsError is raised. data can be a sequence or iterator.

<u>**statistics.median_grouped(data, interval=x)**</u>

Return the median of grouped continuous data, 
calculated as the 50th percentile, using interpolation. If data is empty, StatisticsError is raised. data can be a sequence or iterator.

<u>**statistics.mode(data)**</u>

Return the most common data point from discrete or nominal data. The mode (when it exists) is the most typical value, and is a robust measure of central location.