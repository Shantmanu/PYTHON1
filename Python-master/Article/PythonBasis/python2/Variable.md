# VI. Variables in Python #

## 1. The creation and assignment of variables##

In a Python program, a variable is represented by a variable name, which can be of any data type. The variable name must be a combination of uppercase and lowercase English, numbers and underscores (_), and cannot start with a number, such as:

```python
a=88
```

Here, `a` is a variable, representing an integer. Note that Python does not need to declare a data type. In Python, `=` is an assignment statement, which is the same as other programming languages, because Python does not need to declare data types when defining variables, so any data type can be assigned to a variable, and the same variable can be repeatedly assigned, and Can be of different data types.

![Variables in Python.png](http://upload-images.jianshu.io/upload_images/2136918-69affa6da83f1dfc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

This kind of language with variable types is called a dynamic language, and its counterpart is a static language. A static language must specify the variable type when defining a variable. If the type does not match when assigning a value, an error will be reported. For example, Java is a static language.


## 2. Pointing of Variables##

Let's take a look at this code and find that the last variable b printed out is `Hello Python`.

![Python variable points to.png](http://upload-images.jianshu.io/upload_images/2136918-052a908c25fcfc49.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

This is mainly because the variable a initially points to the string `Hello Python`, `b=a` creates the variable b, and the variable b also points to the string `Hello Python` pointed to by a. Finally, `a=123`, put The variable a points to `123` again, so the final output variable b is `Hello Python`

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-31-%E5%8F%98%E9%87%8F%E7%9A%84%E6%8C%87 %E5%90%91.png)

 

## 3. Multiple variable assignment##

Python allows multiple variables to be assigned at the same time. E.g:

```python
a = b = c = 1
```

The above example creates an integer object with a value of 1, and three variables are allocated to the same memory space.

Of course, multiple variables can also be specified for multiple objects. E.g:

```python
a, b, c = 1, 2, "liangdianshui"
```

In the above example, two integer objects 1 and 2 are assigned to variables a and b, and the string object "liangdianshui" is assigned to variable c.

