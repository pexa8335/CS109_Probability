---
tags:
  - Counting
  - Statistics
Date: 2025-11-01
Relevant:
  - "[[Lecture 1 - Counting.]]"
  - "[[1. Counting problem.]]"
---
# Solution.

## Subproblem 1.

**Case number 1:** Last digit is 0 - 1 choice.
Step 2: Choosing the first digit - 6 choices (Discard 0).
Step 3: Choosing the second digit - 5 choices (Discard the chosen digit in step 1 and 0).
Step 4: Choosing the third digit - 4 choices (Discard the chosen digit in step 1, step 2 and 0).
And so on until step 5.

$$
\prod_{i=2}^6 i
$$
$\implies$ The number of different even natural numbers have 5 digits in case number 1 is $6 \times 5 \times 4 \times 3 \times 1 = \frac{6!}{2} = 360$.

**Case number 2:** Last digit is {2, 4, 6} - 3 choices.
Step 2: Choosing the first digit - 5 choices (Discard the chosen number in last digit and 0).
Step 3: Choosing the second digit - 5 choices (Discard the chosen number in step 1 and in last digit, 0 acceptable).
And so on until step 5.
$$
3\times 5\times \prod_{i=3}^5
$$
$\implies$ The number of different even natural numbers have 5 digits in case number 2 is $5 \times 5 \times 4 \times 3 \times 3 = 900$.

Total: 900 + 360 = 1260.

## Subproblem 2.

The digits $\{1, 2, 3\}$ must appear together in some order, forming a block $B$. The digits in the block $B$ can be arranged in $3 \times 2 \times 1 = 6$ choices.

The required numbers have 5 digits, {1, 2, 3} are 3 digits, so we have only 2 digits left.

We have only 3 positions for 5 number {$0; 4; 5; 6;$ block B}.

**Case number 1:** Block starts at the first position - 6 choices.
Step 2: Choosing last digit - 3 choices (Even number 0, 4, 6).
Step 3: Choosing second digit - 3 choices (Discard the block and last digit).

$\implies$ The number of different even natural numbers have 5 digits and are adjacent in case number 1 is $3 \times 6 \times 6 = 54$.

**Case number 2:** Block starts the second position - 6 choices.

**Subcase 2.1:** Last digit is 0 - 1 choice.
Step 3: Choosing first digit - 3 choices (Discard last digit and block).

Number of possibilities = 3 x 6 = 18.

**Subcase 2.2:** Last digit is {4, 6} - 2 choices.
Step 3: Choosing first digit - 2 choice (Discard 0, last digit and block).

Number of possibilities = 6 x 2 x 2 = 24.

$\implies$ The number of different even natural numbers have 5 digits and are adjacent in case number 2 is $24 + 18 = 42$.

**Case number 3:** Block starts at the last position - the `2` must be at the last digit - 2 choices.
Step 2: Choosing first digit - 3 choices (Discard 0 and block).
Step 3: Choosing second digit - 3 choices (Discard first digit and block).

$\implies$ The number of different even natural numbers have 5 digits and are adjacent in case number 3 is $3 \times 3 \times 2 = 18$.

Total: 54 + 42 + 18 = 114 choices.


