# Three, the basic data types of Python #

## 1. String##

The English string is a data type that can be seen everywhere in Python. The identification of strings is also very simple, which is enclosed in "quotation marks".

Quotation marks include single quotes `''`, double quotes `" "` and triple quotes `''''''`, such as `'abc'`, `"123"`, etc.

Please note here that the single quotation mark `''` or double quotation mark `""` itself is only a representation, not part of the string. Therefore, the string `'abc'` only has 3 characters of a, b, and c.

If you are good at thinking, you will definitely ask?

Why are there single quotation marks `''`, double quotation marks `" "` and triple quotation marks `''''''` Ah, it's just a matter of direct decision-making, so troublesome, so many rules express the same thing. Well?

Yes, in general, a grammar is best represented by only one rule. There are three different representations of strings, which proves there are reasons.

So let's first look at these three ways to define a string of the same content, and then print it out to see what it is.

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-29-071320.png)

The printed result is the same.

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-29-071403.png)

What if our string is not `two dots of water`, but `two dots of water`?

This will directly report an error.

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-29-071800.png)

But note that using single quotation marks `''` does not work, but using double quotation marks `" "` is fine.

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-29-072459.png)

The printed result is also as expected:

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-29-072523.png)

As for the triple quotation marks, the same is true. If the string content contains double quotation marks, the same error will be reported. Then you can use triple quotes at this time.

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-29-072701.png)

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-29-072829.png)

Then the string defined by single quotation marks and double quotation marks cannot express such content?

No, you can use escape characters.

For example, single quotation marks can be represented by `\'`, and double quotation marks can be represented by `\"`.

Note that here is the backslash `\`, not the slash `/`.

After understanding, test it directly:

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-29-073544.png)

The results are as follows:

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-29-073601.png)

Finally, it is also mentioned that the triple quotes `''''''` can branch directly.

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-29-074157.png)

operation result:

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-29-074209.png)






## 2, Integer##

Integer English is integer. The integers in the code are the same as the integers we usually know, including positive integers, negative integers and zero, which are numbers without decimal points.

Python can handle integers of any size, for example: `1`, `100`, `-8080`, `0`, etc.

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-29-075017.png)

operation result:

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-29-075046.png)

Of course, be aware that if the number is enclosed in quotation marks, it belongs to a string, not an integer. For example, `'100'`, this 100 is a string, not an integer.

In the real world, we usually do calculations for integers, so the code world is the same, integers can be directly added, subtracted, multiplied, and divided.

such as:

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-29-075748.png)

Program running results:

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-29-075806.png)

Here is a reminder everyone, look at the above example, have you found anything?

Look at the result printed by `int4`, it is `0.5`, which is a decimal.

And what is our definition of integer above?

It is a number without a decimal point.

So `int4` is definitely not an integer.

Here we can use the `type()` function to check the type.

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-30-032745.png)

The results are as follows:

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-30-032826.png)

You can see that `int4` is of type float, and `int1`, `int2`, and `int3` are all int integer types.

So what type of float is it?

Float is a floating-point number type, which we will talk about below.

Before talking about floating-point numbers, you can see what Python arithmetic operators are and have an impression.

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-30-034538.png)





## 3. Floating point number##

The English name of a floating point number is float, which refers to a number with decimals.

There are many similarities between floating-point numbers and integers, but floating-point numbers are the most tormenting and the most difficult to understand.

Just like what the world-class boss Herb Sutter said: “People in the world can be divided into three categories: one is who knows that they don’t understand floating-point arithmetic; Few expert-level figures, they want to know if it is possible for them to finally fully understand floating-point operations."

Why do you say that?

Look at the following example, just like integers, just basic floating point addition operations.

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-30-081702.png)

However, the calculation result may not be acceptable to beginners.

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-30-081922.png)

For the first one, `0.55+0.41` is equal to 0.96, and the calculation results are exactly the same. But for the last two, you will find out how there are so many zeros.

This is because the computer's expression of floating-point numbers is inherently imprecise. What is stored in the computer is a binary number. Binary cannot accurately express some numbers and can only be very close to this number.

So we have to be careful when doing operations on floating point numbers and comparing sizes.




## 4、Boolean value##

The representation of Boolean value and Boolean algebra is exactly the same. A Boolean value has only two values ​​of `True` and `False`, either `True` or `False`. In Python, you can directly use True and False to represent Boolean values (Please pay attention to case), it can also be calculated by Boolean operation.

Boolean values ​​can be operated on with `and`, `or` and `not`.

The `and` operation is an AND operation, and the result of the and operation is True only if everything is True.

The `or` operation is an OR operation. As long as one of them is True, the result of the or operation is True.

The `not` operation is a negation operation. It is a unary operator that turns True into False and False into True.



## 5、Null value##

Basically every programming language has its own special value-null value. In Python, it is represented by None







