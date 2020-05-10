# Description:
Lucky tickets are a kind of mathematical entertainment. A ticket is considered lucky if the sum of the first 3 digits coincides with the sum of the last 3 digits of the ticket number.
You are supposed to write a program that checks whether the two sums are equal. The code snippet below displays "Lucky" if they do and "Ordinary" otherwise.

However, some parts of the code are missing. Fill in the blanks to make it work!

Input: a string of 6 digits.

Output: either "Lucky" or "Ordinary" (without quotes).

```
Sample Input 1:

090234
```
```
Sample Output 1:

Lucky
```
```
Sample Input 2:

123456
```
```
Sample Output 2:

Ordinary
```
# Solution
```python
# Save the input in this variable
ticket = int(input())

# Add up the digits for each half
half1 = (ticket // 100000 % 10) + (ticket // 10000 % 10) + (ticket // 1000 % 10)
half2 = (ticket // 100 % 10) + (ticket // 10 % 10) + (ticket % 10)

# Thanks to you, this code will work
if half1 == half2:
    print("Lucky")
else:
    print("Ordinary")
```
