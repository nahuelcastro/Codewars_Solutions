## Return the first M multiples of N
---
Implement a function, multiples(m, n), which returns an array of the first m multiples of the real number n. Assume that m is a positive integer.

Ex.

multiples(3, 5.0)
should return

[5.0, 10.0, 15.0]

---

### Given Code


```python
def multiples(m, n):
    # your code here
```

---

### Solution

```python
def multiples(m, n):
    arr = []
    for x in range (1,m+1):
        arr.append(x*n)
    return arr
```


---


[See on CodeWars.com](https://www.codewars.com/kata/593c9175933500f33400003e)