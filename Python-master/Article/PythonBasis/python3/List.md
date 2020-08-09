# One, List (List) #

## 1. What is List (List)

List is a built-in data type of Python. It is an ordered collection, elements can be added and deleted at any time.

Then why is there a List?

Let's use an example to illustrate.

Now there is a team who wants to go out to play and sign up first. If we use the knowledge we have learned before, then use a string variable to record them all.

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-31-080527.png)

But this is too cumbersome and unsightly.

In programming, we must learn to be lazy and avoid "repetitive work." If there are a hundred members, then you copy and paste in time, which will bother you.

The list can be used at this time.

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-31-080835.png)

In this way, one line of code can store more than N names.


## 2. How to create a List (list) ##

It can be analyzed from the above example that the format of the list is like this.

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-31-081342.png)

In fact, the list is the data enclosed in square brackets `[]`, and each data in it is called an element. Use commas to separate each element.

And the data elements of the list are not necessarily the same data type.

such as:

```python
list1=['二点水','twowter','liangdianshui',123]
```

There are string types and integer types.

Let's try to print it out and see what the printed result is.

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-31-081912.png)

The results are as follows:

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-31-081951.png)


## 3. How to access the value in List##

Just like the example at the beginning, sometimes we don’t need to print out the names of all the people, sometimes we need to know who is the third person who signed up? Who are the top two applicants?

So how to get it out of the list?

To put it another way, how do I access the values ​​in the list?

At this time, we can access the values ​​in the list through the subscript index of the list, and you can also use square brackets to intercept characters.

E.g:

```python
name = ['a bit of water','two points of water','three points of water','four points of water','five points of water']

# Access the list by index
print(name[2])
# Use square brackets to intercept the data in the list
print(name[0:2])
```

Output result:

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-31-090321.png)

Obviously, we need to know who is the third one in the list of `name`? Just use `name[2]`.

Here you will ask, why is it 2 and not 3?

This is because in the world of programming, all start from 0, not from 1 in our daily habits.

So you need to know who the third one is?

That is `name[2]` on it.

From the example, we also printed the result of `name[0:2]`.

Judging from the printing result, only the first and second element contents are printed.

There may be questions here?

Why don't you print the first three? Doesn't it mean that 2 is the third?

That's because this is the interval of **left closed and right open**.

So `name[0:2]` means to start from the 0th and get to the second, but not including the second.

Again, for a better understanding, you can try more and play more programming.

So you can try the following various methods:

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-31-091524.png)

Look at the output:

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-31-091624.png)

Based on the output results and the knowledge mentioned above, it is easy to understand some of the usages.




 ## 4. How to update the List (list) ##

It is the example from the beginning. We recorded the name of the applicant with the code. Then there may be newcomers joining in the future, or we may find that the name was wrong at the beginning and want to modify it.

What to do at this time?

At this time, you can modify or update the data items of the list through the index, or you can use the append() method to add list items.

```python
name = ['a bit of water','two points of water','three points of water','four points of water','five points of water']


# Modify or update the data items of the list through the index
name[1]='2 points of water'
print(name)

# Use append() method to add list items
name.append('Six Points of Water')
print(name)
```

Output result:

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-31-092406.png)





## 5. How to delete elements in List##

In this case, someone will definitely withdraw halfway.

Then we need to remove his name from the list.

At this time, use the del statement to delete the elements of the list

```python
name = ['a bit of water','two points of water','three points of water','four points of water','five points of water']

print(name)

# Use the del statement to delete elements of the list
del name[3]
print(name)
```

Output result:

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-31-092705.png)

If you look at the output, there is no longer the data `四点水` in the list. The proof has been deleted successfully.






## 6, List (list) operator##

The operators of the list pairs `+` and `*` are similar to strings. The `+` sign is used for combined lists, and the `*` sign is used for repeated lists.

|Python Expression|Result|Description|
|-----------|-----|-----|
|len([1, 2, 3])|3|Calculate the number of elements|
|[1, 2, 3] + [4, 5, 6]| [1, 2, 3, 4, 5, 6]| Combination|
|['Hi!'] * 4|['Hi!','Hi!','Hi!','Hi!']|Copy|
|3 in [1, 2, 3]|True|Does the element exist in the list|
|for x in [1, 2, 3]: print x,|1 2 3|Iteration|


## 7. List (List) Functions & Methods##

|Functions&Methods|Description|
|----|----|
|len(list)|Number of list elements|
|max(list)|Returns the maximum value of list elements|
|min(list)|Returns the minimum value of list elements|
|list(seq)|Convert a tuple to a list|
|list.append(obj)|Add a new object at the end of the list|
|list.count(obj)|Count the number of times an element appears in the list|
|list.extend(seq)|Append multiple values ​​in another sequence at the end of the list at once (extend the original list with the new list)|
|list.index(obj)|Find the index position of the first match of a value from the list|
|list.insert(index, obj)|Insert the object into the list|
|list.pop(obj=list[-1])|Remove an element from the list (the last element by default), and return the value of the element|
|list.remove(obj)|Remove an element from the list (the parameter is the element in the list), and does not return any value|
|list.reverse()|Reverse the elements in the list|
|list.sort([func])|Sorting the original list|


## 8, Example##


Finally, through an example to familiarize yourself with the operation of List

example:

```python
#-*-coding:utf-8-*-
#-----------------------Use of list----------------------- -----------

# 1. For a product, users of the product need to be listed, then a list can be used to indicate
user=['liangdianshui','twowater','二点水']
print('1. Product user')
print(user)

# 2. If you need to count how many users there are, then the number of elements in the list that the len() function can get
len(user)
print('\n2. Count how many users are there')
print(len(user))

# 3. At this time, what if you need to know the specific user? You can use the index to access the elements at each position in the list, the index is 0 from the beginning
print('\n3. View specific users')
print(user[0]+','+user[1]+','+user[2])

# 4. Suddenly a new user came, and we need to add a user to the end of the original list
user.append('茵茵')
print('\n4. Add a new user at the end')
print(user)

# 5. A new user is added, but this user is a VIP-level student and needs to be placed first, and can be inserted into the specified position through the insert method
# Note: When inserting data, pay attention to whether it is out of bounds, the index cannot exceed len(user)-1
user.insert(0,'VIP user')
print('\n5. Add user to specified location')
print(user)

# 6. Suddenly I found out that I made a mistake before, "yinyin" is a "VIP user", therefore, "yinyin" needs to be deleted; pop() deletes the element at the end of the list
user.pop()
print('\n6. Delete the last user')
print(user)

# 7. After a period of time, the user "liangdianshui" did not play this product and deleted his account
# So you need to delete the element at the specified position, use the pop(i) method, where i is the index position
user.pop(1)
print('\n7. Delete the list element at the specified position')
print(user)

# 8. The user "liangdianshui" wants to modify his nickname
user[2]='Three points of water'
print('\n8. Replace an element with another element')
print(user)

# 9. It seems not good enough to save the user's nickname alone, it is best to put the account in it too
# The account number here is an integer type, which is different from the string type of the nickname, but the data type of the elements in the list can be different
# And the list element can also be another list
newUser=[['VIPUser',11111],['twowater',22222],['三点水',33333]]
print('\n9. List data of different element types')
print(newUser)

```

![Use of list](http://upload-images.jianshu.io/upload_images/2136918-65d31cae9f8bb34d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


