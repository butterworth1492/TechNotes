# Packages
```
# For way more details: https://realpython.com/python-import/

world/
    __init__.py
      from . import africa

world/africa
    __init__.py
    zimbabwe.py

world/europe
    __init__.py
        from . import greece
        from . import norway
    greece.py
    norway.py
    spain.py


>>> import world
    # ‘world’ package imported.
    # ‘africa’ subpackage auto-imported  (but not zimbabwe)

>>> from world import europe
    # ‘europe’ package imported
    # ‘greece’ and ‘norway’ subpackages auto-imported (but not spain)

>>> import world.africa.zimbabwe
    # ‘zimbabwe’ subpackage imported

>>> import world.europe.spain
    # ‘spain’ subpackage imported
```

# Loops / Conditionals
```
>>> while True:
>>>   do_something()
```

```
>>> if True:
>>>   do_something()
>>> elif False:
>>>   do_something_else()
>>> else:
>>>   give_up()
```

```
>>> for i in range(0,5):
>>>   print(i)
```

```
>>> for l in "bigstring":
>>>   print(l, end='')
```



# Situational Awareness

Module name.  (The name of the file by default)
```
if  __name__ == “__main__”:      
  do_something()
```

File name
```
>>> print( __file__ )
c:\python37\lib\io.py
```

Current file name and line number
```
>>> from inspect import currentframe, getframeinfo
>>> frameinfo = getframeinfo(currentframe())
>>> print(frameinfo.filename, frameinfo.lineno)
/blah/test.py 2
```

# Inspection

Object type
```
>>> type(“Hello”)
```

Best-effort enumeration of attributes and methods
```
>>> dir(“Hello”)
```

Return __dict__ attribute
```
>>> vars(“Hello”)
```

Returns whether object contains attribute
```
>>> has_attr(“Hello”, ‘strip’)
```

# Conversion

```
>>> chr(97)
"a"

>>> ord(“a”)
97

>>> int(“10”)
10

>>> float(14)
14.0

>>> float(“14”)
14.0

>>> bin(10)
"0b1010"

>>> hex(14)
"0xe"

>>> oct(10)
"0o12"
```

# Ternary Operator

```
>>> min = a if a < b else b
```

# Data Type Stuff

Type alias
```
>>> Vector = list[float]
```

```
>>> Vector = list[int]

>>> def add_vector(v: Vector) -> int:
>>>   return( sum(v) )

>>> test_vector = range(0,6)
>>> result = add_vector(test_vector)
>>> print(result)

```
# Function Stuff

Standard
```
>>> def func(x):
```

Default parameter
```
>>> def func(name=”Bob”):
```

Typed parameters
```
>>> def func(name: str):
```

Return type
```
>>> func(name) -> str:
```

Positional vs named parameters
```
>>> def func(a,b):
>>>   pass

>>> func(1,2)         # a=1, b=2
>>> func(b=1, a=2)    # a=2, b=1
```

Returning multiple values
```
>>> def func():
>>>   return 'a','b'

>>> x,y = func()
```

# List Comprehensions

Basic
```
>>> my_string = “Hello”

>>> [ c for c in my_string ]
Hello
```

List
```
>>> my_list = [1,2,3,4,5,6]

>>> [ i for i in my_list ]
[1,2,3,4,5,6]

>>> [ i for i in my_list if (i%2 == 0) ]
[2,4,6]
```

Dictionary
```
>>> my_dict = {'a':1, 'b':2, 'c':3, 'd':4, 'e':5, 'f':6}                    

>>> [ print(f"key:{k} value:{v}") for k,v in my_dict.items() ]
key:a value:1
key:b value:2
key:c value:3
key:d value:4
key:e value:5
key:f value:6
```

Nested loops
```
>>> my_list_1 = [1,2,3,4,5,6]
>>> my_list_2 = [10,20,30]

>>> [ x*y for x in my_list_1 for y in my_list_2 ]
[10, 20, 30, 20, 40, 60, 30, 60, 90]
```

# String Slicing
```
# string[ (inclusive) : (exclusive) ]

>>> my_string = "The rain in Spain falls mainly on the plain"

>>> my_string[0:3]
The

>>> my_string[:8]
The rain

>>> my_string[9:]
in Spain falls mainly on the plain  

>>> my_string[::2] 
Teri nSanflsmil ntepan

>>> my_string[::-1]
nialp eht no ylniam sllaf niapS ni niar ehT 
```

# Iteration functions

enumerate()
```
>>> for i,x in enumerate( ["hello","world",”foo”,”bar”] ):
>>>   print(f"{i}: {x}")

0: hello
1: world
2: foo
3: bar
```

range()
```
>>> list( range(4) )
[ 0,1,2,3,4 ]

>>> list( range(2,5) )
[2,3,4]

>>> list( range(0,10,2) )
[0,2,4,6,8]

>>> list( range(10,0,-2)
[10,8,6,4,2]
```

zip()
```
>>> for item in zip([1,2,3],['a','b','c']): 
>>>   print(item)
(1,’a’)
(2,’b’)
(3,’c’)
```

# String Functions

