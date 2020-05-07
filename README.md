# Python-JetBrains-Academy

This is a cheatsheet of what I've learned so far about python (3.x) on [JetBrains Academy](https://hyperskill.org/)<br>

# What is PEP?
<b>PEP</b> stands for <b>Python Enhancement Proposal</b>. There are different types of PEP and the most useful one for beginners is the informational PEP. PEPs of this kind typically describe commonly accepted guidelines or conventions about the language, so they can be very helpful. Besides PEP 8, which is an official style guide, another great PEP to look at is the [Zen of Python](https://www.python.org/dev/peps/pep-0020/).<br>
Let me show you some of the basic rules of PEP. <br>
* <b>Do not use more than 79 characters in a line of code</b>. Shorter lines look better in code editors
* <b>Avoid extra spaces within parantheses</b>
```python
# Good
print('Hello!')

# Bad
print( 'Hello!' )
```
* <b>Avoid an extra space before an open parenthesis</b>
```python
# Good
print('some text')

# Bad
print ('some text')
```
* <b>You can use either single or double quotes to define strings</b>. Please, choose one that you like the most and consistently use it in your code. The only recommendation in PEP 8 is that if a string contains single or double quotes, you should use the other one to avoid backslashes
```python
# Good
print("It's a good string!")

# Bad and harder to read
print('It\'s a bad string!')
```
