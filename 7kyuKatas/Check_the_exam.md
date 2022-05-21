## Check the exam
---

The first input array is the key to the correct answers to an exam, like ["a", "a", "b", "d"]. The second one contains a student's submitted answers.

The two arrays are not empty and are the same length. Return the score for this array of answers, giving +4 for each correct answer, -1 for each incorrect answer, and +0 for each blank answer, represented as an empty string (in C the space character is used).

If the score < 0, return 0.

For example:

```
checkExam(["a", "a", "b", "b"], ["a", "c", "b", "d"]) → 6
checkExam(["a", "a", "c", "b"], ["a", "a", "b",  ""]) → 7
checkExam(["a", "a", "b", "c"], ["a", "a", "b", "c"]) → 16
checkExam(["b", "c", "b", "a"], ["",  "a", "a", "c"]) → 0
```
---

### Given Code


```python
def check_exam(arr1,arr2):
    # your code here
```

---

### Solution

```python
def check_exam(arr1,arr2):
    count = 0
    for x in range (len(arr1)):
        if(arr1[x] == arr2[x]):
            count += 4
        elif(arr2[x] != "" ):
            count -= 1
    if(count < 0):
        count = 0
    return count
```


---


[See on CodeWars.com](https://www.codewars.com/kata/5a3dd29055519e23ec000074)