```
my_string = “The rain in Spain falls mainly on the plain”

>>> len( my_string )
43

>>> my_string.count(‘a’)
5

>>> my_string.find(‘rain’)
4

>>> my_string.find(‘blah)
-1

>>> my_string.find(‘ain’)
5

>>> my_string.find(‘ain’, 6)
14 

>>> my_string.title()
The Rain In Spain Falls Mainly On The Plain

>>> my_string.casefold()
the rain in spain falls mainly on the plain

>>> my_string.lower()
the rain in spain falls mainly on the plain

>>> my_string.upper()
THE RAIN IN SPAIN FALLS MAINLY ON THE PLAIN

>>> my_string.swapcase()
tHE RAIN IN sPAIN FALLS MAINLY ON THE PLAIN

>>> my_string.replace(‘ain’,’AIN’)
The rAIN in SpAIN falls mAINly on the plAIN

>>> my_string.replace(‘ain’,’AIN’,2)
The rAIN in SpAIN falls mAINly on the plain

>>> "|".join(my_string)    # T|h|e| |r|a|i|n| |i|n| |S|p|a|i|n| |f|a|l|l|s| |m|a|i|n|l|y| |o|n| |t|h|e| |p|l|a|i|n

>>> my_string.split()
['The', 'rain', 'in', 'Spain', 'falls', 'mainly', 'on', 'the', 'plain']

>>> my_string.split(“i”)
['The ra', 'n ', 'n Spa', 'n falls ma', 'nly on the pla', 'n']

>>> my_string.split("ain")
['The r', ' in Sp', ' falls m', 'ly on the pl', '']
```

# Lambda Functions

```
>>> func = lambda a,b: a+b
>>> func(1,2)
3

>>> (lambda a,b: a+b)(3,5)
8
```

# map() / filter() / reduce

### map(): Apply function to all items in an iterable
```
>>> my_list = [1,2,3,4,5]

>>> def square(n):
>>>   return n**2

>>> squared_list = list( map(square,my_list) )
[1,4,9,16,25] 

# Using a lambda function
>>> squared_list = list(
>>>   map(
>>> 	lambda n: n**2,
>>> 	my_list
>>>   )
>>> )
[1,4,9,16,25]
```

### filter(): Remove all items not passing a test in an itterable
```
>>> my_list = [1,2,3,4,5]

>>> def even(n):
>>>   return n%2 == 0

>>> evens_list = list( filter(even,my_list) )
[2,4]

# Done with a dict
>>> people = [
>>>   {'Name': "John", 'Age': 15},
>>>   {'Name': "Jane", 'Age': 8},
>>>   {'Name': "Bob", 'Age': 47},
>>>   {'Name': "Alice", 'Age': 29},
>>>   {'Name': "Sam", 'Age': 73}
>>> ]

>>> def adult(person):
>>>   return person['Age'] >= 18

>>> adults = list( filter(adult,people) )
[{'Name': 'Bob', 'Age': 47}, {'Name': 'Alice', 'Age': 29}, {'Name': 'Sam', 'Age': 73}]
```

### reduce(): Apply a reduction to all elements of an iterable
```
>>> from functools import reduce
>>> my_list = [1,2,3,4,5]

>>> def add(a,b):
>>>   return a+b

>>> added_list = reduce(add,my_list)
15
```

# Patterns / Regex

Basic (sub)string matching
```
>>> my_string = "The rain in Spain falls mainly on the plain"
>>> if “rain” in my_string:
>>>   do_something()
```

Find first match using match()
```
>>> from re import match
>>> my_string = "The rain in Spain falls mainly on the plain"

# Must take into account all chars from beginning (“.*”)
>>> matches = match(".*(rain) in (Spain)", my_string)

>>> print( matches.groups() )
('rain', 'Spain')
```

Find first match using search()
```
>>> from re import search
>>> my_string = "The rain in Spain falls mainly on the plain"  

# No need for the “.*”
>>> matches = search("(ain)", my_string)

>>> print( matches.groups() )
('ain',)
```

Find all matches
```
>>> from re import findall
>>> my_string = "The rain in Spain falls mainly on the plain"

>>> matches = findall("([^\W]+ain)", my_string)
>>> print(matches)
['rain', 'Spain', 'main', 'plain']
```

Match across multiple lines
```
>>> findall(“blah”, my_string, re.MULTILINE)
```

# I/O
Read file line-by-line
```
with open("test_input.txt","r") as infile:
  lines = infile.readlines()
  for line in lines:
    print(line, end="")
```

Write to a file
```
with open("test_output.txt","w") as outfile:
  outfile.write("Hello, world!")
```

Write to STDERR
```
import sys
print("Error!", file=sys.stderr)
```

Prompt/capture user input
```
s = input("-> ")
print(s)
```

# Object-Oriented Stuff

Parent class
```
>>> class Person:

>>>   def __init__(self,name,age):
>>>     self.name = name
>>>     self.age = age

>>>   def __del__(self):
>>>     del self.name
>>>     del self.age        

>>>   def __str__(self):
>>>     return f"Name: {self.name} Age:{self.age}"

>>>   @classmethod  # For creating factory methods
>>>   def default_person(cls):
>>>     return cls("Jane", 32)

>>>   @staticmethod
>>>   def static_method():
>>>     print("Notice the missing 'self'?")

>>>   def stub(self):
>>>     pass

>>> p = Person("John",36)
>>> print(p)                           # Call __str__ magic method
Name: John Age:36

>>> p.age = 45
>>> print(p)
Name: John Age:45

>>> p = Person.default_person()        # Invoke class method
>>> print(p)
Name: Jane Age:32

>>> p.static_method()              	   # Invoke static method
Notice the missing 'self'?

>>> del p                              # Call the destructor
```

Child class
```
>>> class CountryPerson(Person):

>>>   def __init__(self,name,age,country):
>>>     super().__init__(name,age)
>>>     self.country = country

>>>   def __str__(self):
>>>     return f"Name: {self.name} Age:{self.age} Country:{self.country}"

>>> c = CountryPerson("Bob",53,"US")
>>> print(c)
Name: Bob Age:53 Country:US

>>> c.static_method()
Notice the missing 'self'?
```