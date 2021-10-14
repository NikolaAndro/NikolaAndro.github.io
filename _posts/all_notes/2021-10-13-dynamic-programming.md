---
layout: post
title:  "Dynamic Programming"
date:   2021-10-13 09:29:20 +0700
categories: post
---

# Note In Progress

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
**Dynamic programming** solves problems by combining the solutions to subproblems. It can be similar to divide-and-conquer method, where problem is partitioned into disjoint subproblems, subproblems are recursively solved and then combined to find the solution of the original problem. However, dynamic programming applies when the subproblems overlap - that is, when subproblems share subsubproblems. In this context, a divide-and-conquer algorithm does more
work than necessary, repeatedly solving the common subsubproblems. A dynamic-programming algorithm solves each subsubproblem just once and then saves its answer in a table, thereby `avoiding the work of recomputing the answer` every time it solves each subsubproblems.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
Dynamic Programming is used to solve optimization problems. These type of problems can have many possible optimal solutions. Hence, the goal of dynamic programming is to find one optimal solution. 


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
In order to know `when to look for a dynamic-programming solution` to a problem, we need to recognize if our problem has **optimal substructure** and **overlapping subproblems**. 

# Optimal Substructure

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
A problem demonstrates an `optimal substructure` if an optimal solution to the problem, within itself, contains optimal solutions to subproblems. Hence, when we recognize such a structure, we can be sure that we can apply dynamic programming.

When discovering optimal solution of a problem, we will follow the pattern:
  - Show that a solution to the problem consists of making a decision/choice, such as cutting a rod, that leaves one or more subproblems to be solved using the same method.
  - Suppose that for this problem, we were given the first decision that leads to an optimal solution.
  - Given this choice, we need to determine which subproblems arise.
  - Show that solutions to the subproblems used to solve the original problem are also optimal by using a `cut and paste technique`. In this technique, we assume that some piece of the optimal solution S* is not an optimal solution to a smaller subproblem. Then we need to show that replacing that piece with the optimal
solution to the smaller subproblem improves the supposedly optimal solution S*. Therefore, that S* must include an optimal solution to a smaller subproblem.

In other words:

Let's say you are asked to minimize the function g(x) . You know that the value of g(x) depends on g(y) and g(z) . Now if we can minimize g(x) by minimizing both g(y) and g(z) , only then we can say that the problem has optimal substructure. If g(x) is minimized by only minimizing g(y) and if minimizing or maximizing g(z) doesn't have any effect on g(x) , then this problem doesn't have optimal substructure. In simple words, if optimal solution of a problem can be found from the optimal solution of its subproblem, then we can say the problem has optimal substructure property.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
Dynamic Programming very frequently uses optimal substructure in a `bottom-up approach`. This means that we first determine optimal solutions to subproblems and then using those optimal solutions, we find the optimal solution of the "upper level" problem. 

# Overlapping Subproblems

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
When a recursive algorithm revisits the same problem repeatedly, we can say that the optimization problem has `overlapping subproblems`. Dynamic-programming algorithms take advantage of overlapping subproblems by solving each problem once and then storing the solution in a table, which is being visited every time the same problem is being encountered in order to reduce redundancy of computations.

# Memoization

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
Memoizing a recursive algorithm means maintaining solution to each problem in a table. Initially, each table entry contains a `special value` to indicate that the entry has yet to be filled in. When the subproblem is encountered for the first time, as recursive algorithm unfolds, its solution is computed and stored in the table. Each next time we visit this subproblem, we simply look up the solution of the problem in the table and return it without having to do computations for that subproblem again.  

Some of the problems that can be solved using the dynamic programming:
  - Rod Cutting
  - Matrix-Chain Multiplication
  - Longest Common Subsequence
  - Coin Changing Problem
  - Knapsack Problem
  - Graph Problems


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
Nikola Andric
