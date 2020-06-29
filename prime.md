In math, we call a natural number prime if it's greater than 1 and can be evenly divided only by 1 and itself (without any remainder):<br>

2, 3, 5, 7, 11, 13, 17, ...<br>

Create a list of all primes up to 1000 in the code below. Just save this list into a variable prime_numbers, you don't have to print anything.<br>

Make use of any() or all() to check if a number n leaves a zero remainder when divided by values from 2 to n - 1 (inclusively).<br>

# Solution
```python
prime_numbers = [x for x in range(2, 1000) if all(x % y for y in range(2, x))]
```
