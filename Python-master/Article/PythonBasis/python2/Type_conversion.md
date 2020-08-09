# Five, basic data type conversion #

There are several methods for basic data type conversion in Python.

|Method|Description|
|-----|------|
|int(x [,base ]) | Convert x to an integer |
|float(x) | Convert x to a floating point number |
|complex(real [,imag ])| Create a complex number |
|str(x) | Convert object x to string |
|repr(x) | Convert object x to expression string |
|eval(str) | Used to calculate the valid Python expression in a string and return an object |
|tuple(s) | Convert sequence s into a tuple |
|list(s) | Convert the sequence s to a list |
|chr(x) | Convert an integer to a character |
|unichr(x) | Convert an integer to a Unicode character |
|ord(x) | Convert a character to its integer value |
|hex(x) | Convert an integer to a hexadecimal string |
|oct(x) | Convert an integer to an octal string |

Note: In Python 3, there is only one integer type int, which is represented as a long integer, and there is no Long in python2.

Here we can try these function methods.

For example, the `int()` function converts the string type that conforms to the rule into an integer.

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-30-091547.png)

Output result:

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-30-091648.png)

Note that this is a string type that conforms to the rules. If the string is in literal form, it cannot be coerced by the `int()` function.

There are also strings in decimal form that cannot be converted with the `int()` function.

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-31-064739.png)

This conversion will report an error.

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-31-064811.png)

But this does not mean that floating-point numbers cannot be converted into integers, but that strings in decimal form cannot be forced into strings.

Floating point numbers can still be converted by the `int()` function.

such as:

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-31-065336.png)

Output result:

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-31-065407.png)

But you will find that the result is 88, and 0.88 after the decimal point is removed.

This is because the `int()` function converts data to integers. If it is a floating-point number converted to an integer, the `int()` function will do the rounding process and only take the integer part. So the output result is 88.

The rest of the methods are not listed one by one, as long as you use more and try more, these methods will gradually become familiar. And if you are a beginner, you can play with each method, write it, write it casually, and run it to see the results. Anyway, your computer won't be broken because of this.










