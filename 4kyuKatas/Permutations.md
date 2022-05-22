## Permutations
---

In this kata you have to create all permutations of a non empty input string and remove duplicates, if present. This means, you have to shuffle all letters from the input in all possible orders.

Examples:

```
* With input 'a'
* Your function should return: ['a']
* With input 'ab'
* Your function should return ['ab', 'ba']
* With input 'aabb'
* Your function should return ['aabb', 'abab', 'abba', 'baab', 'baba', 'bbaa']

```

The order of the permutations doesn't matter.

---
### Given Code

```python
def permutations(string):
    # your code here
```

---

### Solution

```python
def permutations(string):
    res = set([string])
    
    if len(string) == 2:
        res.add(string[1] + string[0])
    elif len(string) > 2:
        for i, c in enumerate(string):
            for s in permutations(string[:i] + string[i + 1:]):
                res.add(c + s)

    return list(res)
```

---
[See on CodeWars.com](https://www.codewars.com/kata/5254ca2719453dcc0b00027d)