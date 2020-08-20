# Python-JetBrains-Academy

This is a cheatsheet of what I've learned so far about python (3.x) on [JetBrains Academy](https://hyperskill.org/)<br>
- [What is PEP?](#what-is-pep)
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
#### Scope
When you define a variable it becomes either global or local. If a variable is defined at the top-level of the module it is considered global. That means that you can refer to this variable from every code block in your program. Global variables can be useful when you need to share state information or some configuration between different functions. For example, you can store the name of a current user in a global variable and then use it where needed. It makes your code easier to change: in order to set a new user name you will only have to change a single variable.<br>

Local variables are created when you define them in the body of a function. So its name can only be resolved inside the current function's scope. It lets you avoid issues with side-effects that may happen when using global variables.<br>
Thus, a global variable can be accessed both from the top-level of the module and the function's body. On the other hand, a local variable is only visible inside the nearest scope and cannot be accessed from the outside.<br>
A variable resolution in Python follows the <b>LEGB rule</b>. That means that the interpreter looks for a name in the following order:<br>
1. <b>Locals</b>. Variables defined within the function body and not declared global.
2. <b>Enclosing</b>. Names of the local scope in all enclosing functions from inner to outer.
3. <b>Globals</b>. Names defined at the top-level of a module or declared global with a <b>global</b> keyword.
4. <b>Built-in</b>. Any built-in name in Python.
#### Global and nonlocal keywords
We already mentioned one way to assign a global variable: make a definition at the top-level of a module. But there is also a special keyword global that allows us to declare a variable global inside a function's body.<br>

You can't change the value of a global variable inside the function without using the <b>global</b> keyword:
```python
x = 1
def print_global():
    print(x)
 
print_global()  # 1
 
def modify_global():
    print(x)
    x = x + 1
 
modify_global()  # UnboundLocalError
```
<b>nonlocal</b> keyword lets us assign to variables in the outer (but not global) scope:
```python
def func():
    x = 1
    def inner():
        x = 2
        print("inner:", x)
    inner()
    print("outer:", x)
 
def nonlocal_func():
    x = 1
    def inner():
        nonlocal x
        x = 2
        print("inner:", x)
    inner()
    print("outer:", x)
 
func()  # inner: 2
        # outer: 1
 
nonlocal_func()  # inner: 2
                 # outer: 2
```

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
# Strings methods
#### Chaining methods
* <b>str.replace(old, new[, count])</b> replaces all occurrences of the old string with the new one. The count parameter is optional, and if specified, only the first count occurrences are replaced in the given string.
* <b>str.upper()</b> converts all characters of the string to the upper case.

* <b>str.lower()</b> converts all characters of the string to the lower case.

* <b>str.title()</b> converts the first character of each word to upper case.

* <b>str.swapcase()</b> converts upper case to lower case and vice versa.

* <b>str.capitalize()</b> changes the first character of the string to the title case and the rest to the lower case.
#### Editing methods
* <b>str.lstrip([chars])</b> removes the leading characters (i.e. characters from the left side). If the argument chars isn’t specified, leading whitespaces are removed.

* <b>str.rstrip([chars])</b> removes the trailing characters (i.e. characters from the right side). The default for the argument chars is also whitespace.

* <b>str.strip([chars])</b> removes both the leading and the trailing characters. The default is whitespace.
```python
whitespace_string = "     hey      "
normal_string = "incomprehensibilities"
 
# delete spaces from the left side
whitespace_string.lstrip()  # "hey      "
 
# delete all "i" and "s" from the left side
normal_string.lstrip("is")  # "ncomprehensibilities"
 
# delete spaces from the right side
whitespace_string.rstrip()  # "     hey"
 
# delete all "i" and "s" from the right side
normal_string.rstrip("is")  # "incomprehensibilitie"
 
# no spaces from both sides
whitespace_string.strip()  # "hey"
 
# delete all trailing "i" and "s" from both sides
normal_string.strip("is")  # "ncomprehensibilitie"
```
# Split and Join methods for String
The <b>split()</b> method divides a string into substrings by a separator. If the separator isn't given, whitespace is used as a default. The method returns a list of all the substrings and, notably, the separator itself is not included in any of the substrings.
```python
# split example
definition = input()  # 'Coin of the realm is the legal money of the country' 
 
definition.split()
# ['Coin', 'of', 'the', 'realm', 'is', 'the', 'legal', 'money', 'of', 'the', 'country']
 
definition.split("legal")
# ['Coin of the realm is the ', ' money of the country']
```
You can also specify how many times the split is going to be done with the maxsplit argument that comes after the separator. The number of elements in the resulting list will be equal to maxsplit + 1.

If the argument isn't specified, all possible splits are made.
```python
# maxsplit example
definition = input()  # 'Coin of the realm is the legal money of the country'
 
definition.split("of", 1)
# ['Coin ', ' the realm is the legal money of the country']
 
definition.split("of")
# ['Coin ', ' the realm is the legal money ', ' the country']
```
The <b>join()</b> method is used to create a string out of a collection of strings. However, its use has a number of limitations. First, the argument of the method must be an iterable object with strings as its elements. And second, the method must be applied to a separator: a string that will separate the elements in a resulting string object. See below the examples of that:
```python
word_list  = ["dog", "cat", "rabbit", "parrot"]
 
" ".join(word_list)  # "dog cat rabbit parrot"
"".join(word_list)  # "dogcatrabbitparrot"
"_".join(word_list)  # "dog_cat_rabbit_parrot"
" and ".join(word_list)  # "dog and cat and rabbit and parrot"
```
The splitlines() method is similar to split(), but it is used specifically to split the string by the line boundaries. There are many escape sequences that signify the end of the line, but the split() method can only take one separator. So this is where the splitlines() method comes in handy:
```python
# splitlines example
long_text = 'first line\nsecond line\rthird line\r\nforth line'
 
long_text.splitlines()
# ['first line', 'second line', 'third line', 'forth line']
```
# Multiline strings
```python
print("""This
is
a
multi-line
string""")
```
```
This
is
a
multi-line
string
```
# String formating
#### % operator
Thus, the variable to the right of % was included in the string to the left of it. If we'd wanted to divide 11 by 3, the / operator would have returned a float number with a lot of decimal places.
```python
print(11 / 3)  # 3.6666666666666665
```
With % character, we could control the number of decimal places, for example, reduce their number to 3 or 2:
```python
print('%.3f' % (11/3))  # 3.667
print('%.2f' % (11/3))  # 3.67
```
#### format() method
```python
print('Mix {}, {} and a {} to make an ideal omelet.'.format('2 eggs', '30 g of milk', 'pinch of salt'))

print('{0} in the {1} by Frank Sinatra'.format('Strangers', 'Night'))

print('The {film} at {theatre} was {adjective}!'.format(film='Lord of the Rings',
                                                        adjective='incredible',
                                                        theatre='BFI IMAX'))
                                                        
print('The {0} was {adjective}!'.format('Lord of the Rings', adjective='incredible'))
```
#### Formated string literals
```python
hundred_percent_number = 1823
needed_percent = 16
needed_percent_number = hundred_percent_number * needed_percent / 100
 
print(f'{needed_percent}% from {hundred_percent_number} is {needed_percent_number}')
# 16% from 1823 is 291.68
 
print(f'Rounding {needed_percent_number} to 1 decimal place is {needed_percent_number:.1f}')
# Rounding 291.68 to 1 decimal place is 291.7
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
# While loop
```python
number = 0
while number < 5:
    print(number)
    number += 1
print('Now, number is greater than or equal to 5')
```
If you delete the part of the conditional code where you increase the value of a counter, you will bump into the infinite loop. What does it mean? Since you don’t increase your variable, a condition never becomes false and can work forever. Usually, it is a logical fallacy, and you'll have to stop the loop using special statements or finishing the loop manually.
# For loop
```python
oceans = ['Atlantic', 'Pacific', 'Indian', 'Southern', 'Arctic']
for ocean in oceans:
    print(ocean)
```
Even strings are iterable, so you can spell the word, for example:
```python
for char in 'magic':
    print(char)
    
# Output
m
a
g
i
c
```
#### Range function
The range() function is used to specify the number of iterations. It returns a sequence of numbers from 0 (by default) and ends at a specified number. Be careful: the last number won’t be in the output.
```python
for i in range(5):
    print(i)
    
# Output
0
1
2
3
4
```
You can change the starting value if you’re not satisfied with 0, moreover, you can configure the increment (step) value by adding a third parameter:
```python
for i in range(5, 45, 10):
    print(i)
```
#### Nested loops
```python
names = ['Rose', 'Daniel']
surnames = ['Miller']
for name in names:
    for surname in surnames:
         print(name, surname)
```
#### Loop control statements
###### Break
```python
pets = ['dog', 'cat', 'parrot']
for pet in pets:
    print(pet)
    if pet == 'cat':
        break
```
###### Continue
```python
pets = ['dog', 'cat', 'parrot']
for pet in pets:
    if pet == 'dog':
        continue
    print(pet)
```
###### Loop else statement
If the loop didn’t encounter the break statement, an else clause can be used to specify a block of code to be executed after the loop.
```python
pets = ['dog', 'cat', 'parrot']
for pet in pets:
    print(pet)
else:
    print('We need a turtle!')
```
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
# Lists
```python
dog_breeds = ['corgi', 'labrador', 'poodle', 'jack russel']
print(dog_breeds)  # ['corgi', 'labrador', 'poodle', 'jack russel']

numbers = [1, 2, 3, 4, 5]
print(numbers)  # [1, 2, 3, 4, 5]

list_out_of_string = list('danger!')
print(list_out_of_string)  # ['d', 'a', 'n', 'g', 'e', 'r', '!']
 
list_out_of_integer = list(235)  # TypeError: 'int' object is not iterable

multi_element_list = list('danger!')
print(multi_element_list )  # ['d', 'a', 'n', 'g', 'e', 'r', '!']
 
single_element_list = ['danger!']
print(single_element_list)  # ['danger!']
```
#### Creating empty list
```python
empty_list_1 = list()
empty_list_2 = []
```
#### Length of list
```python
numbers = [1, 2, 3, 4, 5]
print(len(numbers))  # 5
 
empty_list = list()
print(len(empty_list))  # 0
 
single_element_list = ['danger!']
print(len(single_element_list))  # 1
 
multi_elements_list = list('danger!')
print(len(multi_elements_list))  # 7
```
#### List comprehension
List comprehension is a way of making new lists. It allows you to create a list from any iterable object in a concise and efficient manner. See the basic syntax below:
```python
new_list = [x for x in some_iterable]

# the equivalent code
new_list = []
for x in some_iterable:
    new_list.append(x)
```
You may wonder why there is a need for list comprehensions at all since we have a list() function. Obviously, list comprehensions are used not just for copying elements from some iterable into a list, but mainly for modifying them in some way to create a specific new list. In this case, in the first place of the list comprehension, we write some function of our variable. For example, the code below shows how to create a list of squared numbers.
```python
# squared numbers
numbers = [1, 2, 3]
square_list = [x * x for x in numbers]  # [1, 4, 9]

# from string to float
strings = ["8.9", "6.0", "8.1", "7.5"]
floats = [float(num) for num in strings]  # [8.9, 6.0, 8.1, 7.5]
```
#### List comprehension with if
Another way to modify the original iterable object is by introducing the if statement into the list comprehension.
```python
# odd numbers
numbers = [4, 8, 15, 16, 23, 42, 108]
odd_list = [x for x in numbers if x % 2 == 1]  # [15, 23]

# conditions with functions
text = ["function", "is", "a", "synonym", "of", "occupation"]
words_tion = [word for word in text if word.endswith("tion")]  
print(words_tion)  # ["function", "occupation"]
```
Finally, we can introduce the else statement in list comprehension. The syntax here differs a bit: <b>x if condition else y for x in some_iterable </b>. Using this, we can, for example, get 0 a new list for each negative number in the old list:
```python
old_list = [8, 13, -7, 4, -9, 2, 10]
new_list = [num if num >= 0 else 0 for num in old_list]
print(new_list)  # [8, 13, 0, 4, 0, 2, 10]
```
# Any() and All()
The result of the <b>any()</b> function call is the boolean value: it returns True if an element or a group of elements in an iterable object are evaluated True. Otherwise, it returns False. Let’s take a look at the example. Imagine that you and your friends, Jam and Andy, wrote a test and got your results in the form of a list with True and False values. The test is passed if at least one answer is correct. Now you need to check if you and your friends passed that test.
```python
your_results = [True, False, False]
print(any(your_results))  # True

andy_results = [False, False, False]
print(any(andy_results))  # False
```
The <b>all()</b> function works pretty much like any(). The difference is that <b>all()</b> function checks if all the elements of an iterable object are True and returns True if they are. Otherwise, you get False. Do you remember the story from the previous section where we checked the results of the test? Let's proceed. Imagine yet another test, this time the final one. To succeed, you should answer all the questions correctly. How did it go this time for you and the two friends of yours?
```python
your_results = [True, False, False]
print(all(your_results))  # False

andy_results = [True, True, True]
print(all(andy_results))  # True
```
#### Conditions
Coders often use any() and all() functions in conditions. It helps to check the elements of iterable objects quickly and to avoid complex constructions.

Let's choose a candy box for Valentine's Day. Each box contains several types of sweets. But you are interested in the even amount of candies of each type because, obviously, you will share them with your valentine.
```python
box = [10, 20, 33]
 
if any([candy % 2 for candy in box]):
    print("It is not a proper gift.")
else:
    print("Perfect!")
```
Short and sweet, isn't it? Life is like a box of chocolates! As long as the values you deal with can be converted to True and False, it's safe to use both functions in conditions.
# Dictionary
A dictionary consists of a collection of key-value pairs. Each key-value pair maps the key to its associated value. If you already know the values needed, then the easiest way to create a dictionary is to use the curly braces with a comma-separated list of <b>key: value</b> pairs. If you want to create an empty dictionary, you can do so with the help of curly braces as well. Note that values in a dictionary can be of different types.
```python
birds = {"pigeon": 12, "sparrow": 5, "red crossbill": 1}
prices = {'espresso': 5.0, 'americano': 8.0, 'latte': 10, 'pastry': 'various prices'}
empty_dict = {}
 
print(type(birds))  # <class 'dict'>
print(type(prices))  # <class 'dict'>
print(type(empty_dict))  # <class 'dict'>
```
```python
another_empty_dict = dict()  # using the dict constructor
```
When creating a non-empty dictionary, a dict constructor can take a dictionary as an argument, and / or future dictionary keys as arguments with assigned values, as in the example:
```python
# note that the future dictionary keys are listed without quotes
prices_with_constr = dict({'espresso': 5.0}, americano=8.0, latte=10, pastry='various prices')
```
```python
# a nested dictionary example
my_pets = {'dog': {'name': 'Dolly', 'breed': 'collie'},
           'cat': {'name': 'Fluffy', 'breed': 'maine coon'}}
 
# another nested dictionary example
# note that keys of the outer dictionary are numbers
digits = {1: {'Word': 'one', 'Roman': 'I'}, 
          2: {'Word': 'two', 'Roman': 'II'}, 
          3: {'Word': 'three', 'Roman': 'III'}, 
          4: {'Word': 'four', 'Roman': 'IV'}, 
          5: {'Word': 'five', 'Roman': 'V'}}
```
#### Accessing items
```python
my_pet = {}
 
# add 3 keys and their values into the dictionary
my_pet['name'] = 'Dolly'
my_pet['animal'] = 'dog'
my_pet['breed'] = 'collie'
 
print(my_pet)  # {'name': 'Dolly', 'animal': 'dog', 'breed': 'collie'}
 
# get information from the dictionary about an added item
print(my_pet['name'])  # Dolly


# our nested dictionary once again:
my_pets = {'dog': {'name': 'Dolly', 'breed': 'collie'},
           'cat': {'name': 'Fluffy', 'breed': 'maine coon'}}
 
print(my_pets['cat'])  # {'name': 'Fluffy', 'breed': 'maine coon'}
 
print(my_pets['cat']['breed'])  # maine coon
```
#### Choosing keys
You can save object of any type in a dictionary, but not all of them qualify as a key. You need a good, unique key for each object in your collection. Still, this is not the only restriction on dictionary keys and we will cover them later. For now, safely use numbers and strings.<br>

When a key has already been added to your dictionary, its old value will be overridden:
```python
trilogy = {'IV': 'Star Wars', 'V': 'The Empire Strikes Back', 'VI': 'Return of the Jedi'}
print(trilogy['IV'])  # Star Wars
 
trilogy['IV'] = 'A New Hope'
print(trilogy['IV'])  # A New Hope
```
# Modules
#### Connect module
```python
import super_module

super_module.super_function()  # calling a function defined in super_module

print(super_module.super_variable)  # accessing a variable defined in super_module
```
#### Import exact function from module
```python
from super_module import super_function  # import one function from super_module

super_function()  # super_function is now available directly at the current module

super_module.super_function()  # note, that in this case name super_module is not imported, 
                               # so this line leads to an error
```
A good practice is to load a single module in a single line and put all your imports at the top of the file because it increases readability.
```python
import module1
import module2
import module3

# the rest of module code goes here
```
# Random module
```python
import random

print(random.random())  # 0.5557276751294531
```
We can also control the pseudo-random behavior by specifying the seed manually, i.e. configure the new sequence of pseudo-random numbers using <b>random.seed(x)</b> function. You can set your own number or omit the optional argument x and consequently current system time would be used by default.
```python
random.seed()
print(random.random())  # 0.956177930864557
```
#### Random basic functions
```python
print(random.uniform(3, 100))  # 35.94079523197162  # returns a pseudo-random float number in the range between a and b

print(random.randint(35, 53))  # 52  # returns a pseudo-random integer number in the range between a and b

print(random.choice('Voldemort'))  #  m, returns pseudo-random element from non-empty sequences

# random.randrange(a, b, c) – returns a pseudo-random number from a range between a and b with a step c. 
# Just like with the range() function, the start and step arguments may be omitted with the default values 0 and 1 respectively.
# It means that the function can take one, two, or three parameters

print(random.randrange(3, 100, 5))  # 18
print(random.randrange(1, 5))       # 2
print(random.randrange(100))        # 44

tiny_list = ['a', 'apple', 'b', 'banana', 'c', 'cat']
random.shuffle(tiny_list) # shuffles a sequence. Attention: it doesn't work with immutable datatypes
print(tiny_list)  # ['apple', 'banana', 'a', 'cat', 'b', 'c']

print(random.sample(range(100), 3))  # [24, 33, 91]  # returns a pseudo-random k length list from a population sequence. This function is used for random sampling without replacement
```
# Class
```python
# class syntax
class MyClass:
    var = ...  # some variable

    def do_smt(self):
    # some method
```
Generally, class name starts with a capital letter and it is usually a noun or a noun phrase. The names of the classes follow the CapWords convention: meaning that if it's a phrase, all words in the phrase are capitalized and written without underscores between them.
```python
# good class name
class MyClass:
    ...

# not so good class name:
class My_class:
```
#### Class attribute
```python
class Book:
    material = "paper"
    cover = "paperback"
    all_books = []
```
#### Class instances
```python
my_book = Book()

print(my_book.material)  # "paper"
print(my_book.cover)  # "paperback"
print(my_book.all_books)  # []
```
#### def __init__ (constructor)
```python
class River:
    # list of all rivers
    all_rivers = []
    
    def __init__(self, name, length):
        self.name = name
        self.length = length
        # add current river to the list of all rivers
        River.all_rivers.append(self)

volga = River("Volga", 3530)
seine = River("Seine", 776)
nile = River("Nile", 6852)
```
You may have noticed that our <b>__init__</b> method had another argument besides name and length: <b>self</b>. The self argument represents a particular instance of the class and allows us to access its attributes and methods.
<br>
Note that when we actually call an object's method we don't write the self argument in the brackets. The self parameter (that represents a particular instance of the class) is passed to the instance method implicitly when it is called. So there are actually two ways to call an instance method: self.method() or class.method(self). In our example it would look like this:
```python
# self.method()
volga.get_info()
# The length of the Volga is 3530 km

# class.method(self)
River.get_info(volga)
# The length of the Volga is 3530 km
```
#### Method syntax
```python
class MyClass:
    # the constructor
    def __init__(self, arg1):
        self.att = arg1

    # custom method
    def do_smt(self):
        # does something
```
###### Methods vs functions
Though they are quite similar, Python does make a distinction between methods and functions. To quote the official documentation, "a method is a function that 'belongs to' an object." Since we're interested in OOP, we'll specifically be looking at methods associated with class instances. So each time you want to create a method, you should put <b>self</b> keyword as first argument.
