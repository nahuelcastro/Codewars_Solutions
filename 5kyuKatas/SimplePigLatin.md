## Simple Pig Latin

Move the first letter of each word to the end of it, then add "ay" to the end of the word. Leave punctuation marks untouched.

Examples
--------

```python
pig_it('Pig latin is cool') # igPay atinlay siay oolcay
pig_it('Hello world !')     # elloHay orldway !

```

* * * * *

REGULAR EXPRESSIONS

ALGORITHMS

-----

### Given Code


```python
def pig_it(text):
    pass
```

---

### Solution

```python
def pig_it(text):
    retList = []
    for w in text.split(' '):
        if w.isalpha():
            retList.append(w[1::] + w[0] + 'ay')
        else:
            retList.append(w)
    return ' '.join(retList)
```


---


[See on CodeWars.com](https://www.codewars.com/kata/520b9d2ad5c005041100000f)