## Moving Zeros To The End

Write an algorithm that takes an array and moves all of the zeros to the end, preserving the order of the other elements.

```python
move_zeros([1, 0, 1, 2, 0, 1, 3]) # returns [1, 1, 2, 1, 3, 0, 0]

```

* * * * *

ARRAYS

SORTING

ALGORITHMS

-----

### Given Code


```python
def move_zeros(lst):
    return lst
```

---

### Solution

```python
def move_zeros(lst):
    return [i for i in lst if i != 0] + [0] * lst.count(0)
```

---


[See on CodeWars.com](https://www.codewars.com/kata/52597aa56021e91c93000cb0)