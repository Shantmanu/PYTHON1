> Original: http://stackoverflow.com/questions/231767/the-python-yield-keyword-explained
>
> Note: This is a translation of a popular post on stackoverflow

## Problem##

What is the purpose of the Python keyword yield? What is it for?

For example, I am trying to understand the following code:

```Python
def node._get_child_candidates(self, distance, min_dist, max_dist):
 if self._leftchild and distance-max_dist <self._median:
 yield self._leftchild
 if self._rightchild and distance + max_dist >= self._median:
 yield self._rightchild
```


The following is the call:


```python
result, candidates = list(), [self]
while candidates:
 node = candidates.pop()
 distance = node._get_dist(obj)
 if distance <= max_dist and distance >= min_dist:
 result.extend(node._values)
 candidates.extend(node._get_child_candidates(distance, min_dist, max_dist))
return result
```

What happens when ```_get_child_candidates``` is called? Returned a list? Returned an element? Has it been called repeatedly? When does this call end?


## Reply

In order to understand what a yield is, you must understand what a generator is. Before understanding generators, let's get closer to iteration.

**Iterable object**

When you create a list, you can read the list item by item, which is called an iterable object:

```Python
>>> mylist = [1, 2, 3]
>>> for i in mylist:
... print(i)
1
2
3
```

mylist is an iterable object. When you use a list comprehension to build a list, you create an iterable object:

```python
>>> mylist = [x*x for x in range(3)]
>>> for i in mylist:
... print(i)
0
1
4
```

All you can use the ```for .. in ..``` syntax is called an iterator: list, string, file...you use them often because you can read the elements as you want, But you store all the values ​​in the memory, this method is not what you want if you have a lot of data.

**Builder**

The generator can be iterated, but you can only read it once, because it does not put all the values ​​in memory, it generates data in real time:

```python
>>> mygenerator = (x*x for x in range(3))
>>> for i in mygenerator:
... print(i)
0
1
4
```

It doesn't look any different except replacing [] with (). However, you cannot use ```for i in mygenerator``` again, because the generator can only be iterated once: first calculate 0, then continue to calculate 1, then calculate 4, one by one...

**yield keyword**

Yield is a keyword similar to return, except that this function returns a generator.

```python
>>> def createGenerator():
... mylist = range(3)
... for i in mylist:
... yield i*i
...
>>> mygenerator = createGenerator() # create a generator
>>> print(mygenerator) # mygenerator is an object!
<generator object createGenerator at 0xb7555c34>
>>> for i in mygenerator:
... print(i)
0
1
4
```

This example is useless, but it lets you know that this function will return a large number of values ​​that you only need to read once.

In order to be proficient in yield, you must understand: when you call this function, the code inside the function is not executed immediately, this function just returns a generator object, isn't it a bit strange?

So, when does the code inside the function execute? When you use for to iterate.

Now it's the key point!

In the first iteration, your function will execute, from the beginning to the yield keyword, and then return the value after yield as the return value of the first iteration. Then, every time you execute this function, it will continue to execute the one you defined inside the function The next time in the loop, return that value until there is nothing to return.

If the yield keyword is not defined inside the generator, then the generator is considered empty. This situation may be because the loop is gone, or the if/else condition is not met.

**Back to your code**

Builder:

```Python
# Here you create the method of the node object that will return the generator
def node._get_child_candidates(self, distance, min_dist, max_dist):

 # Here is the code that will be called each time you use the generator object:

 # If there is still a child of the node object on its left
 # AND if distance is ok, return the next child
 if self._leftchild and distance-max_dist <self._median:
 yield self._leftchild

 # If there is still a child of the node object on its right
 # AND if distance is ok, return the next child
 if self._rightchild and distance + max_dist >= self._median:
 yield self._rightchild

 # If the function arrives here, the generator will be considered empty
 # there is no more than two values: the left and the right children
```


Caller:

```Python
# Create an empty list and a list with the current object reference
result, candidates = list(), [self]

# Loop on candidates (they contain only one element at the beginning)
while candidates:

 # Get the last candidate and remove it from the list
 node = candidates.pop()

 # Get the distance between obj and the candidate
 distance = node._get_dist(obj)

 # If distance is ok, then you can fill the result
 if distance <= max_dist and distance >= min_dist:
 result.extend(node._values)

 # Add the children of the candidate in the candidates list
 # so the loop will keep running until it will have looked
 # at all the children of the children of the children, etc. of the candidate
 candidates.extend(node._get_child_candidates(distance, min_dist, max_dist))

return result
```

