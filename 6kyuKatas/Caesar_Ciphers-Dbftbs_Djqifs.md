## Caesar_Ciphers-Dbftbs_Djqifs
---
Caesar Ciphers are one of the most basic forms of encryption. It consists of a message and a key, and it shifts the letters of the message for the value of the key.

Read more about it here: <https://en.wikipedia.org/wiki/Caesar_cipher>

Your task
---------

Your task is to create a function encryptor that takes 2 arguments - key and message - and returns the encrypted message.

Make sure to only shift letters, and be sure to keep the cases of the letters the same. All punctuation, numbers, spaces, and so on should remain the same.

Also be aware of keys greater than 26 and less than -26. There's only 26 letters in the alphabet!

Examples
--------

A message `'Caesar Cipher'` and a key of `1` returns `'Dbftbs Djqifs'`.

A message `'Caesar Cipher'` and a key of `-1` returns `'Bzdrzq Bhogdq'`.

---

### Given Code


```python
def encryptor(key, message):
    # your code here
```

---

### Solution

```python
def is_letter(char):
    return ord(char) >= 65 and ord(char) <= 122

def encryptor(key, message):    
    if key > 26:
        key = key % 26
    elif key < -26:
        key = ((key * -1) % 26) * -1
        
    base = 65
    res = ''
    for i in range (0, len(message)):
        old_letter = message[i]
        new_letter = message[i]
        
        if is_letter(message[i]):
            is_lower = old_letter == old_letter.lower()
            old_letter = old_letter.upper()
            
            new_letter = chr( ((ord(old_letter) - base) + key) %26 + base )
            if is_lower:
                new_letter = new_letter.lower()
        res += new_letter
    return res
```


---


[See on CodeWars.com](https://www.codewars.com/kata/546937989c0b6ab3c5000183)