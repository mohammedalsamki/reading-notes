# class 12

## <ins>*Pandas*
> its a powerful and flexible quantitative library for data analysis.its built on NumPy and provides easy-to-use data structures and data analysis tools for the Python.

    The Pandas module works with the tabular data, and thats the main diffrence between panda and numpy where numpy works with numeric data
    
NumPy arrays have one dtype for the entire array, while pandas DataFrames have one dtype per column

## usage 

```py 
import pandas as pd
```
 ## <ins>*Data Structure*

- Series : A one dimensional labeled array capable of holding any data type 
  
```py

s = pd.Series([3, -5, 7, 4], index=[ , , , ])

```


- Dataframe : A two dimensional labeled data structure with columns
  
```py

data = {'Country': ['Belgium',  'India',  'Brazil'],
'Capital': ['Brussels',  'New  Delhi',  'Brasília'],
'Population': [11190846,  1303171035, 207847528]}

df = pd.DataFrame(data,columns=['Country', 'Capital', 'Population'])

```


## <ins>*Dropping*

```py
s.drop(['a',  'c']) #Drop  values  from  rows  (axis=0)
df.drop('Country', axis=1) #Drop values from columns(axis=1)

```
## <ins>*Sort & Rank*
```py
df.sort_index() #Sort  by  labels  along  an  axis

df.sort_values(by='Country')  #Sort  by  the  values  along  an  axis

df.rank() #Assign  ranks  to  entries
```


*<a href="https://www.datacamp.com/" target="_blank">Source</a>*
<br>
![Datacamp](https://img.shields.io/badge/Datacamp-05192D?style=for-the-badge&logo=datacamp&logoColor=03E860)