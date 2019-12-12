

```python
# The pythoic 
import this
```

# Lambda, map and reduce

'lambda function' The quickest way to define a one-time used function


```python
# Comparing lambda function with normal function

def square(x):
    return x * x

square_lambda = lambda x: x * x

assert square(3) == square_lambda(3)
print(' square: {}\n square_lambda: {}'.format(square(3), square_lambda(3)))
```


```python
# map
nums = [1, 2, 3, 4, 5]
nums_squared = map(square, nums)
nums_squared_lambda = map(lambda x: x * x, nums)

print(list(nums_squared))
print(list(nums_squared_lambda))
```


```python
list(map(str, nums))
```


```python
# reduce
from functools import reduce

# computing 5!
nums = [1, 2, 3, 4, 5]
product = reduce(lambda x, y: x * y, nums)
print(product)
```

# List

The most commonly used data type in python


```python
nums = [1, 2, 3, 4, 5]
weekdays = ['Mon', 'Tue', 'Wed', 'Thu', 'Fri']
```

## 1. Index and slicing


```python
nums[-1]
```


```python
nums[::-1]
```


```python
nums[::2]
```


```python
nums[-2::-2]
```

The basic sytax \[star:end:step\]


## 2. insert and delete


```python
elems = list(range(10))
elems[1:1] = [0.2, 0.3, 0.5]
print(elems)
```

## 3. Packing and swapping


```python
a = [1, 2, 3]
x, y, z = a
print(x, y, z)
```


```python
print(x, y)
x, y = y, x
print(x, y)
```

## 4. Flattening


```python
list_of_lists = [[1], [2, 3], [4, 5, 6]]
sum(list_of_lists, [])
```

## 5. enumerate and zip


```python
weekdays = ['Mon', 'Tue', 'Wed', 'Thu', 'Fri']
for i,j in enumerate(weekdays):
    print(i, j)
```


```python
nums = [0, 1, 2, 3, 4]
weekdays = ['Mon', 'Tue', 'Wed', 'Thu', 'Fri']
list(zip(nums, weekdays))
```

# iterator


```python
new_list = [1, 2, 3, 4]
new_iterator = iter([1, 2, 3, 4])
new_iterator
```


```python
for item in new_list:
    print(item)
```


```python
for item in new_iterator:
    print(item)
```


```python
class TestIterator: 
    # Cosntructor 
    def __init__(self, limit): 
        self.limit = limit 
    # Called when iteration is initialized 
    def __iter__(self): 
        self.x = 10
        return self
    # To move to next element
    def __next__(self): 
        # Store current value ofx 
        x = self.x 
        # Stop iteration if limit is reached 
        if x > self.limit: 
            raise StopIteration 
        # Else increment and return old value 
        self.x = x + 1; 
        return x 
    
for i in TestIterator(15): 
    print(i) 
```


```python
# different from python2
nums = [0, 1, 2, 3, 4]
weekdays = ['Mon', 'Tue', 'Wed', 'Thu', 'Fri']
print(list(zip(nums, weekdays)))
print(list(map(lambda x: x * x, nums)))
```


```python
import itertools as it

print(list(it.combinations([1, 2, 3], 2)))
#print(list(it.permutations(['a', 'b', 'c'])))
print(list(it.repeat(2, 5)))
```

# The usage of "_"

1. Refer to the last executed expression


```python
a = 20
a
```


```python
_
```

2. Ignoring the values


```python
x, _, y = (1, 2, 3)
print(x, y)
```


```python
x, *_, y = (1, 2, 3, 4, 5)
print(x, y)
```


```python
for _ in range(3):
    # do something for 10 times
    print('Coffee break is great!')
```

3. convention could be used for avoiding conflict with Python keywords (convention)

4. separating digits of numbers using *underscore* for readability


```python
a = 1_000_000
a
```

5. Magic method


```python
class A:
    def __init__(self, a):
        self.a = a
    def __len__(self):
        return 2
```

6. Private naming


```python
_internal_name = 'private_name' # private variable
_internal_version = '1.0' # private variable
class _Base: # private class
    _hidden_factor = 2 # private variable    
    def __init__(self, price):
        self._price = price    
    def _double_price(self): # private method
        return self._price * self._hidden_factor    
    def get_double_price(self):
        return self._double_price() 
```

7. “mangling” for class variable or functions

# Formatting a string

1. C-style string formatting


```python
name = "John"
age = 23
print("%s is %d years old." % (name, age))
```

'%s' can be used to covert any object to a string


```python
mylist = [1,2,3]
print("A list: %s" % mylist)
```

2. format (Python3+)


```python
name = "John"
age = 23
print("{} is {} years old.".format(name, age))
print()
```

3. The f-string expression (Python 3.6+)


```python
name = 'world'
print(f"hello {name}")
```

4. Template string (standard library)


```python
from string import Template
t = Template('Hey, $name!')
t.substitute(name=name)
```

# The end

If you think python is so great, please do not forget to check [What's the f*ck Python](https://github.com/satwikkansal/wtfpython)

Also, another surprise:


```python
import antigravity
```

Reference:

1. [Chip Huyen: Python is cool](https://github.com/chiphuyen/python-is-cool)
2. [Hackernoon: What makes the Python Cool.](https://hackernoon.com/what-makes-the-python-cool-426e4c576685)
3. [Hackernoon: Understanding the underscore( _ ) of Python](https://hackernoon.com/understanding-the-underscore-of-python-309d1a029edc)

3. [GeekforGeeks: 10 Interesting Python Cool Tricks](https://www.geeksforgeeks.org/10-interesting-python-cool-tricks/)

4. [RealPython: itertools in python3, By example](https://realpython.com/python-itertools/)

5. [RealPython: Python String Formatting Best Practices](https://realpython.com/python-string-formatting/)



Find python package:

1. [Awesome-python](https://github.com/vinta/awesome-python)

Python Coding guide

[Google: Python Coding Style](https://google.github.io/styleguide/pyguide.html)



