---
layout: post
title: Ahmads blog!!!
description: click here to see my blog
type: issues
comments: True
---

```python
# Homework for 3.6 and 3.7
# Function to classify age group
def classify_age(age):
    if 3 <= age <= 12:
        return "Child"
    elif 13 <= age <= 17:
        return "Teenager"
    else:
        return "Adult"

# Main program for age classification
try:
    # Get user input
    age_input = int(input("Please enter your age: "))
    # Classify and print result
    age_group = classify_age(age_input)
    print(f"You are classified as: {age_group}")
except ValueError:
    print("Please enter a valid number for age.")

```

    You are classified as: Teenager



```python
# Popcorn hack number 1: Example weather condition
weather = "Sunny"
if weather == "Sunny":
    print("It's a bright day!")
elif weather == "Rainy":
    print("Don't forget your umbrella!")
elif weather == "Cloudy":
    print("It might rain later.")
else:
    print("Weather condition unknown.")

```

    It's a bright day!



```python
# Popcorn hack number 3: Classifying traffic light status
light = "Yellow"
message = (
    "Go!" if light == "Green" else
    "Slow down and prepare to stop." if light == "Yellow" else
    "Stop!" if light == "Red" else
    "Unknown light status."
)
print(message)

```

    Slow down and prepare to stop.



```python
# Popcorn hack number 3: Classifying traffic light status
light = "Yellow"
message = (
    "Go!" if light == "Green" else
    "Slow down and prepare to stop." if light == "Yellow" else
    "Stop!" if light == "Red" else
    "Unknown light status."
)
print(message)

```

    Slow down and prepare to stop.

