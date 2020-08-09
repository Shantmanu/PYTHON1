# 2. print() function #

Let me talk about the `print()` function first. If you are a novice, you may not know much about the function. It does not matter. You only need to understand its components and functions. The function will be explained in detail later.

The `print()` function consists of two parts:

1. Command: print
2. The execution target of the instruction, the content in parentheses after print

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-17-074454.png)

The function of `print()` is to let the computer display the result of the instruction you gave it on the screen terminal. The instructions here are what you have in the `print()` function.

For example, in the previous chapter, our first Python program printed `print('Hello Python')`

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-17-080241.png)

Its execution process is as follows:

1. Send a command to the interpreter to print "Hello Python" 
2. The parser interprets the code into machine language that the calculator can understand
3. Print the result after the computer is executed

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-17-083751.png)

Someone may ask here, why do we need to add single quotes instead of `print(Hello Python)` directly?

If you have such questions during the code writing process, it is best to write the code directly and verify it yourself.

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-08-17-094034.png)

Obviously, after removing the single quotation marks, the running result is marked in red (error), which proves that this is not possible.

The main reason is that this does not conform to Python's grammatical rules. After removing the single quotes, the Python interpreter can't understand what you are writing.

Therefore, the error of `SyntaxError: invalid syntax` is reported, which means: syntax error. Explain that your sentence is out of order.
















