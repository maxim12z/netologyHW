[Задание](https://github.com/netology-code/ibos-homeworks/tree/v2/07_python1)

```python
a = 1
a += 1
print(a)
```

```python
a = str("1")
a = a + "1"
print(a)
```

```python
import sys
import os

m = 0
for elements in os.listdir(sys.argv[1]):
    print(elements)
    m += 1
print(f'Количество объектов в папке {sys.argv[1]} - {m} шт.')
```

```python
import sys
import os

if os.path.isdir(sys.argv[1]):
    print('directory exist')
elif os.path.isfile(sys.argv[1]):
    print('file exist')
else:
    print('object not exist')
```

```python
import sys
import base64

if(len(sys.argv) != 3):
    print('Allow only 2 arguments')
    exit(2)

if(sys.argv[1] != 'crypt' and sys.argv[1] != 'decrypt'):
    print('First argument must be crypt or derypt')
    exit(3)

if sys.argv[1] == 'crypt':
    a = sys.argv[2]
    a = a.encode('ascii')
    a = base64.b64encode(a)
    a = a.decode('ascii')
    print(a)

if sys.argv[1] == 'decrypt':
    a = sys.argv[2]
    a = a.encode('ascii')
    a = base64.b64decode(a)
    a = a.decode('ascii')
    print(a)
```
