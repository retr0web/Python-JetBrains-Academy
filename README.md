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

# Variable

#### <b>Defining a variable and assigning values</b>
```python
day_of_week = "Monday"

print(day_of_week)  # Monday

print(type(day_of_week))  # <class 'str'>
```
Python allows you to assign values of different types to the same variable. Let's assign the string value to a variable and then assign it an int value.
```pyhton
month = "December"
print(type(month))  # <class 'str'>

month = 12
print(type(month))  # <class 'int'>
```
This works because Python is a language with dynamic typing.

#### <b>Naming rules</b>
Each variable has a specific name that distinguishes it from other variables. There are some rules for naming variables that you should follow:
* names are case-sensitive (<b>month</b> is not the same as <b>Month</b>);
* a name begins with a letter or an underscore, followed by letters, digits, and underscores (e.g. <b>user_name</b>, ,b>score1</b>, <b>_count</b>);
* name cannot start with a digit (e.g. <b>2q</b> is not a valid name);
* a name must not be a <b>keyword</b>.<br>
<strong>Do not break these rules; otherwise, your program will not work.</strong>

# Taking input

#### <b>Reading input from user</b>
```python
user_name = input()
print('Hello, ' + user_name)
```
In the first line, the program will wait for the user to enter something and the fact that, since we assign the input to the variable, we will be able to perform some actions with it later. In the second line, the program appends the entered name to the end of 'Hello, ' string and prints the whole phrase as a result.

#### <b>Clear messages</b>
It is highly recommended to state clearly what type of input we expect from our user. To do so, the input() function may take an optional argument, that is a message:
```python
user_name = input('Please, enter your name: ')
print('Hello, ' + user_name)
```
The program starts, the user sees the message, enters their name and gets the result as follows:
```
Please, enter your name: Sauron
Hello, Sauron
```
#### <b>Important details</b>
Let's dig into some details. First of all, how long can the user's input be? The second question is: how does the program understand that the person entered everything they wanted?<br>

Here's a thing about the input() function: as soon as the program has started executing this function, it stops and waits for the user to enter some value and press Enter. That also means that if there's no input from the user, the program will not execute any further.<br>

What else should you remember? Well, this: any value you enter, the function sees as a string. It doesn't matter if you enter digits or letters, the input will be converted to a string.<br>
If you want a number to be a number, you should write it explicitly:
```python
print("What's your favorite number?")
value = int(input())  # now value keeps an integer number
```
However, be careful: in these circumstances, if a user enters a non-integer value, an Error will appear.<br>

To read several inputs, you should call the function more than once:
```python
day = int(input())  # 4
month = input()     # October
```
