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

# Comments
Python comments start with a <b>hash #</b>. Everything after the hash mark and up to the end of the line is regarded as a comment and <b>will be ignored when running the code</b>.
```python
print("This will run.")  # This won't run
```
In the example above, you can see what PEP 8 calls an inline comment because it's written on the same line as the code.<br>

A comment can also refer to the block of code that follows it:
```python
# Outputs three numbers
print("1")
print("2")
print("3")
```
#### Formating comments
Although it is pretty easy to write a comment, let's discuss how to do this in accordance with best practices.<br>

To begin with, <b>after a hash mark there should be one space and, in inline comments, there should be at least two spaces between the end of the code and the hash mark</b>.
```python
print("Learning Python is fun!")  # This is a proper comment formatting
print("PEP-8 is important!")#This is a very bad example
```
<b>Indent your comment to the same level as the statement it explains</b>.
```python
# Good

# this comment is at the wrong place
print("This is a statement to print.")

# Bad

   # this comment is at the wrong place
print("This is a statement to print.")
```
<b>It's better to split a long comment into several lines</b>: you can do it by adding a hash mark at the beginning of each new line:
```python
# Imagine that this is an example of a really long comment
# that we need to spread over three lines, so we continue
# to write it even here.
print("The long comment above explains this line of code.")
```
<b>Comments that span multiple lines are called multi-line or block comments</b>. In Python, there is no special way to indicate them.

Also, You may come across multi-line comments enclosed in triple quotes <b>"""..."""</b>, still, we recommend that you use several hash marks for this purpose. Thus, your code will comply with the official style guide. Triple quotes are reserved for documentation strings, or docstrings for short. They are also informative, but their use is limited to functions, methods and several other cases.

# Basic data types
Every data object (a variable or a constant) has a type that describes how to keep it in memory, which operation can be applied to this object and how to compute them.
#### <b>Strings</b>
Whenever you want to work with some kind of textual information in your program, you'll have to work with strings. The string type is called str. Strings are extremely common and useful in Python. String literals may be delimited using either single or double quotes.
```python
print("")                    # empty string
print('a')                   # single character
print("string")              # one word
print('1234')                # a sequence of digits
print("Hello, world!")       # a sentence
print('Bonjour, le monde!')  # a sentence
```
#### Numerical types
Numbers are the most important thing for any programmer. There is hardly any serious program you can write without using numbers, so let's discuss some basic numerical types:
* <b>int</b> (signed integers). Called integers or ints, they are whole numbers (positive, negative, or zero), having no decimal point
* <b>float</b> (floating-point numbers). Called floats, they represent real numbers and have a decimal point
```python
print(11)    # prints 11
print(11.0)  # prints 11.0
```
#### Printing types
We also have a way to clearly demonstrate types of different objects using the <b>type()</b> function which is a part of Python.
```python
print(type('hello'))  # <class 'str'>
print(type("world"))  # <class 'str'>
 
print(type(100))      # <class 'int'>
print(type(-50))      # <class 'int'>
 
print(type(3.14))     # <class 'float'>
print(type(-0.5))     # <class 'float'>
```
As you can see from the examples above, the <b>type()</b> function indicates the data type of a passed value after the word class.
