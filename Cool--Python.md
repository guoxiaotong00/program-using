#Python is cool

Zen of python:

```python
import this
```





List:

1. Lambda, map and reduce, filter

2. List

   1. Index and slicing

      ```python
      mylist[-1]
      mylist[::-1]
      mylist[::2]
      elems[-2::-2]
      ```

   2. Packing and swapping 

      ```python
      a = [1, 2, 3]
      x, y, z = a
      x, y = y, x
      ```

   3. Joining 

      ```python
      my_list = ['geeks', 'for', 'geeks'] 
      print(''.join(my_list))
      ```

   4. Flattening the list

      ```python
      import itertools
      a = [[1, 2], [3, 4], [5, 6]] 
      print(list(itertools.chain.from_iterable(a))) 
      ```

      Flatten nested list

      ```python
      nested_lists = [[1, 2], [[3, 4], [5, 6], [[7, 8], [9, 10], [[11, [12, 13]]]]]]
      flatten = lambda x: [y for l in x for y in flatten(l)] if type(x) is list else [x]
      flatten(nested_lists) 
      ```

      ```python
      list_of_lists = [[1], [2, 3], [4, 5, 6]]
      sum(list_of_lists, [])
      ```

   5. insert

      ```python
      elems = list(range(10))
      elems[1:1] = [0.2, 0.3, 0.5]
      ```

   6. Enumerate 

      ```python
      mylist = ['Monday','Tuesday','Thursday','Friday']
      for i,j in enumerate(mylist):
          print(i, j)
          
      ==>0 Monday
         1 Tuesday
         2 Thursday
         3 Friday
      ```

3. The usage of "_"

   - Refer to the last executed expression

   - Ignoring the values

     ```python
     x, _, y = (1, 2, 3)
     x, *_, y = (1, 2, 3, 4, 5)
     for _ in range(10):
         # do something for 10 times
         pass
     ```

   - Private naming

     ```python
     _internal_name = 'one_nodule' # private variable
     _internal_version = '1.0' # private variable
     class _Base: # private class
         _hidden_factor = 2 # private variable    
         def __init__(self, price):
             self._price = price    def _double_price(self): # private method
             return self._price * self._hidden_factor    
         def get_double_price(self):
             return self._double_price() 
     ```

   - convention could be used for avoiding conflict with Python keywords (convention)

     Like: class⎵

   - “mangling” for class variable or functions

     Like: ⎵⎵method

     ```python
     class A:
         def _single_method(self):
             pass    
         def __double_method(self): # for mangling
             passclass B(A):
         def __double_method(self): # for mangling
             pass
     ```

     alternative

     ```python
      __all__ = ['Class1', 'Class2']
         
     class Class1:
         pass
     class Class2:
         pass
     class Class3:
         pass
     ```

     

   - Magic method

     ```python
     class A:
         __init__(self, a):
             self.a = a
         __len__(self):
             return 2
     ```

   - separating digits of numbers using *underscore* for readability

     ```python
     a = 1_000_000
     ```

     

4. Construct the string

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
      print("{name} is {} years old.".format(name=name, age))
      print()
      ```

      

   3. The f-string expression (Python 3.6+)

   ```python
   expr = 'world'
   print(f'hello {expr=}')
   ```

   4. Template string (standard library)

      ```python
      from string import Template
      t = Template('Hey, $name!')
      t.substitute(name=name)
      ```

      

5. New if expression

   ```python
   if (n := len(a)) > 10:
       print(f"List is too long ({n} elements, expected <= 10)")
   ```

   

6. asyncio

7. iterator

   ```python
   iter([1, 2, 3, 4])
   ```

   `map` and `zip` return a iterator not a list (different from python2)

   ```python
   class Test: 
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
       
   for i in Test(15): 
       print(i) 
   ```

   permutation and combination

   ```python
   combinations([1, 2, 3], 2)
   combinations_with_replacement([1, 2], 2)
   
   bills = [20, 20, 20, 10, 10, 10, 10, 10, 5, 5, 1, 1, 1, 1, 1]
   list(it.combinations(bills, 3))
   ```

   

   ```python
   list(it.permutations(['a', 'b', 'c']))
   
   ```

   count

   ```python
   it.count(start=0.5, step=0.75)
   ```

   repeat

   ```python
   repeat(2, 5)
   ```

   flattening

   ```python
   list(it.chain.from_iterable([[1, 2, 3], [4, 5, 6]]))
   ```

   



A surprise:

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