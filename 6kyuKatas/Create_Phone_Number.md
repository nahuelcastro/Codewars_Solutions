## Create Phone Number
---
Write a function that accepts an array of 10 integers (between 0 and 9), that returns a string of those numbers in the form of a phone number.

### Example

```
create_phone_number([1, 2, 3, 4, 5, 6, 7, 8, 9, 0]) # => returns "(123) 456-7890"

```

The returned format must be correct in order to complete this challenge.\
Don't forget the space after the closing parentheses!

---

### Given Code


```python
def create_phone_number(n):
    # your code here
```

---

### Solution

```python
def create_phone_number(n):
    res = ""
    for i in range(0,len(n)):
        write = True
        if (i == 0):
            res += '('
        elif (i == 3):
            res += ')'
            res += ' '
        elif (i == 6):
            res += '-'
        res += str(n[i])
    return res
```


---


[See on CodeWars.com](https://www.codewars.com/kata/525f50e3b73515a6db000b83)