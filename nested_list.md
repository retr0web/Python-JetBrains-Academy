Create a list of words from the text below that are shorter than or equal to the input value. Print the new list.
#### Sample input:
1
#### Sample output:
['a', 'a']
# Solution
```python
text = [["Glitch", "is", "a", "minor", "problem", "that", "causes", "a", "temporary", "setback"],
        ["Ephemeral", "lasts", "one", "day", "only"],
        ["Accolade", "is", "an", "expression", "of", "praise"]]
        
counter = int(input())
words = []
for x in text:
    for word in x:
        if len(word) <= counter:
            words.append(word)
print(words)
```
