---
layout: post
title:  'Python file handing'
date:   2019-08-27 12:49:00 +0100
categories: python
---
Personal cheatsheet on file handling.  


# Reading a file
For illustration, use:
```python
from pathlinb import Path
path = Path("/usr/share/dict/propernames")
```

Print first line of file (by default, file is opened in _read_ mode `r`):   
or using `pathlib`:  
```python
with path.open() as f:
    print(f.readline())
```
The method `readline()` reads one line at a time, including the newline character `\n`.  

Print first 20 _characters_ (counting `\n` at end of lines):  
```python
with path.open() as f:
    print(f.read(20))
```

Print first 4 _lines_:  
```python
with path.open() as f:
    for i in range(4):
        print(f.readline().strip())
```

Print lines 10 through 20:  
```python
with path.open() as f:
    print(''.join(f.readlines()[10:20]))
```

Count number of lines:  
```python
with path.open() as f:
    print(f"There are {len(f.readlines())} lines.")
```


# Write to a file
Use a dummy file (in current working directory):  

```python
filename = Path('bob.txt')
```
Write into file:
```python
with filename.open('w+') as f:
    f.write('one\n')
    f.write('two\n')
    f.write('three')
```
(Note how we need to explicit add `\n` at the end of each line.)
The option `+` creates the file if it does not exist.  

Append to file:  
```python
with filename.open('a+') as f:
    f.write('\nfour\n')
```
