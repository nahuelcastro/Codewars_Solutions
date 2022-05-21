## Polish alphabet
---
There are 32 letters in the Polish alphabet: 9 vowels and 23 consonants.

Your task is to change the letters with diacritics:

```
ą -> a,
ć -> c,
ę -> e,
ł -> l,
ń -> n,
ó -> o,
ś -> s,
ź -> z,
ż -> z

```

and print out the string without the use of the Polish letters.

For example:

```
"Jędrzej Błądziński"  -->  "Jedrzej Bladzinski"
```
---
### Given Code

```python
def correct_polish_letters(st): 
    # your code here
```

---

### Solution

```python
def correct_polish_letters(st): 
    res = ""
    dict= {'ą':'a' ,'ć' : 'c','ę' : 'e','ł' : 'l','ń' : 'n','ó' : 'o','ś': 's','ź' : 'z','ż' : 'z'}
    for x in range(len(st)):
        sim = st[x]
        if (sim in dict):
            sim = dict[sim]
        res += sim
    return res
```

---
[See on CodeWars.com](https://www.codewars.com/kata/57ab2d6072292dbf7c000039)