---
layout: post
title: Undecidable & Graphs
description: notes on AUndecidable & Graphs
courses: {'csp': {'week': 25}}
author: Ahmad Imran
type: ccc
---

# popcorn hack 1

False.

In a directed graph, an edge from node A to node B means there is a one-way connection from A to B. There is not necessarily a corresponding edge from B to A unless it is explicitly included in the graph.

So:

A → B does not imply B → A.

If both A → B and B → A exist, it's called a bidirectional or reciprocal edge, but that must be defined separately.

# popcorn hack 2

True.

Heuristics are designed to find solutions more quickly by using shortcuts or rules of thumb, but they don't always guarantee the most accurate or optimal solution. Exact algorithms, on the other hand, are designed to find the best possible solution, but they may take longer to compute.

# popcorn hack 3

True.

Heuristic algorithms like the Nearest Neighbor algorithm are faster and can provide good solutions for the Traveling Salesman Problem (TSP), but they do not guarantee an optimal solution. As the number of cities increases, the difference between the heuristic solution and the optimal solution can grow, and in some cases, the gap can become exponentially larger due to the nature of the problem's complexity.

# Homework

Social Network Analysis (SNA) uses graphs to study relationships in social networks, where users are represented as nodes and relationships as edges. In social media platforms, nodes could be individuals, and edges represent connections like friendships, follows, or interactions. For example, on Twitter, users are nodes, and the following relationship forms directed edges. Graph theory helps Twitter analyze influence by identifying users with many connections or interactions, and it also powers recommendation systems by exploring user connections. This approach helps understand information flow and user behavior across networks.

# popcorn hack 1

False.

An algorithm cannot solve an undecidable problem. By definition, an undecidable problem is one for which no algorithm can provide a solution for all possible inputs. These problems are beyond the scope of algorithmic resolution, as proven by results such as Turing's Halting Problem.

# popcorn hack 2

True.

If a programmer encounters an undecidable problem, they can often use a heuristic or approximation algorithm that works most of the time or in specific cases. While these algorithms may not guarantee a solution for every possible input, they can provide useful results in practice for many instances of the problem. However, such solutions don't guarantee correctness for all inputs, and they don't fully solve the problem in the theoretical sense.

# popcorn hack 3

The correct answer is:

D. Bubble sorting

Bubble sorting is a well-defined, decidable problem where an algorithm can always determine whether a list is sorted or not. It's a simple sorting algorithm with a clear procedure that terminates in a finite amount of time.

The other options (A, B, C) are undecidable problems:

A. Halting Problem: It's undecidable to determine whether an arbitrary program will halt or run indefinitely.

B. The Collatz Conjecture: It's an unsolved problem in mathematics, and there's no known algorithm that can decisively prove it for all integers.

C. Rice’s Theorem: This is a generalization that shows that most non-trivial properties of programs are undecidable.

# Homework

Modern operating systems and web browsers use various mechanisms to handle infinite loops and long-running scripts. Operating systems like Linux limit resources with tools like ulimit, and Windows can terminate unresponsive processes. Browsers like Chrome and Firefox display error messages when scripts run too long, such as "Script took too long to run." They also use event-driven models and asynchronous execution to remain responsive. These systems work together to maintain stability and prevent system freezes.
