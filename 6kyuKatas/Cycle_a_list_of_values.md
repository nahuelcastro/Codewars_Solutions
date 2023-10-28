## Cycle a list of values
---
Prologue
--------

You're part of a team porting MS Paint into the browser and currently working on a new UI component that allows user to control the canvas zoom level.

According to the wireframes delivered to you in PowerPoint format the user should be able to *cycle* through specified zoom levels by clicking a button in the UI repeatedly. The reverse direction should work with shift key held.

A new function is needed to support this behavior, so you alt-tab to Visual Studio and get to work.

* * * * *

Instructions
------------

Implement a function which when given the arguments

1.  Direction to which to cycle the current value
2.  List of values
3.  Current value

returns the value next to current value in the specified direction.

The function should pick the next value from the other side of the list in case there are no values in the given direction.

Examples
--------

```
# Given the direction 1, returns the value next to 1 on the right
cycle(1, [1,2,3], 1)   # => 2

# Given the direction -1 and value 1, wraps around list returning the last element
cycle(-1, [1,2,3], 1)  # => 3

# 0 does not exist in the list, returns null
cycle(1, [1,2,3], 0)   # => null

# Corner case: multiple instances of given value, picks next relative to first occurrence
cycle(1, [1,2,2,3], 2) # => 2

```

---

### Given Code


```python
# d = direction, v = values array, c = number to search 
# return None in case of value not found
def cycle(d, v, c):
    pass
```

---

### Solution

```python
# d = direction, v = values array, c = number to search 
# return None in case of value not found
def cycle(d, v, c):
    
    if not c in v:
        return None
    
    i_first_ocurrence = None
    for i in range(len(v)):
        if v[i] == c:
            i_first_ocurrence = i
            break

    i_ret = i_first_ocurrence + d
    
    return v[(i_first_ocurrence + d) % len(v)]
    
```


---


[See on CodeWars.com](https://www.codewars.com/kata/5456812629ccbf311b000078)