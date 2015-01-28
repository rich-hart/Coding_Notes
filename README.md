# Coding_Notes
Useful coding notes that I come across

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
