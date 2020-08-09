# Three, naming convention

## 1. Module
* Try to use lowercase names for modules, keep the first letter lowercase, and try not to use underscores (unless there are multiple words and the number is small)

```python
# Correct module name
import decoder
import html_parser

# Deprecated module name
import Decoder
```

## 2. Class name
* The class name uses the CamelCase naming style, the first letter is capitalized, and the private class can start with an underscore

```Python
class Farm():
 pass

class AnimalFarm(Farm):
 pass

class _PrivateFarm(Farm):
 pass
```

* Put related classes and top-level functions in the same module. Unlike Java, there is no need to limit one class to one module.

## 3. Function

* Function names are all lowercase, if there are multiple words, separated by underscores

```python
def run():
 pass

def run_with_env():
 pass
```

* Private functions add an underscore before the function_

```python
class Person():

 def _private_func():
 pass
```

## 4. Variable name

* Try to lower case variable names, if there are multiple words, separate them with underscores

```python
if __name__ =='__main__':
 count = 0
 school_name =''
```

* Constants are in all capitals, if there are multiple words, use underscores to separate

```python
MAX_CLIENT = 100
MAX_CONNECTION = 1000
CONNECTION_TIMEOUT = 600
```

## 5、Constant##

* Constants are named in uppercase separated by underscores

```python
MAX_OVERFLOW = 100

Class FooBar:

 def foo_bar(self, print_):
 print(print_)

```
