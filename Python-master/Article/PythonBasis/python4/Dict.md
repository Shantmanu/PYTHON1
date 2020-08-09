# 一、Dictionary (Dictionary) #

## 1. What is a dict (dictionary) ##

In the last chapter, we learned about lists and tuples to represent ordered sets.

And when we talked about lists, we used lists to store the names of users.

```python
name = ['a bit of water','two points of water','three points of water','four points of water','five points of water']
```

So if we want to add the phone number to contact these children's shoes for convenience, what should we do?

Use list to solve this problem:

```python
name = [['A bit of water', '131456780001'], ['Two points of water', '131456780002'], ['Three points of water', '131456780003'], ['Four points of water', '131456780004'], ['Five points of water', '131456780005']]
```

But this is very inconvenient. We recorded the phone numbers just to get in touch with these children's shoes in time for anything.

If we use a list to store these, the longer the list, the longer it will take us to find it.

At this time, it can be represented by a dict (dictionary). Python has a built-in dictionary (dict). The full name of dict is dictionary. If you have learned Java, a dictionary is equivalent to a map in JAVA, using key-value storage. Has extremely fast search speed.

```python
name = {'a bit of water': '131456780001','two points of water': '131456780002','three points of water': '131456780003','four points of water': '131456780004','five points of water': '131456780005 '}
```



## 2. The creation of dict (dictionary)##

Dictionary is another variable container model, and can store any type of object.

Each key-value (key=>value) pair of the dictionary is separated by a colon (:), and each pair is separated by a comma (,). The entire dictionary is enclosed in curly braces ({}). The format is as follows:

```python
dict = {key1: value1, key2: value2}
```

Note: The key must be unique, but the value need not. The value can take any data type, but the key must be immutable.

Create a dict (dictionary) instance:

```python
dict1={'liangdianshui':'111111' ,'twowater':'222222' ,'two points of water':'333333'}
dict2={'abc':1234,1234:'abc'}
```



## 3. Access dict (dictionary) ##

We know how to create a list, and return to the question raised at the beginning. Why can we use a dictionary to quickly find out the phone number of a child's shoe?



```python
name = {'a bit of water': '131456780001','two points of water': '131456780002','three points of water': '131456780003','four points of water': '131456780004','five points of water': '131456780005 '}

print(name['Two dots of water'])
```


Output result:

```
131456780002
```

As you can see, if you know a person’s name, which is the key value, you can quickly find his corresponding phone number, which is Value.

One thing to note here is: If this key is not in the dictionary, an error will be reported.



## 4. Modify dict (dictionary) ##

The way to add new content to the dictionary is to add new key/value pairs, modify or delete existing key/value pairs

```python
#-*-coding:utf-8-*-
dict1={'liangdianshui':'111111' ,'twowater':'222222' ,'two points of water':'333333'}
print(dict1)
# Add a key-value pair
dict1['jack']='444444'
print(dict1)
# Modify key-value pairs
dict1['liangdianshui']='555555'
print(dict1)
```

Output result:

```
{'liangdianshui': '111111','twowater': '222222','二点水': '333333'}
{'liangdianshui': '111111','twowater': '222222','二点水': '333333','jack': '444444'}
{'liangdianshui': '555555','twowater': '222222','二点水': '333333','jack': '444444'}
```

## 5. Delete dict (dictionary) ##

Use `del` to delete an element in dict (dictionary), or delete dict (dictionary)

All elements in the dictionary can be cleared by calling the `clear()` method

```python
#-*-coding:utf-8-*-
dict1={'liangdianshui':'111111' ,'twowater':'222222' ,'two points of water':'333333'}
print(dict1)
# Through the key value, delete the corresponding element
del dict1['twowater']
print(dict1)
# Delete all elements in the dictionary
dict1.clear()
print(dict1)
# Delete dictionary
del dict1
```

Output result:

```
{'liangdianshui': '111111','twowater': '222222','二点水': '333333'}
{'liangdianshui': '111111','Two dots of water': '333333'}
{}
```

## 6. Matters needing attention when using dict (dictionary)##

(1) dict (dictionary) is not allowed to create a key twice, but when creating a dict (dictionary), if a key value is assigned twice, the last assigned value will prevail

E.g:

```python
#-*-coding:utf-8-*-
dict1={'liangdianshui':'111111' ,'twowater':'222222' ,'two water':'333333','twowater':'444444'}
print(dict1)
print(dict1['twowater'])
```

Output result:

```
{'liangdianshui': '111111','twowater': '444444','二点水': '333333'}
444444
```


(2) dict (dictionary) keys must be immutable, but the keys can be used as numbers, strings or tuples, but lists cannot be used

E.g:

```python
#-*-coding:utf-8-*-
dict1={'liangdianshui':'111111' ,123:'222222' ,(123,'tom'):'333333','twowater':'444444'}
print(dict1)
```

Output result:

```
{'liangdianshui': '111111', 123: '222222', (123,'tom'): '333333','twowater': '444444'}
```

(3) The internal storage order of the dict has nothing to do with the order in which the keys are placed

Compared with list, dict has the following characteristics:

* The search and insert speed is extremely fast, and will not slow down as the key increases

* Need to take up a lot of memory and waste a lot of memory

The opposite of list:

* The time to find and insert increases with the increase of elements

* Small footprint, little waste of memory


## 7. Functions and methods of dict (dictionary)##

|Methods and Functions|Description|
|---------|--------|
|len(dict)|Calculate the number of dictionary elements|
|str(dict)|Printable string representation of output dictionary|
|type(variable)|Returns the input variable type, if the variable is a dictionary, it returns the dictionary type|
|dict.clear()|Delete all elements in the dictionary|
|dict.copy()|Returns a shallow copy of a dictionary|
|dict.values()|Return all values ​​in the dictionary as a list|
|popitem()|Randomly return and delete a pair of keys and values ​​in the dictionary|
|dict.items()|Return a traversable (key, value) tuple array as a list|







