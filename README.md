# Coding_Notes
Useful coding notes that I come across

### Formatting

#### PEP8 Git Diff

```
git diff [branch_1] [branch_2] | pep8 --diff
```

#### SQL Formatter

https://github.com/darold/pgFormatter
http://people.planetpostgresql.org/dfetter/index.php?/archives/78-Formatting!.html
### Debugging

#### Stack Trace
```python
import pdb; pdb.set_trace(); 
```
#### Stack Trace on error

```python
import pdb, traceback, sys

def bombs():
    a = []
    print a[0]

if __name__ == '__main__':
    try:
        bombs()
    except:
        type, value, tb = sys.exc_info()
        traceback.print_exc()
        pdb.post_mortem(tb)
```

#### List functions
Single line list of keys from dictionary
```python
[key for key, value in dictionary.iteritems()]
```
#### List all functions in a class
```python
import inspect
inspect.getmembers([class], predicate=inspect.ismethod)
```

#### Command Line Searching with git grep

git grep [options] [-e] <pattern> [<rev>...] [[--] <path>...]

<!---
run as root -s
exit root run 'exit'
import timeit #time functions
http://beyondgrep.com/ for grep text search tool
-->

https://pypi.python.org/pypi/pep8radius
#### Vim notes

on Mac

copy selected part: visually select text(type v or V in normal mode) and type ```:w !pbcopy```

copy the whole file ```:%w !pbcopy```

past from the clipboard ```:r !pbpaste```



##### Python template

https://wiki.python.org/moin/Vim

```python
#!/usr/bin/env python

"""
Python source code - replace this with a description of the code and write the code below this text.
"""

# vim: tabstop=8 expandtab shiftwidth=4 softtabstop=4
```
