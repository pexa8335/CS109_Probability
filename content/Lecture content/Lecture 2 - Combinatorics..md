---
tags:
  - "#Combinatorics"
  - Statistics
Date: 2025-11-01
Relevant:
  - "[[Lecture 1 - Counting.]]"
  - "[[1. Counting problem.]]"
---
# Problem statement.

>[!question]
>How many unique orderings of characters are possible for the string `CHRIS`?


![[Pasted image 20251101171108.png]]

![[Pasted image 20251101171136.png]]

Because we can be able to break this problem into steps, and it has the property that the choice of one step doesn't affect how many outcomes remain in the future step. We use the **Counting with Steps rule.** [[Lecture 1 - Counting.]]

$$
5 \times 4 \times 3 \times 2 \times 1 = 5!
$$

This problem comes up so much that it has a special name - Permutations.

## 1. Permutations of Distinct Objects.

**Definition:** Permutation rule.

A permutation rule is an ordered arrangement of _n_ distinct objects.  

The number of unique orderings of _n_ distinct objects is:
$$
n! = n\times(n-1)\times(n-2)\times\dots \times 2 \times 1.
$$

## 1.1 Problem 1.

**Subproblem 1.**

![[Pasted image 20251101173948.png]]


Step 1: Choosing 1 out of 6 numbers - 6 choices.  
Step 2: Choosing 1 out of 5 numbers - 5 choices (Discard the chosen number in Step 1).  
And so on until step 6.  
$$
\prod_{i=1}^{6}i = 6! 
$$
Total = 6! = 720 passcodes.

**Subproblem 2.**

How many unique passcodes are possible if a phone password is some ordered subset of any 6 digits? 

Total = 10 x 9 x 8 x 7 x 6 x 5 = $\frac{10!}{4!}$ = 151200 passcodes.

## 1.2 Problem 2.

![[Pasted image 20251101174744.png]]

**Subproblem 1:** How many distinct bit strings can be formed from three 0’s and two 1’s?

**Assumption:** The 0’s and 1’s are distinguishable.

Total: 5! = 120.

But they're not distinct. We've overcounted.

For every single outcome, 11000, the number of ways to switch out between 1 is 2!.  
And the same with 0, the number of ways to switch out between 0 is 3!

So the solution is to divide the total outcome by $2! \times 3!$, we have: $\frac{5!}{2! \times 3!} = 10$

>The 000, in case we're observing it as distinct numbers, there would be 3 x 2 x 1 = 3! numbers, but it turns out the same so we have to divide by 3!.

By inference, we have the formula below.

## 2. Permutations of Indistinct Objects.

Definition: Permutations of Indistinct Objects.

Generally when there are _n_ objects and:  
$n_{1}$ objects are indistinct,  
$n_{2}$ objects are indistinct,  
...  
$n_{r}$ objects are indistinct.  

We have the permutations of indistinct objects formula:

$$
\frac{n!}{n_{1} \times n_{2} \times \dots \times n_{r}}
$$
