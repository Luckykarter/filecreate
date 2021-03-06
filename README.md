# FileCreate
[![PyPI](https://img.shields.io/pypi/v/FileCreate)](https://pypi.org/project/filecreate/)

Provides functionality for creating a new empty file with unique name.

The file_mask parameter may contain a sequence of hash marks '#' which will be substituted by a unique sequence number 
starting from 001. 

## Install:

```bash  
$ pip install filecreate
```  

## Usage Samples:

```Python
from filecreate import FileCreate

# Create file using mask
# by default parameter leading_zeros=True and all hash signs are replaced with numbers
with FileCreate('test####.txt') as file:    # if test0001.txt does not exist - creates it
    file.writelines()                       # working with file descriptor as usual

with FileCreate('test####.txt', leading_zeros=False):   # will create file test1.txt
    file.writelines()                       

# if file cannot be created (maximum sequence reached) - FileExistsError exception is raised

# Get available file name without creating an actual file
filename = FileCreate.get_filename('Folder', 'test###.txt')

```

