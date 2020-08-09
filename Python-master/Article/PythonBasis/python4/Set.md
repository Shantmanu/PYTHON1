# 二、set #

Python's set is similar to other languages. It is a set of unordered and non-repetitive elements. Its basic functions include relationship testing and elimination of duplicate elements.

set is similar to dict, but set does not store value.


## 1. The creation of set##

To create a set, you need to provide a list as the input set

```python
set1=set([123,456,789])
print(set1)
```

Output result:

```
{456, 123, 789}
```

The incoming parameter `[123,456,789]` is a list, and the displayed `{456, 123, 789}` just tells you that there are 3 elements in this set, 456, 123, 789, and the order of display is the same as your parameter The order of the elements in the list is inconsistent, which also shows that the set is disordered.

Another point, we observe that the output result is in curly brackets. After previous learning, we can know that tuple (tuple) uses parentheses, list (list) uses square brackets, and dict (dictionary) uses big brackets. Brackets and dict are also unordered, but dict stores key-value pairs, while set can be understood as only storing key values.

Recall that when creating in a dict (dictionary), there are duplicate keys, which will be overwritten by the following key-value values, and duplicate elements are automatically filtered in the set.


```python
set1=set([123,456,789,123,123])
print(set1)
```

Output result:

```
{456, 123, 789}
```

## 2, set add element##

Elements can be added to the set through the add(key) method, which can be added repeatedly, but it will not have any effect

```python
set1=set([123,456,789])
print(set1)
set1.add(100)
print(set1)
set1.add(100)
print(set1)
```

Output result:
```
{456, 123, 789}
{456, 123, 100, 789}
{456, 123, 100, 789}
```

## 3. set delete element##

The elements in the set can be deleted through the remove(key) method

```python
set1=set([123,456,789])
print(set1)
set1.remove(456)
print(set1)
```

Output result:

```
{456, 123, 789}
{123, 789}
```


## 4、Use of set##

Because a set is a set of unordered and non-repeating elements, two sets can do union, intersection, difference, etc. in the mathematical sense.

![set set operation](http://upload-images.jianshu.io/upload_images/2136918-733b1d1071f772bd?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

example:

```python
set1=set('hello')
set2=set(['p','y','y','h','o','n'])
print(set1)
print(set2)

# Intersection (Find the same elements in two sets)
set3=set1 & set2
print('\nIntersection set3:')
print(set3)
# Union (combine the elements of the two sets and remove duplicate values)
set4=set1 | set2
print('\nUnion set4:')
print(set4)
# Difference
set5=set1-set2
set6=set2-set1
print('\nDifference set5:')
print(set5)
print('\nDifference set6:')
print( set6)


# Remove the duplicate elements in the massive list, and use hash to solve it, but it feels that the performance is not very high, and the set solution is still very good
list1 = [111,222,333,444,111,222,333,444,555,666] 
set7=set(list1)
print('\nRemove duplicate elements in the list set7:')
print(set7)

```

The result of running:

```
{'h','l','e','o'}
{'h','n','o','y','p'}

Intersection set3:
{'h','o'}

Union set4:
{'h','p','n','e','o','y','l'}

Difference set5:
{'l','e'}

Difference set6:
{'p','y','n'}

Remove duplicate elements in the list set7:
{555, 333, 111, 666, 444, 222}
```


