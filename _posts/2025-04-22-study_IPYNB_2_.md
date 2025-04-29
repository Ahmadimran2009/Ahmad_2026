---
layout: post
title: Binary and logic gates
description: notes on binary and logic gates
courses: {'csp': {'week': 25}}
author: Ahmad Imran
type: ccc
---

# Binary hacks
---

# popcorn hack 1



```python
def binary_to_decimal(binary_str):
    decimal = 0
    for i in range(len(binary_str)):
        decimal += int(binary_str[-(i + 1)]) * (2 ** i)
    return decimal

#Get user input
binary_input = input("Enter a binary number: ")
decimal_output = binary_to_decimal(binary_input)
print(f"The decimal representation of {binary_input} is {decimal_output}.")

```

    The decimal representation of 1000100 is 68.


# popcorn hack 2


```python
import random
import time

def binary_addition_battle():
    num1 = bin(random.randint(0, 255))[2:]
    num2 = bin(random.randint(0, 255))[2:]
    
    print("\n=== Binary Addition Battle ===")
    print(f"Number 1: {num1}")
    print(f"Number 2: {num2}")
    
    start_time = time.time()
    user_answer = input("Your answer (in binary): ").strip()
    end_time = time.time()
    
    correct_answer = bin(int(num1, 2) + int(num2, 2))[2:]
    
    if user_answer == correct_answer:
        print(f"✅ Correct! You took {end_time - start_time:.2f} seconds. (+10 points)")
        return 10
    else:
        print(f"❌ Wrong! Correct answer was {correct_answer}. (-5 points)")
        return -5

def binary_decimal_speed_challenge():
    decimal_number = random.randint(0, 255)
    binary_number = bin(random.randint(0, 255))[2:]
    
    print("\n=== Binary-Decimal Speed Challenge ===")
    
    # Decimal to Binary
    print(f"Convert decimal {decimal_number} to binary:")
    start_time = time.time()
    user_binary = input("Your answer: ").strip()
    correct_binary = bin(decimal_number)[2:]
    end_time = time.time()
    
    points = 0
    if user_binary == correct_binary:
        print(f"✅ Correct! (+1 point)")
        points += 1
    else:
        print(f"❌ Wrong! Correct answer: {correct_binary}")
    
    # Binary to Decimal
    print(f"\nConvert binary {binary_number} to decimal:")
    start_time2 = time.time()
    user_decimal = input("Your answer: ").strip()
    correct_decimal = str(int(binary_number, 2))
    end_time2 = time.time()
    
    if user_decimal == correct_decimal:
        print(f"✅ Correct! (+1 point)")
        points += 1
    else:
        print(f"❌ Wrong! Correct answer: {correct_decimal}")
    
    print(f"Total time: {end_time - start_time + end_time2 - start_time2:.2f} seconds")
    return points

# Main game flow
def play_game():
    total_score = 0
    print("🎮 Welcome to Popcorn Hack 2!\n")
    
    total_score += binary_addition_battle()
    total_score += binary_decimal_speed_challenge()
    
    print(f"\n🏆 Final Score: {total_score} points")

# Run the game
play_game()

```

    🎮 Welcome to Popcorn Hack 2!
    
    
    === Binary Addition Battle ===
    Number 1: 11011101
    Number 2: 1110100
    ❌ Wrong! Correct answer was 101010001. (-5 points)
    
    === Binary-Decimal Speed Challenge ===
    Convert decimal 237 to binary:
    ❌ Wrong! Correct answer: 11101101
    
    Convert binary 1001100 to decimal:
    ❌ Wrong! Correct answer: 76
    Total time: 5.05 seconds
    
    🏆 Final Score: -5 points


# Homework hack

To convert a binary number to decimal, you multiply each bit by 2 raised to its position power (starting from the right at 0) and then add them up.

For 11111111:
Each bit is 1, so you add:
2
7
+
2
6
+
2
5
+
2
4
+
2
3
+
2
2
+
2
1
+
2
0
=
128
+
64
+
32
+
16
+
8
+
4
+
2
+
1
=
255
2 
7
 +2 
6
 +2 
5
 +2 
4
 +2 
3
 +2 
2
 +2 
1
 +2 
0
 =128+64+32+16+8+4+2+1=255

✅ So, 11111111 in binary = 255 in decimal

---

# Logic gate hacks

---

# popcorn hack 1

**Q:**  
What are methods of real-world purpose that using logic gates can implement? Explain deeper if using our listed impacts, explaining why this impact is helpful.

**A:**  
Logic gates are used in real-world systems like:

- **Computers and Smartphones:**  
  Logic gates control how computers perform calculations, store memory, and make decisions. Without logic gates, modern devices wouldn’t work because they need to process millions of logical operations every second.

- **Medical Devices:**  
  Devices like pacemakers use logic gates to monitor and regulate heartbeats. This impact is **life-saving** because it ensures that if the heart’s rhythm is abnormal, the device automatically corrects it.

- **Traffic Lights:**  
  Traffic light systems use logic gates to change lights based on sensors (like if a car is waiting). This is **helpful** because it improves traffic flow and safety, making streets more efficient and preventing accidents.

- **Security Systems:**  
  Alarm systems use logic gates to activate alarms only when certain conditions (like door open **and** motion detected) are true. This is **helpful** because it increases protection by being accurate — not triggering false alarms easily.

# Popcorn Hack 2

**Q:**  
A digital circuit receives three binary inputs: X, Y, and Z. The circuit outputs 1 if and only if X AND Y are both 1, OR Z is 1.

Which expression matches?

**Answer:**  
**A. (X AND Y) OR Z**

**Explanation:**  
- First, if both **X AND Y are 1**, the output should be 1.
- Also, if **Z is 1** (no matter X or Y), the output should be 1.
- That matches **(X AND Y) OR Z**.

# homework hack


```python
def secure_entry_system(keycard, pin, voice_auth):
    def AND(a, b):
        return a & b  # AND logic

    # All three conditions must be true
    return AND(AND(keycard, pin), voice_auth)

# Test cases
print(secure_entry_system(1, 1, 1))  # Expected Output: 1 (Access Granted)
print(secure_entry_system(1, 1, 0))  # Expected Output: 0 (Access Denied)
print(secure_entry_system(1, 0, 1))  # Expected Output: 0 (Access Denied)
print(secure_entry_system(0, 1, 1))  # Expected Output: 0 (Access Denied)

```

    1
    0
    0
    0


Now you must have keycard, pin, and voice authorization all set to 1 to get access (1 = Access Granted).

If any one is missing (0), access is denied.
