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

# Situational Awareness

Module name.  (The name of the file by default)
```
if  __name__ == “__main__”:      
  do_something()
```

File name
```
print( __file__ )

>>> c:\python37\lib\io.py
```

Current file name and line number
```
from inspect import currentframe, getframeinfo
frameinfo = getframeinfo(currentframe())
print(frameinfo.filename, frameinfo.lineno)

>>> /blah/test.py 2
```

