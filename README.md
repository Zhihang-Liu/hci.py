# hci.py

The Higher container interface for Python

## example

### iter module

```py
Iter(range(1, 5))
    .fold(0, lambda x, y: x+y)
# Out: 10

Iter(range(1, 10))
    .map(lambda x:x+1)
    .map(lambda x:x*2)
    .reduce(lambda x,y:x+y)
# Out: 108

Iter(range(1, 4))
    .for_each(print)
'''
1
2
3
'''
```

### func module

```py
def f2i(v: float) -> int:
    return int(v)

def i2s(v: int) -> str:
    return str(v)

# Three statement is equivalence
r: str = Func(f2i) | i2s < 1.1
r: str = Func(f2i) >> i2s < 1.1
r: str = i2s << Func(f2i) < 1.1
# Func(f2i) : Func[float, int]
# Func(f2i) >> i2s : Func[float, str]
# i2s << Func(f2i) : Func[float, str]
```
