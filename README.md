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

# Integer arithmetic
#### <b>Basic operations</b>
Python supports basic arithmetic operations:

* addition +
* subtraction -
* multiplication *
* division /
* integer division //
* the remainder of a division %
* exponentiation (is a way to raise a number to a power) **
```python
print(10 + 10)   # 20
print(100 - 10)  # 90
print(10 * 10)   # 100
print(77 / 10)   # 7.7
print(77 // 10)  # 7
print(7 % 2)  # 1, because 7 is an odd number
print(8 % 2)  # 0, because 8 is an even number
print(10 ** 2)  # 100
```
#### Operation priority
```python
print(10 / 5 / 2)  # 1.0
print(8 / 2 * 5)   # 20.0
```
The expressions above may seem ambiguous to you, since they have alternative solutions depending on the operation order: either 1.0 or 4.0 in the first example, and either 20.0 or 0.8 in the second one. In such cases, Python follows a left-to-right operation convention from mathematics. It's a good thing to know, so try to keep that in mind, too!
#### Operators and PEP
You must follow the rule of 79 lines, so if you have a lot of operations you have to write your code like this:
```python
income = (gross_wages
          + taxable_interest
          + (dividends - qualified_dividends)
          - ira_deduction
          - student_loan_interest)
```
This is called Knuth's style.

# Booleans

The Boolean type, or simply bool, is a special data type that has only two possible values: <b>True</b> and <b>False</b>. In Python, the names of boolean values start with a capital letter.
<br>
```python
is_open = True
is_closed = False
```
There are three built-in boolean operators in Python: and, or and not. The first two are binary operators which means that they expect two arguments. not is a unary operator, it is always applied to a single operand. First, let's look at these operators applied to the boolean values.
```python
# AND
a = True and True    # True
b = True and False   # False
c = False and False  # False
d = False and True   # False

# OR
a = True or True    # True
b = True or False   # True
c = False or False  # False
d = False or True   # True

# NOT
to_be = True           # to_be is True
not_to_be = not to_be  # not_to_be is False
```
#### Truthy and Falsy values
Though Python has the boolean data type, we often want to use non-boolean values in a logical context. And Python lets you test almost any object for truthfulness. When used with logical operators, values of non-boolean types, such as integers or strings, are called truthy or falsy. It depends on whether they are interpreted as True or False.
<br>
The following values are evaluated to False in Python:
* constants defined to be false: None and False,
* zero of any numeric type: 0, 0.0,
* empty sequences and containers: "", [], {}.
Anything else generally evaluates to True. Here is a couple of examples:
```python
print(0.0 or False)  # False
print(False and "")  # False
```
#### Short-circuit evaluation
The last thing to mention is that logical operators in Python are short-circuited. That's why they are also called lazy. That means that the second operand in such an expression is evaluated only if the first one is not sufficient to evaluate the whole expression.
* x and y returns x if x is falsy; otherwise, it evaluates and returns y.
* x or y returns x if x is truthy; otherwise, it evaluates and returns y.
```python
# division is never evaluated, because the first argument is True
lazy_or = True or (1 / 0)  # True
 
# division is never evaluated, because the first argument is False
lazy_and = False and (1 / 0)  # False
```
# Comparisons
#### Comparison operators
* <b><</b> strictly less than
* <b><=</b> less than or equal
* <b>></b> strictly greater than
* <b>>=</b> greater than or equal
* <b>==</b> equal
* <b>!=</b> not equal
* <b>is</b> object identity
* <b>is not</b> negated object identity
* <b>in</b> membership
* <b>not in</b> negated membership

#### Comparison chaining
Since comparison operations return boolean values, you can join them using logical operators.
```python
x = -5
y = 10
z = 12
 
result = x < y and y <= z  # True
```
In Python, there is a fancier way to write complex comparisons. It is called chaining. For example, x < y <= z is almost equivalent to the expression you saw in the last example. The difference is that y evaluated only once. 
```pyhton
result = 10 < (100 * 100) <= 10000  # True, the multiplication is evaluated once
```
# If statement
```python
biscuits = 17
if biscuits >= 5:
    print("It's time for tea!")
```
#### Nested if statements
```python
rainbow = "red, orange, yellow, green, blue, indigo, violet"
warm_colors = "red, yellow, orange"
my_color = "orange"
 
if my_color in rainbow:
    print("Wow, your color is in the rainbow!")
    if my_color in warm_colors:
        print("Oh, by the way, it's a warm color.")
```
# While loop
```python
number = 0
while number < 5:
    print(number)
    number += 1
print('Now, number is greater than or equal to 5')
```
If you delete the part of the conditional code where you increase the value of a counter, you will bump into the infinite loop. What does it mean? Since you don’t increase your variable, a condition never becomes false and can work forever. Usually, it is a logical fallacy, and you'll have to stop the loop using special statements or finishing the loop manually.
# Built-in functions
```python
number = "111"
 
# finding the length of an object
print(len(number))  # 3
 
# converting types
integer = int(number)
float_number = float(number)
print(str(float_number))  # "111.0"
 
# adding and rounding numbers
my_sum = sum((integer, float_number))
print(my_sum)  # 222.0
print(round(my_sum))  # 222
 
# finding the minimum and the maximum
print(min(integer, float_number))  # 111
print(type(max(integer, float_number, my_sum)))  # <class 'float'>
```
# Functions
```python
def function_name(parameter1, parameter2, ...):
    # function's body
    ...
    return "return value"
```
You can also declare a sort of empty function with pass statement:
```python
# This function does nothing (yet)
def lazy_func(param):
    pass
```
# Else statement
```python
if today == "holiday":
    print("Lucky you!")
else:
    print("Keep your chin up, then.")
    
print("It’s a day now!" if sun else "It’s a night for sure!")
```
#### Nested if-else statements
```python
if x < 100:
    print('x < 100')
else:
    if x == 100:
        print('x = 100')
    else:
        print('x > 100')
    print('This will be printed only because x >= 100')
```
