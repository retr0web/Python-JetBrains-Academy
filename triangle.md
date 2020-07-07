Draw a triangle of a given height<br>
Input 3
# Solution
```python
n = int(input())
n_triangle = n * 2 - 1
for i in range(n):
    string = '#' * (2 * i + 1)
    print(string.center(n_triangle))
```
