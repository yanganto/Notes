Indentation
---
```
if foo:
    if bar:
        x=42
else:
  print foo
```
[0]  
[0 ,4]  
[0 ,4, 8]  
[0]  
[0, 2]  
[0]

Default argument
---
the default value only assign when the function __on create__


Closure function
---
```
def outer():
  x = 10
  def m(number):
    print(number)
  x = 100
  m(x)
```
> 100  

```
def outer():
  x = 10
  def m(number=x):
    print(number)
  x = 100
  m(x)
```
> 10  
__TK__ will need this skill, but use class with `__call__` is a better implement, or __functool.partial__

```
v = 10
def c()
  v = v + 10

c()
```
> Error  v already init as local
```
v = 10
def c()
  global v
  v = v + 10
c()
```

The `__del__` of python
---
```
class F(object):
  def __del__:
    # use B
class B
  def __del__:
    # use F
```

- del -> reference count - 1
- reference count = 0 => exec gc

Circular reference
---
- both with `__del__` function will problem
- use weak reference, gc will ignore the reference
- user abc

User virtualenv
--
requirement.txt write manually to avoid problem

flakr8
a modular source code checker w/ Git hook and Mercurial check
