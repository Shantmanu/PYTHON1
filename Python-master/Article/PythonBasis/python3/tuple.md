# Two, tuple (tuple) #

## 1. What is a tuple ##

In the previous section, I just talked about an ordered list List. Now let's say that another kind of ordered list is called a tuple: tuple.

Tuple is very similar to List, but once the tuple is initialized, it cannot be modified.
In other words, tuples are immutable, so what does immutable mean?

Tuple immutability means that when you create a tuple, it cannot be changed, that is to say, it does not have methods such as append() and insert(), but it also has a method to obtain an index value. But it cannot be assigned.

So why should there be tuples?

That's because tuples are immutable, so the code is safer.

So it is recommended to use tuple instead of list as much as possible.



## 2. How to create a tuple ##

Tuple creation is very simple, just add elements in parentheses and separate them with commas.

```python
tuple1=('Two points of water','twowter','liangdianshui',123,456)
tuple2='Two points of water','twowter','liangdianshui',123,456
```

Create empty tuple

```python
tuple3=()
```

When the tuple contains only one element, you need to add a comma after the element

```python
tuple4=(123,)
```

If you don't add a comma, what you create is not a tuple, but the number ```123```.


This is because parentheses () can represent tuples and parentheses in mathematical formulas, which creates ambiguity.

So if you don't add a comma when there is only one element, the computer will not be able to recognize whether you want to perform integer or decimal operations or represent tuples.

Therefore, Python stipulates that in this case, the calculation is performed in parentheses, and the calculation result is naturally ```123```, and if you want to express a tuple, you need to add a comma.

Specifically, look at the output values ​​of tuple4 and tuple5 in the following figure

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-31-093847.jpg)







## 3. How to access tuple ##

The subscript index of the tuple also starts from 0, and the tuple can use the subscript index to access the value in the tuple.

```python
#-*-coding:utf-8-*-

tuple1=('Two points of water','twowter','liangdianshui',123,456)
tuple2='Two points of water','twowter','liangdianshui',123,456

print(tuple1[1])
print(tuple2[0])
```

Output result:

![Visit tuple](http://upload-images.jianshu.io/upload_images/2136918-edfb7c9ebc7d5ab0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)





## 4. Modify tuple ##

Some people may wonder when seeing this subtitle. Didn’t it take a long time to say that tuples are immutable?

Here is how to modify the tuple (tuple) again.

That's because the value of the element in a tuple is not allowed to be modified, but we can connect and combine the tuple, and modify the value of other lists to affect the value of the tuple.

Specifically, look at the following example:

```python
#-*-coding:utf-8-*-
list1=[123,456]
tuple1=('two water','twowater','liangdianshui',list1)
print(tuple1)
list1[0]=789
list1[1]=100
print(tuple1)
```

Output result:
```
('二点水','twowater','liangdianshui', [123, 456])
('二点水','twowater','liangdianshui', [789, 100])
```


As you can see, the tuple value output twice has changed. Let's see how the storage of tuple1 is.


![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-31-%E4%BF%AE%E6%94%B9tuple%E6%B5%81%E7%A8%8B %E5%9B%BE.png)


As you can see, tuple1 has four elements, the last element is a List, and there are two elements in the List.

When we modify the two elements `124` and `456` in the List list to `789` and `100`, judging from the output value of tuple1, it seems that it has indeed changed.

But what actually changes is not the element of the tuple, but the element of the list.

The list pointed to by the tuple at the beginning is not changed to another list. Therefore, the so-called "unchanged" of the tuple means that the point of each element of the tuple will never change. Note that the fourth element in tupe1 still points to the original list, which has not changed. What we modify is only the elements in the list.



## 5. Delete tuple (tuple) ##

The element value in the tuple is not allowed to be deleted, but we can use the del statement to delete the entire tuple

```python
#-*-coding:utf-8-*-

tuple1=('Two points of water','twowter','liangdianshui',[123,456])
print(tuple1)
del tuple1
```

## 6, tuple (tuple) operator##

As with strings, you can use `+` and `*` to perform operations between tuples. This means that they can be combined and copied, and a new tuple will be generated after the operation.

|Python Expression|Result|Description|
|-----------|-----|-----|
|len((1, 2, 3))|3|Calculate the number of elements|
|(1, 2, 3) + (4, 5, 6)|(1, 2, 3, 4, 5, 6)|Connect|
|('Hi!',) * 4|('Hi!','Hi!','Hi!','Hi!')|Copy|
|3 in (1, 2, 3)|True|Does the element exist|
|for x in (1, 2, 3): print(x)|1 2 3|Iteration|

## 7, tuple built-in functions##

|Method|Description|
|----|----|
|len(tuple)|Calculate the number of tuple elements|
|max(tuple)|Returns the maximum value of the element in the tuple|
|min(tuple)|Returns the minimum value of the element in the tuple|
|tuple(seq)|Convert a list to a tuple|


## 8, Example##

Finally, just like the list, here is an example. You can also try more to play the various ways of playing tuples.

```python
name1 = ('a bit of water','two points of water','three points of water','four points of water','five points of water')

name2 = ('1 point of water', '2 points of water', '3 points of water', '4 points of water', '5 points of water')

list1 = [1, 2, 3, 4, 5]

# Count the number of elements
print(len(name1))
# Connect, add two tuples
print(name1 + name2)
# Copy tuple
print(name1 * 2)
# Whether the element exists (whether the name1 tuple contains a little water element)
print('a bit of water' in name1)
# Maximum element
print(max(name2))
# Element minimum
print(min(name2))
# Convert list to tuple
print(tuple(list1))
```

The output is as follows:

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-31-101523.png)








