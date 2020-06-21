Given a numeric sequence, create a list in which each number will be a digit from this input string. <br>
Then use this list to calculate the running total, or cumulative sum. <br>
Essentially, it's a new list of partial sums that gets updated every time a new element appears.<br>
<br>
For example, we can transform the list [1, 2, 3]  to [1, 1 + 2, 1 + 2 + 3], which equals to [1, 3, 6].
#### Sample input
12345
#### Sample output
[1, 3, 6, 10, 15]
# Solution
```python
sequence = input("Input number: ")
place_holder = [int(n) for n in sequence]
result_list = []
result_list.append(place_holder[0])

for i in range(len(place_holder) - 1):
    result_list.append(result_list[i] + place_holder[i + 1])
print(result_list)
```
# Alternative solution
```python
numbers = [int(num) for num in input()]
print([sum(numbers[:i]) for i in range(1, len(numbers) + 1)])
```
