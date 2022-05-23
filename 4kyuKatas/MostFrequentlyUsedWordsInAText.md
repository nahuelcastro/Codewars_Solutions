## Most frequently used words in a text
---
Write a function that, given a string of text (possibly with punctuation and line-breaks), returns an array of the top-3 most occurring words, in descending order of the number of occurrences.

Assumptions:
------------

-   A word is a string of letters (A to Z) optionally containing one or more apostrophes (`'`) in ASCII.
-   Apostrophes can appear at the start, middle or end of a word (`'abc`, `abc'`, `'abc'`, `ab'c` are all valid)
-   Any other characters (e.g. `#`, `\`, `/` , `.` ...) are not part of a word and should be treated as whitespace.
-   Matches should be case-insensitive, and the words in the result should be lowercased.
-   Ties may be broken arbitrarily.
-   If a text contains fewer than three unique words, then either the top-2 or top-1 words should be returned, or an empty array if a text contains no words.

Examples:
---------

```
top_3_words("In a village of La Mancha, the name of which I have no desire to call to
mind, there lived not long since one of those gentlemen that keep a lance
in the lance-rack, an old buckler, a lean hack, and a greyhound for
coursing. An olla of rather more beef than mutton, a salad on most
nights, scraps on Saturdays, lentils on Fridays, and a pigeon or so extra
on Sundays, made away with three-quarters of his income.")
# => ["a", "of", "on"]

top_3_words("e e e e DDD ddd DdD: ddd ddd aa aA Aa, bb cc cC e e e")
# => ["e", "ddd", "aa"]

top_3_words("  //wont won't won't")
# => ["won't", "wont"]

```

Bonus points (not really, but just for fun):
--------------------------------------------

1.  Avoid creating an array whose memory footprint is roughly as big as the input text.
2.  Avoid sorting the entire array of unique words.

---
### Given Code

```python
def top_3_words(text):
    # your code here
```

---

### Solution

```python
def top_3_words(text):
    res = []
    
    # replace all char distinct from letters or ' or and whitespaces to whitespaces
    for c in text:
        if not (c.isalpha() or c == '\'' or c == ' '):
            text = text.replace(c, ' ')
    text = text.lower()
    text = text.split()

    # create a dictionary with the words and their frequency
    d = {}
    for word in text:
        if word.replace('\'', '').isalpha():
            if word in d:
                d[word] += 1
            else:
                d[word] = 1
    
    pair1 = ('',0); pair2 = ('',0); pair3 = ('',0)

    for key, value in d.items():
        if value > pair1[1]:
            pair3 = pair2
            pair2 = pair1
            pair1 = (key, value)
        elif value > pair2[1]:
            pair3 = pair2
            pair2 = (key, value)
        elif value > pair3[1]:
            pair3 = (key, value)

    if pair1[1] == 0:
        return []

    res.append(pair1[0].lower())
    if pair2[1] != 0: res.append(pair2[0].lower())
    if pair3[1] != 0: res.append(pair3[0].lower())

    return res
```

---
[See on CodeWars.com](https://www.codewars.com/kata/51e056fe544cf36c410000fb)