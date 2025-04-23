---
layout: post
title: Study guide
description: My study guide for the course.
courses: {'csp': {'week': 25}}
author: Ahmad Imran
type: ccc
---

# 🖥️ Computer Science Exam Study Guide (AP/Intro Java)

## 📘 Big Ideas

| Big Idea | Description |
|----------|-------------|
| 1. Program Design and Algorithm Development | Writing code with logic, methods, and control structures. |
| 2. Data Structures | Using arrays, ArrayLists, and 2D arrays to organize data. |
| 3. Algorithms and Control Structures | Applying loops, conditionals, recursion to solve problems. |
| 4. Code Implementation | Translating logic into Java syntax. |
| 5. Code Analysis | Tracing and understanding what Java code does. |
| 6. Computing Innovations | Broader social impacts of computing (lightly tested). |

---

## 📚 Table of Contents

1. [Java Basics](#java-basics)
2. [Data Types & Variables](#data-types--variables)
3. [Operators & Expressions](#operators--expressions)
4. [Control Structures](#control-structures)
5. [Objects & Classes](#objects--classes)
6. [Arrays & ArrayLists](#arrays--arraylists)
7. [Methods](#methods)
8. [Inheritance & Polymorphism](#inheritance--polymorphism)
9. [Searching & Sorting](#searching--sorting)
10. [Error Handling](#error-handling)
11. [FRQ Tips](#frq-tips)
12. [MCQ Strategies](#mcq-strategies)

---

## Java Basics

```java
public class MyClass {
    public static void main(String[] args) {
        System.out.println("Hello World!");
    }
}
```

- Single-line comment: `//`
- Multi-line comment: `/* ... */`

---

## Data Types & Variables

| Type     | Example               | Description          |
|----------|-----------------------|----------------------|
| int      | int age = 17;         | Whole number         |
| double   | double pi = 3.14;     | Decimal number       |
| boolean  | boolean isOn = true;  | True or false        |
| char     | char grade = 'A';     | Single character     |
| String   | String name = "Bob";  | Sequence of characters |

---

## Operators & Expressions

- Arithmetic: `+`, `-`, `*`, `/`, `%`
- Relational: `==`, `!=`, `<`, `>`, `<=`, `>=`
- Logical: `&&`, `||`, `!`
- Assignment: `=`, `+=`, `-=`, `*=`, `/=`

---

## Control Structures

### If / Else

```java
if (x > 0) {
    System.out.println("Positive");
} else {
    System.out.println("Zero or negative");
}
```

### For Loop

```java
for (int i = 0; i < 5; i++) {
    System.out.println(i);
}
```

### While Loop

```java
int i = 0;
while (i < 5) {
    System.out.println(i);
    i++;
}
```

### Do-While Loop

```java
int i = 0;
do {
    System.out.println(i);
    i++;
} while (i < 5);
```

---

## Objects & Classes

### Defining a Class

```java
public class Dog {
    private String name;

    public Dog(String n) {
        name = n;
    }

    public String getName() {
        return name;
    }
}
```

### Using an Object

```java
Dog d = new Dog("Buddy");
System.out.println(d.getName());
```

---

## Arrays & ArrayLists

### Arrays

```java
int[] nums = {1, 2, 3};
System.out.println(nums[0]);
```

### ArrayLists

```java
import java.util.ArrayList;

ArrayList<String> list = new ArrayList<>();
list.add("Hello");
System.out.println(list.get(0));
```

| Method      | Description             |
|-------------|-------------------------|
| .add()      | Add element             |
| .get()      | Access element          |
| .set()      | Replace element         |
| .remove()   | Remove element          |
| .size()     | Get number of elements  |

---

## Methods

```java
public static int square(int x) {
    return x * x;
}
```

- Parameters = Inputs
- Return type = What it gives back
- Void = No return value

---

## Inheritance & Polymorphism

### Inheritance

```java
public class Animal {
    public void speak() {
        System.out.println("Animal sound");
    }
}

public class Dog extends Animal {
    public void speak() {
        System.out.println("Bark");
    }
}
```

### Polymorphism

```java
Animal a = new Dog();
a.speak(); // Bark
```

---

## Searching & Sorting

### Linear Search

```java
public int linearSearch(int[] arr, int target) {
    for (int i = 0; i < arr.length; i++) {
        if (arr[i] == target) return i;
    }
    return -1;
}
```

### Binary Search (sorted array)

```java
public int binarySearch(int[] arr, int target) {
    int low = 0, high = arr.length - 1;
    while (low <= high) {
        int mid = (low + high) / 2;
        if (arr[mid] == target) return mid;
        else if (arr[mid] < target) low = mid + 1;
        else high = mid - 1;
    }
    return -1;
}
```

### Selection Sort

```java
public void selectionSort(int[] arr) {
    for (int i = 0; i < arr.length - 1; i++) {
        int min = i;
        for (int j = i + 1; j < arr.length; j++) {
            if (arr[j] < arr[min]) {
                min = j;
            }
        }
        int temp = arr[i];
        arr[i] = arr[min];
        arr[min] = temp;
    }
}
```

---

## Error Handling

### Types of Errors

- Compile-time: Syntax issues
- Run-time: Crashes (e.g., divide by 0)
- Logic: Wrong result

### Try-Catch

```java
try {
    int x = 5 / 0;
} catch (ArithmeticException e) {
    System.out.println("Division by zero error");
}
```

---

## FRQ Tips

- Follow the method signature exactly.
- Use helper methods to break down big problems.
- Write comments if stuck: `// TODO: fix loop logic`
- Loop through arrays with `.length` or `.size()`
- Initialize all variables before use
- Use consistent indentation and clear naming
- Even partial work can earn points

---

## MCQ Strategies

- Underline key words in the question.
- Eliminate obvious wrong choices.
- Trace code step-by-step.
- Watch out for:
  - Off-by-one errors
  - Integer division (`5 / 2 = 2`)
  - `.equals()` vs `==` for Strings
- If stuck, make your best guess—no penalty for wrong answers

## 🧩 Big Ideas to Study

### 1. 🛠️ Creative Development
- Understand how programs are designed and developed.
- Know what **collaborative programming** looks like (e.g., pair programming, version control).
- Be able to **explain algorithms in plain English**—what each step does and why.

### 2. 📊 Data
- Learn how data is **stored, organized, and visualized**.
- Identify **patterns and trends** in datasets.
- Know different file formats like **CSV** and **JSON**, and understand the purpose of **metadata**.

### 3. ⚙️ Algorithms and Programming
- Master key programming concepts:
  - **Searching and sorting**
  - **Conditionals** (`if`, `else`)
  - **Loops** (`for`, `while`)
- Understand how **functions** work, including **parameters** and **return values**.
- Be comfortable writing and reading **pseudocode**.

### 4. 🌐 Computing Systems and Networks
- Know how the **Internet** works, including:
  - **IP addresses**
  - **DNS**
- Understand how data moves:
  - **Packets**
  - **Protocols** like **HTTP**, **TCP/IP**
- Be able to explain common **cybersecurity risks**:
  - **DDoS attacks**
  - **Phishing**
  - **Malware**

### 5. 🌍 Impact of Computing
- Be able to give examples of how computing affects:
  - **Society**
  - **Culture**
  - **Economy**
- Understand the **digital divide** and **bias in algorithms and data**.

---

## 🧠 Key Vocabulary to Know

- **Abstraction** – Simplifying complexity by hiding unnecessary detail.
- **Algorithm** – A set of steps to solve a problem.
- **Binary** – Base-2 number system (only 0s and 1s).
- **Encryption** – Securing data through encoding.
- **Lossless vs. Lossy Compression** – Keeping all data vs. removing less important data.
- **Overflow Error** – When a calculation exceeds the limits of storage.
- **Heuristic** – A quick, approximate method for problem-solving.
- **Simulation** – Modeling real-world processes with a computer program.

---

## ✅ Create Task Tips

- **Clearly explain** your algorithm's purpose.
- Use **selection** (`if` statements) and **iteration** (`loops`).
- Demonstrate how your **data is used** to solve a problem.
- Include **meaningful comments** in your code to improve clarity.

---

## 📚 Study Tips

- Practice writing in **pseudocode**—focus on logic, not syntax.
- Use the **College Board's practice questions** and scoring guides.
- Review your **Create Performance Task** and reflect on feedback.
- Use **flashcards** or **quiz apps** to test yourself on vocab.

---
