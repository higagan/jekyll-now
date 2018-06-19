---
layout: post
title:  Balanced Brackets
published: true
category: Python
---
 Let’s take a quick example to see how to define a python dictionary.
``` python
 mydict={'a':1,'b':2,'c':3}
```
We can also use the dict() function.
``` python
otherdict=dict((['a',1],['b',2],['c',3]))
otherdict
{‘a’: 1, ‘b’: 2, ‘c’: 3}
```
But we have one problem. If the key does not exist, and we try to access it, it raises a KeyError.
``` python
>>> otherdict['d']
Traceback (most recent call last):
File "<pyshell#364>", line 1, in <module>
otherdict['d']
```
To deal with this situation, we have defaultdict in Python. First, we must import it from Python collections module.
```python
>>> from collections import defaultdict

```
Next, we define a python function to return a default value for the keys we don’t initialize.

```python

>>> def defaultvalue():
                return 0
```
Now, we create a Python defaultdict using the defaultdict() function. To this, we pass the function defaultvalue as a function argument. Remember, you must pass the function object, you don’t have to call it with parentheses.
``` python

>>> otherdict=defaultdict(defaultvalue)
>>> otherdict['a']=1
>>> otherdict['b']=2
>>> otherdict['c']=3
>>> otherdict['d']     // prints 0 and doest give any error
```
For details
https://data-flair.training/blogs/python-defaultdict/
