---
jupyter:
  jupytext:
    formats: ipynb,md
    text_representation:
      extension: .md
      format_name: markdown
      format_version: '1.1'
      jupytext_version: 1.2.4
  kernelspec:
    display_name: Python 3
    language: python
    name: python3
---

# Name(s)
**PUT YOUR FULL NAME(S) HERE**


**Instructions:** This is an individual assignment, but you may discuss your code with your neighbors.


# Python and NumPy

While other IDEs exist for Python development and for data science related activities, one of the most popular environments is Jupyter Notebooks.

This lab is not intended to teach you everything you will use in this course. Instead, it is designed to give you exposure to some critical components from NumPy that we will rely upon routinely.

## Exercise 0
Please read and reference the following as your progress through this course. 

* [What is the Jupyter Notebook?](https://nbviewer.jupyter.org/github/jupyter/notebook/blob/master/docs/source/examples/Notebook/What%20is%20the%20Jupyter%20Notebook.ipynb#)
* [Notebook Tutorial](https://www.datacamp.com/community/tutorials/tutorial-jupyter-notebook)
* [Notebook Basics](https://nbviewer.jupyter.org/github/jupyter/notebook/blob/master/docs/source/examples/Notebook/Notebook%20Basics.ipynb)

**In the space provided below, what are three things that still remain unclear or need further explanation?**


- Other than downloading the assignment zip on github and uploading to jupyterlabs ide ourselves. how can we import github classroom projects easily into jupyterlab. 
- How does the md file sync with the .iypynb automatically?
- Due to how the .md file and .ipynb file sync. Should we only edit in the .md file then turn in the .ipynb file?


## Exercises 1-7
For the following exercises please read the Python appendix in the Marsland textbook and answer problems A.1-A.7 in the space provided below.


## Exercise 1

```python
import numpy as np

a = np.full((4,6), 2)
print(a) 
```

## Exercise 2

```python
# kinda confused on what a leading diagonal is...
b = (2 * np.eye(4,6)) + np.ones((4,6))
print(b)
```

## Exercise 3

```python
c = a * b
print(c)

# because the dot product needs a x b , b x c matrix layout for operands
```

## Exercise 4

```python
d = np.dot(a.transpose(), b)
e = np.dot(a,b.transpose())
print(d)
print(d)
```

## Exercise 5

```python
def runIt():
    print("Hello World. This environment is my new habitat...")
    
runIt()
```

## Exercise 6

```python
def details():
    r = np.random.random((4,6))
    print("sum: ", r.sum())
    print("mean: ", r.mean())

details()
    
```

## Exercise 7

```python
def loopy(arr):
    ones = 0
    for row in arr:
        for i in row:
            if i == 1:
                ones += 1
    return ones
                
o = np.eye(4,6)
print(o)
print("ones count: ", loopy(o))
```

## Excercises 8-???
While the Marsland book avoids using another popular package called Pandas, we will use it at times throughout this course. Please read and study [10 minutes to Pandas](https://pandas.pydata.org/pandas-docs/stable/getting_started/10min.html) before proceeding to any of the exercises below.


## Exercise 8
Repeat exercise A.1 from Marsland, but create a Pandas DataFrame instead of a NumPy array.

```python
import pandas as pd

ad = pd.DataFrame(a, index=list(range(4)), columns=list(range(6)))
print(ad)
```

## Exercise 9
Repeat exercise A.2 using a DataFrame instead.

```python
bd = pd.DataFrame(b, index=list(range(4)), columns=list(range(6)))
print(bd)
```

## Exercise 10
Repeat exercise A.3 using DataFrames instead.

```python
cd = pd.DataFrame(c, index=list(range(4)), columns=list(range(6)))
print(cd)
```

## Exercise 11
Repeat exercise A.7 using a dataframe.

```python
def data_ones(arr):
    ones = 0
    for i in range(len(arr)):
        for j in range(len(arr.iloc[i])):
            if 1 == arr.iloc[i,j]:
                ones += 1
    return ones

nd = pd.DataFrame(np.eye(4,6), index=list(range(4)), columns=list(range(6)))
print(nd)

print("# of ones: ",data_ones(nd))
    
```

## Exercises 12-14
Now let's look at a real dataset, and talk about ``.loc``. For this exercise, we will use the popular Titanic dataset from Kaggle. Here is some sample code to read it into a dataframe.

```python
titanic_df = pd.read_csv(
    "https://raw.githubusercontent.com/dlsun/data-science-book/master/data/titanic.csv"
)
titanic_df
```

Notice how we have nice headers and mixed datatypes? That is one of the reasons we might use Pandas. Please refresh your memory by looking at the 10 minutes to Pandas again, but then answer the following.


## Exercise 12
How do you select the ``name`` column without using .iloc?

```python
cols = titanic_df['name']
cols

```

## Exercise 13
After setting the index to ``sex``, how do you select all passengers that are ``female``? And how many female passengers are there?

```python
titanic_df.set_index('sex',inplace=True)

```

## Exercise 14
How do you reset the index?

```python

```

```python
titanic_df.reindex(index=titanic_df[0], columns=list(titanic_df.columns))
```

```python

```
