Here is your chance to write instructions for a text-to-speech system. Let's focus on reading phone numbers aloud. <br>
The input phone number will consist solely of digits. Print the name of each digit on a new line for the system to read them one by one.

#### Sample input
4901825
#### Sample ouput
four <br>
nine <br>
zero <br>
one <br>
eight <br>
two <br>
five <br>

# Solution
```python
digits = ["zero", "one", "two", "three", "four", "five", "six", "seven", "eight", "nine"]
number = input()
for n in number:
    print(digits[int(n)])
```
