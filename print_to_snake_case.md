Since we are learning Python, sometimes it might be useful to convert texts from lowerCamelCase to snake_case.<br>
The main trick is to find the correct place where to insert an underscore.<br>
Let's make a rule that it's right before a capital letter of the next word.
#### Sample input
parselTongue
#### Sample output
parsel_tongue
# Solution
```python
word = input()
translated = ''
for w in word:
    if w.islower():
        translated += w
    elif w.isupper():
        translated += "_" + w.lower()
print(translated)
```
