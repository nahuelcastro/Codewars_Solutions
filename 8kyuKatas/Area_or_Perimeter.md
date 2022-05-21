## Area or Perimeter
---

You are given the `length` and `width` of a 4-sided polygon. The polygon can either be a rectangle or a square.\
If it is a square, return its area. If it is a rectangle, return its perimeter.

```
area_or_perimeter(6, 10) --> 32
area_or_perimeter(3, 3) --> 9

```

Note: for the purposes of this kata you will assume that it is a square if its `length` and `width` are equal, otherwise it is a rectangle.


---
### Given Code

```python
def area_or_perimeter(l , w):
    # your code here
```

---

### Solution

```python
def area_or_perimeter(l , w):
    return l*w if l==w else l+l+w+w
```

---
[See on CodeWars.com](https://www.codewars.com/kata/5ab6538b379d20ad880000ab)