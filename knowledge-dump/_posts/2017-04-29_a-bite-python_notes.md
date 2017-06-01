# A bite of Python [notes]

## Function

### Parameter vs Arguments

parameter: 形参
argument： 实参

#### keyword arguments

```python
def func(a, b=5, c=10):
    print('a is', a, 'and b is', b, 'and c is', c)

func(3, 7)
func(25, c=24)
func(c=50, a=100)

func(c=50, 100) # SyntaxError: non-keyword arg after keyword arg
```

---

## Module

### A module's \_\_name\_\_

Every Python module has its \_\_name\_\_ defined. If this is '\_\_main\_\_', that implies that the module is being run standalone by the user and we can take appropriate actions.

```python
if __name__ == '__main__':
    print('This program is being run by itself')
else:
    print('I am being imported from another module')
```

## list/set/dict comprehensions

```python
[truncate(x) for x in items if len(x) > 30]
```

## with statement

The with statement subtly handles file closing and lock releasing even in the case of exceptions being raised.

```python
with open("somefile.txt", "w") as somefile:
	somefile.write("sometext")
return
```

## Decorator

A decorator is any callable Python object that is used to modify a function, method or class definition. A decorator is passed the original object being defined and returns a modified object, which is then bound to the name in the definition.

the decorator syntax is **pure syntactic sugar**, using @ as the keyword:

```python
@viking_chorus
def menu_item():
    print("spam")
```

is equivalent to

```python
def menu_item():
    print("spam")
menu_item = viking_chorus(menu_item)
```

## is vs ==

* **is** checks that 2 arguments refer to the same object
* **==** checks that 2 arguments have the same value.

> A good example is: 1==True returns True, but 1 is True returns False

### Use is when comparing to None

The None value is a singleton but when you're checking for None, you rarely want to actually call __eq__ on the LHS argument. So:

```python
# bad
if item == None:
    continue

# good
if item is None:
   continue

```

Not only **is** the good form faster, it's also more correct. It's no more concise to use ==

---

[elements-of-python-style](https://github.com/amontalenti/elements-of-python-style/blob/master/README.md)