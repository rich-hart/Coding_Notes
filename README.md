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
#### Stack Trace Code

You could do this while in pdb to launch a temporary interactive Python session with all the local variables available:
```python
(pdb) !import code; code.interact(local=vars())
Python 2.6.5 (r265:79063, Apr 16 2010, 13:57:41) 
[GCC 4.4.3] on linux2
Type "help", "copyright", "credits" or "license" for more information.
(InteractiveConsole)
>>> 
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

##### Django 

https://realpython.com/blog/python/asynchronous-tasks-with-django-and-celery/

##### Testing
https://hg.python.org/cpython/file/3dc602b1f4a2/Lib/test/test_threading.py

##### Vim
.vimrc
```
":set mouse=a"
"set mouse=nicr" 
"remove .swp files"
set noswapfile 

set ruler

"highlight text"
syntax on


" number tab"
if exists("+showtabline")
     function MyTabLine()
         let s = ''
         let t = tabpagenr()
         let i = 1
         while i <= tabpagenr('$')
             let buflist = tabpagebuflist(i)
             let winnr = tabpagewinnr(i)
             let s .= '%' . i . 'T'
             let s .= (i == t ? '%1*' : '%2*')
             let s .= ' '
             let s .= i . ')'
             let s .= ' %*'
             let s .= (i == t ? '%#TabLineSel#' : '%#TabLine#')
             let file = bufname(buflist[winnr - 1])
             let file = fnamemodify(file, '%@')
             if file == ''
                 let file = '[No Name]'
             endif
             let s .= file
             let i = i + 1
         endwhile
         let s .= '%T%#TabLineFill#%='
         let s .= (tabpagenr('$') > 1 ? '%999XX' : 'X')
         return s
     endfunction
     set stal=2
     set tabline=%!MyTabLine()
endif
```
    
##### Kubernetes
```
kubectl -n kube-system describe secret default
```
