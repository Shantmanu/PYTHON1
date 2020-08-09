# Four, string encoding issues #

We all know that computers can only process numbers. If you want to process text, you must first convert the text to numbers. The earliest computers used 8 bits as a byte in the design. Therefore, the largest integer that a byte can represent is 255 (binary 11111111 = decimal 255), and 0-255 are used to represent the size Write English letters, numbers and some symbols. This code table is called ASCII code. For example, the code of uppercase letter A is 65, and the code of lowercase letter z is 122.

If you want to express Chinese, obviously one byte is not enough. At least two bytes are needed, and it cannot conflict with the ASCII encoding. Therefore, China has developed the GB2312 encoding to incorporate Chinese.

Similarly, other languages ​​such as Japanese and Korean have this problem. In order to unify the encoding of all characters, Unicode came into being. Unicode unifies all languages ​​into a set of encodings, so that there will be no more garbled problems.

Unicode usually uses two bytes to represent a character. The original English encoding changes from single-byte to double-byte. You only need to fill all the high bytes with 0.

Because Python was born earlier than the release of the Unicode standard, the earliest Python only supports ASCII encoding, and the ordinary string'ABC' is ASCII encoded inside Python.

Python later added support for Unicode, and strings represented by Unicode are represented by `u'...'`.

However, in the latest version of Python 3, strings are encoded in Unicode, which means that Python strings support multiple languages. Just like the example above, my code can display normally without adding `u'...'`.

However, because the Python source code is also a text file, when your source code contains Chinese, you must specify the UTF-8 encoding when saving the source code. When the Python interpreter reads the source code, in order to make it read in UTF-8 encoding, we usually write these two lines at the beginning of the file:

```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-
```

The first line of comment is to tell the Linux/OS X system that this is a Python executable program, and the Windows system will ignore this comment;

The second line of comment is to tell the Python interpreter to read the source code according to UTF-8 encoding, otherwise, the Chinese output you write in the source code may be garbled.

Affirmed that UTF-8 encoding does not mean that your .py file is UTF-8 encoded, you must and make sure that the text editor is using UTF-8 without BOM encoding


