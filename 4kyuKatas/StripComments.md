## Strip Comments
---
Complete the solution so that it strips all text that follows any of a set of comment markers passed in. Any whitespace at the end of the line should also be stripped out.

Example:

Given an input string of:

```
apples, pears # and bananas
grapes
bananas !apples

```

The output expected would be:

```
apples, pears
grapes
bananas

```

The code would be called like so:

```python
result = solution("apples, pears # and bananas\ngrapes\nbananas !apples", ["#", "!"])
# result should == "apples, pears\ngrapes\nbananas"
```


---
### Given Code

```python
def strip_comments(strng, markers):
    # your code here
```

---

### Solution

```python
def strip_comments(strng, markers):
    s = strng.split('\n'); res = ''

    for i in range(0,len(s)):
        for m in markers:
            if m in s[i]:
                s[i] = s[i].split(m)[0]
        res += s[i].rstrip()
        if i != len(s) -1: res += '\n'
    return res
```

---
[See on CodeWars.com](https://www.codewars.com/kata/51c8e37cee245da6b40000bd)