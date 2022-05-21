## Array plus array
---
I'm new to coding and now I want to get the sum of two arrays...actually the sum of all their elements. I'll appreciate for your help.

P.S. Each array includes only integer numbers. Output is a number too.

---
### Given Code

```python
def array_plus_array(arr1,arr2):
    # your code here
```

---

### Solution

```python
def array_plus_array(arr1,arr2):
    count = 0
    for x in range(len(arr1)):
        count += arr1[x]    
    for x in range(len(arr2)):
        count += arr2[x]    
    return count
```

---
[See on CodeWars.com](https://www.codewars.com/kata/5a2be17aee1aaefe2a000151)