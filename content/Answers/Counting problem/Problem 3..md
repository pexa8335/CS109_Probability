---
tags:
  - Counting
  - Statistics
Date: 2025-10-31
Relevant:
  - "[[Lecture 1 - Counting.]]"
  - "[[1. Counting problem.]]"
---
# Solution.

## Subproblem 1.

Step 1 - Position 1 - 9 choices.
Step 2 - Position 2 - 9 choices.
Step 3 and so on - 9 choices.
$\implies$ The number of natural numbers with 9 digits is $9^9$

## Subproblem 2.

Step 1 - Position 1 - 9 choices.
Step 2 - Position 2 - 8 choices (Discard the chosen digit in step 1).
Step 3 - Position 3 - 7 choices (Discard the chosen digit in step 1 and step 2).
And so on until step 9.
$$
\prod _{i=1}^9i
$$
$\implies$ The number of natural numbers with 9 different digits is $9!$

## Subproblem 3.

Step 1 - Position 1 - 9 choices.
Step 2 - Position 2 - 8 choices (Discard the chosen digit in step 1).
Step 3 - Position 3 - 7 choices (Discard the chosen digit in step 1 and step 2).
And so on until step 5.

$$
\prod _{i=5}^9i
$$
$\implies$ The number of natural numbers with 9 different digits is $9 \times 8 \times 7 \times 6 \times 5 = \frac{9!}{4!}$

## Subproblem 4.

An even number must have the last digit divisible by 2 $\implies$ Last digit {$2, 4, 6, 8$} - 4 choices.
Step 1: Choosing the last digit - 4 choices.
Step 2: Choosing the first digit - 8 choices (Discard the chosen digit in step 1).
Step 3: Choosing the second digit - 7 choices (Discard the chosen digit in step 1 and step 2).
And so on until step 5.
$$
\prod_{i=4}^8i
$$$\implies$ The number of different even natural numbers have 9 digits is $8 \times 7 \times 6 \times 5 \times 4 = \frac{8!}{3!}$