This code contains several small parts:

* We iterate over a list, but the list continues to expand during the iteration. It is a concise way to iterate these nested data, even if it is a bit dangerous, because it may lead to infinite iteration. `candidates.extend(node._get_child_candidates(distance, min_dist, max_dist))` exhausts all the values ​​of the generator, but while is constantly generating new generators, they will produce different values ​​from the last time, since it has no effect To the same node.
* `extend()` is an iterator method that acts on the iterator and appends the parameters to the iterator.


Usually we pass it a list parameter:


```Python
>>> a = [1, 2]
>>> b = [3, 4]
>>> a.extend(b)
>>> print(a)
[1, 2, 3, 4]
```


But in your code is a generator, which is good because:

* You don't have to read all the values ​​twice
* You can have many child objects, but you don't have to call them all stored in memory.


And this works well, because Python doesn't care whether a method parameter is a list. Python only wants it to be iterable, so this parameter can be a list, tuple, string, generator... This is called `duck typing`, which is one of the reasons why Python is so great, but it is already another One question...

You can stop here and take a look at some advanced uses of the generator:

**Exhaustion of control generators**

```Python
>>> class Bank(): # let's create a bank, building ATMs
... crisis = False
... def create_atm(self):
... while not self.crisis:
... yield "$100"
>>> hsbc = Bank() # when everything's ok the ATM gives you as much as you want
>>> corner_street_atm = hsbc.create_atm()
>>> print(corner_street_atm.next())
$100
>>> print(corner_street_atm.next())
$100
>>> print([corner_street_atm.next() for cash in range(5)])
['$100','$100','$100','$100','$100']
>>> hsbc.crisis = True # crisis is coming, no more money!
>>> print(corner_street_atm.next())
<type'exceptions.StopIteration'>
>>> wall_street_atm = hsbc.create_atm() # it's even true for new ATMs
>>> print(wall_street_atm.next())
<type'exceptions.StopIteration'>
>>> hsbc.crisis = False # trouble is, even post-crisis the ATM remains empty
>>> print(corner_street_atm.next())
<type'exceptions.StopIteration'>
>>> brand_new_atm = hsbc.create_atm() # build a new one to get back in business
>>> for cash in brand_new_atm:
... print cash
$100
$100
$100
$100
$100
$100
$100
$100
$100
...
```


This is useful for controlling access to some resources.

**Itertools, your best friend**

itertools contains many special iteration methods. Have you ever thought about copying an iterator? Concatenate two iterators? Group nested lists? No need to create a new zip/map of the list?

Just import itertools

Need an example? Let's look at the possible sequence of the 4 horses in the race:

```python
>>> horses = [1, 2, 3, 4]
>>> races = itertools.permutations(horses)
>>> print(races)
<itertools.permutations object at 0xb754f1dc>
>>> print(list(itertools.permutations(horses)))
[(1, 2, 3, 4),
 (1, 2, 4, 3),
 (1, 3, 2, 4),
 (1, 3, 4, 2),
 (1, 4, 2, 3),
 (1, 4, 3, 2),
 (2, 1, 3, 4),
 (2, 1, 4, 3),
 (2, 3, 1, 4),
 (2, 3, 4, 1),
 (2, 4, 1, 3),
 (2, 4, 3, 1),
 (3, 1, 2, 4),
 (3, 1, 4, 2),
 (3, 2, 1, 4),
 (3, 2, 4, 1),
 (3, 4, 1, 2),
 (3, 4, 2, 1),
 (4, 1, 2, 3),
 (4, 1, 3, 2),
 (4, 2, 1, 3),
 (4, 2, 3, 1),
 (4, 3, 1, 2),
 (4, 3, 2, 1)]
```

**Understand the internal mechanism of iterators**

Iteration is a process of implementing iterable objects (implementing the `__iter__()` method) and iterators (implementing the `__next__()` method). An iterable object is any object from which you can obtain an iterator. Iterators are objects that allow you to iterate over iterable objects.
