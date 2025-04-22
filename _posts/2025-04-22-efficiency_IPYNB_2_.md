---

---

# popcorn hack 1



```python
arr = [1, 2, 3, 4, 5]

# Constant time O(1): Accessing the third item (index 2)
print("Third item (O(1)):", arr[2])

# Linear time O(n): Looping through all items
print("All items (O(n)):")
for item in arr:
    print(item)

```

    Third item (O(1)): 3
    All items (O(n)):
    1
    2
    3
    4
    5


# popcorn hack 2


```python
def print_unique_pairs(arr):
    n = len(arr)
    for i in range(n):
        for j in range(i + 1, n):
            print(f"({arr[i]}, {arr[j]})")

# Example usage
arr = [1, 2, 3]
print_unique_pairs(arr)

```

    (1, 2)
    (1, 3)
    (2, 3)


# explanation

The outer loop runs n times.

The inner loop runs approximately n - i - 1 times per outer loop.

So total iterations ≈ n(n-1)/2, which simplifies to O(n²).

This happens because we are generating all pairs of items without repetition.

# popcorn hack 3

Which of these is inefficient for large inputs?

a Linear Time
b Factorial Time
c Constant Time
d Linearithic Time

Which of these can be represented by a nested loop?

a Logarithmic Time
b Linearithmic Time
c Quadratic Time
d Linear Time

Factorial time (O(n!)) is the most inefficient for large inputs because its growth rate increases explosively, making even small input sizes computationally expensive. Among the options for nested loops, quadratic time (O(n²)) is the most common result, as it typically arises when using two nested loops to compare or combine elements, such as generating all unique pairs in an array.

# Homework hacks


```python
def perform_operation(arr, complexity):
    if complexity == "constant":
        # O(1) - Return the first item
        return arr[0] if arr else None

    elif complexity == "linear":
        # O(n) - Print all items
        for item in arr:
            print(item)

    elif complexity == "quadratic":
        # O(n^2) - Print all pairs
        for i in range(len(arr)):
            for j in range(len(arr)):
                print(f"({arr[i]}, {arr[j]})")

    else:
        print("Unsupported complexity type.")

# Example usage
arr = [5, 10, 15, 20, 25]
print("Constant:", perform_operation(arr, "constant"))
print("\nLinear:")
perform_operation(arr, "linear")
print("\nQuadratic:")
perform_operation(arr, "quadratic")

```

    Constant: 5
    
    Linear:
    5
    10
    15
    20
    25
    
    Quadratic:
    (5, 5)
    (5, 10)
    (5, 15)
    (5, 20)
    (5, 25)
    (10, 5)
    (10, 10)
    (10, 15)
    (10, 20)
    (10, 25)
    (15, 5)
    (15, 10)
    (15, 15)
    (15, 20)
    (15, 25)
    (20, 5)
    (20, 10)
    (20, 15)
    (20, 20)
    (20, 25)
    (25, 5)
    (25, 10)
    (25, 15)
    (25, 20)
    (25, 25)

