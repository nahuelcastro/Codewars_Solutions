## Abbreviate a Two Word Name
---
Write a function to convert a name into initials. This kata strictly takes two words with one space in between them.

The output should be two capital letters with a dot separating them.

It should look like this:

`Sam Harris` => `S.H`

`patrick feeney` => `P.F`

---
### Given Code

```python
def abbrevName(name):
    # your code here
```

---

### Solution

```python
def abbrevName(name):
    first, last = name.upper().split(' ')
    return first[0] + '.' + last[0]
```

---
[See on CodeWars.com](https://www.codewars.com/kata/57eadb7ecd143f4c9c0000a3)