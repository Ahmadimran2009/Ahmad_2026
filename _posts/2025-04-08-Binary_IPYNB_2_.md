---
layout: post
categories: ['CSP Big Idea 3']
title: Binary Search
description: Hacks for binary search
courses: {'csp': {'week': 25}}
author: Ahmad Imran
type: ccc
---

# Popcorn hack 1

Which of the following conditions must be met in order for the procedure to work as intended? Explain why.

a. The length of numList must be even

b. The list numList must not contain any duplicate values

c. The values in numList must be in sorted order

d. The value of target must not be equal to -1

The answer is C because the list must be sorted because procedures like binary search use order to decide where to search next. Without sorting, the algorithm can't make correct decisions and may fail.

# Popcorn hack 2

Which of the following statements correctly describes a disadvantage of binary search compared to linear search? Explain why your answer is correct and why the others are wrong.

a Binary search takes more time on average than linear search  
b Binary search cannot be used on unsorted lists without modifications  
c Binary search always ret urns the first occurrence of the target  
d Binary search can only be used on lists with unique values

The correct answer is B because binary search only works properly if the list is sorted. Without sorting, it can’t reliably decide whether to search left or right, which breaks the logic of the search.

# Popcorn hack 3



```python
def binary_search(arr, target):
    left = 0
    right = len(arr) - 1
    
    while left <= right:
        mid = (left + right) // 2
        
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            left = mid + 1
        else:
            right = mid - 1
    
    return -1  # Target not found

# Example usage:
letters = ['a', 'b', 'c', 'd', 'e', 'f', 'g']
print(binary_search(letters, 'c'))  # Output: 2

```

    2


# Homework Hack


```python
import pandas as pd

# Load the dataset
data = pd.read_csv("school_supplies.csv")

# Drop rows with missing values
data_cleaned = data.dropna()

# Sort the data by 'Price'
data_sorted = data_cleaned.sort_values(by="Price")

# Extract sorted prices as a list
price_list = data_sorted["Price"].tolist()

# Preview the sorted data
print("First few rows of sorted data:")
print(data_sorted.head())
print("Original row count:", len(data))
print("Cleaned row count:", len(data_cleaned))

# Binary search function
def binary_search_price(price_list, target):
    left, right = 0, len(price_list) - 1
    while left <= right:
        mid = (left + right) // 2
        if price_list[mid] == target:
            return True
        elif price_list[mid] < target:
            left = mid + 1
        else:
            right = mid - 1
    return False

# Prices to search for
search_prices = [1.25, 6.49, 10.00]

# Search and print results
for price in search_prices:
    found = binary_search_price(price_list, price)
    if found:
        print(f"Price ${price} was found in the list.")
    else:
        print(f"Price ${price} was NOT found in the list.")
```

    First few rows of sorted data:
            Product  Price
    5        Eraser   0.50
    14  Paper Clips   0.89
    2        Pencil   0.99
    9    Glue Stick   1.25
    1           Pen   1.50
    Original row count: 15
    Cleaned row count: 15
    Price $1.25 was found in the list.
    Price $6.49 was found in the list.
    Price $10.0 was NOT found in the list.

