# Two, notes

## 1. Comments

### 1.1, block comment
There is a space after the "#" sign, and the paragraphs are separated by blank lines (the "#" sign is also required)

```python
# Block comment
# Block comment
#
# Block comment
# Block comment
```

### 1.2, line comment
Use at least two spaces to separate the statement, and be careful not to use meaningless comments

```python
# Correct writing
x = x + 1 # thicken the border by one pixel

# Not recommended writing (meaningless comment)
x = x + 1 # x plus 1
```

### 1.3, recommendations

* In key parts of the code (or more complicated places), write comments as much as possible if you can write comments

* More important comment sections, separated by multiple equal signs, can be more eye-catching and highlight the importance

```python
app = create_app(name, options)


# ====================================
# Do not add app routing behaviors such as get post here!!!
# ====================================


if __name__ =='__main__':
 app.run()
```

## 2. Docstring
Docstring as a document generally appears in the head of the module, function and class, so that the document can be obtained through the object's \_\_doc\_\_ object in python.
The editor and IDE can also give automatic prompts based on the Docstring.

* Document comments start and end with """, the first line does not wrap, if there are multiple lines, the last line must wrap, the following is an example of Google's docstring style

```python
# -*- coding: utf-8 -*-
"""Example docstrings.

This module demonstrates documentation as specified by the `Google Python
Style Guide`_. Docstrings may extend over multiple lines. Sections are created
with a section header and a colon followed by a block of indented text.

Example:
 Examples can be given using either the ``Example`` or ``Examples``
 sections. Sections support any reStructuredText formatting, including
 literal blocks::

 $ python example_google.py

Section breaks are created by resuming unindented text. Section breaks
are also implicitly created anytime a new section starts.
"""
```

* Don't copy the function definition prototype in the documentation comments, but describe its specific content, explain specific parameters and return values, etc.

```python
# Not recommended way of writing (do not write nonsense such as function prototypes)
def function(a, b):
 """function(a, b) -> list"""
 ... ...


# Correct writing
def function(a, b):
 """Calculate and return the average value of the data from a to b"""
 ... ...
```

* The description of function parameters, return values, etc. adopts numpy standards, as shown below

```python
def func(arg1, arg2):
 """Write a one-sentence summary of the function here (eg: calculate the average value).

 Here is the specific description.

  parameter
 ----------
 arg1: int
 Specific description of arg1
 arg2: int
 Specific description of arg2

 return value
 -------
 int
 Specific description of return value

 See
 --------
 otherfunc: other related functions etc...

 Example
 --------
 The example uses the doctest format, and the code after `>>>` can be automatically run as a test case by the document testing tool

 >>> a=[1,2,3]
 >>> print [x + 3 for x in a]
 [4, 5, 6]
 """
```


* Document comments are not limited to Chinese and English, but do not mix Chinese and English

* Document comments are not as long as possible, usually one or two sentences can make the situation clear

* Modules, public classes, and public methods, if you can write documentation comments, you should try to write documentation comments


