---
tags:
  - "#Combinatorics"
  - Statistics
Date: 2025-11-01
Relevant:
  - "[[Lecture 1 - Counting.]]"
  - "[[1. Counting problem.]]"
---
>[!tips]
These problems are lecture problems, the problems in List of problems are extra problems.

# Lecture summary.

![[Pasted image 20251108194115.png]]
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

### 1.1 Problem 1.

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

# Problem statement.

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

**Definition:** Permutations of Indistinct Objects.

Generally when there are _n_ objects and:  
$n_{1}$ objects are indistinct,  
$n_{2}$ objects are indistinct,  
...  
$n_{r}$ objects are indistinct.  

We have the permutations of indistinct objects formula:

$$
\frac{n!}{n_{1} \times n_{2} \times \dots \times n_{r}}
$$
### 2.1 Problem 1.

![[Pasted image 20251108170314.png]]

**Subproblem 1.** BOBA.

The total of letters are 4, so the number of possible orderings are $4!$.
The letter B is indistinct, so we have overcounter $2!$.

Applying the formula in **Permutations of Indistinct Objects** we have:
$$
\frac{4!}{2!} = 2! = 12
$$
![[Pasted image 20251108172218.png]]

**Subproblem 2.** MISSISSIPPI.

The total of letters are 11, so the number of possible orderings $11!$.
The letter I, S, P are indistinct, we have 4 letters S, 4 letters I, 2 letters P.

Applying the formula in **Permutations of Indistinct Objects** we have:
$$
\frac{11!}{4! \times 4! \times 2!} = 34,650
$$

![[Pasted image 20251108172400.png]]

### 2.2 Problem 2.

![[Pasted image 20251108172600.png]]

The number of possible orderings in this case is $6!$.
We have 1 indistinct digit, so we have overcounted $2!$ times.

Choose digit to repeat: $5$ outcomes.
The number of possible orderings for each outcome (discard overcounted orderings): $\frac{6!}{2!}$

So, with 5 outcomes, we have the total of possible orderings is: $5 \times \frac{6!}{2!}$.

# Problem statement.

![[Pasted image 20251108195545.png]]

![[Pasted image 20251108203534.png]]


We put the **first k** people in the cake room, so there’s only **1 way** to do that once the line is fixed.

In the **first k** people, it doesn't matter how many times we shuffle the **positions** of people, the way of choosing 5 people remains the same - they all get cake - **discard** $k!$.

But $n!$ - we have an outcome for every ordering of these 15 people, even though in this outcome, this exact set of 15 people doesn't get cake - **discard** $(n-k)!$.

So we have the calculation:
$$
\frac{n!}{1 \times k! \times (n-k)!}
$$
---
## 3. Combinatorics.

**Definition:** A combination is an unordered selection of k objects from a set of n distinct objects.

The number of ways of making this selection is

$$
\frac{n!}{k! \times (n-k)!} = \binom{n}{k}
$$
$\binom{n}{k}$ is binomial coefficient.

>[!important]
>All of our objects are assumed to be distinct.

We don't care about ordering, we just care about what was chosen.

>[!quote]
>Side note: Combination is very similar to ordering of indistinct items. See **Permutations of Indistinct Objects.**

People in the cake room, people not in the cake room, they're all "indistinct" in some ways, like choosing 5 people in the cake room, we **treat** them equally - any possible ordering **of** these 5 remains **as one**, we give the $1^{st}$ person cake first, and then give the $2^{nd}$ person cake, ... and so on, they all still get cake - so they're all indistinct.

### 3.1 Problem 1.

How many ways are there to choose 3 books from a set of 6 books?

$$
\binom{6}{3} = \frac{6!}{3!3!} = 20
$$
```python
import math

print(math.comb(3, 6))
```

Print all possible orderings:

```python
import itertools

cards = make_deck() # Create 52 cards
all_hands = itertools.combinations(cards, 5)

for hand in all_hands:
	print(hand)
```

# Problem statement.

How many ways to put indistinct objects into buckets?

Let's define the `|` as our divider, we have 4 indistinct balls, represented as `o`.
The problem comes up with 4 balls in 3 buckets.
If we put the divider `|` like that: `_____` `|` `_____` `|` `_____`, we have 3 buckets to put 4 balls **into**.

And any ordering of balls in the buckets leads to a unique assignment of balls **to** buckets.

For instance:
`_oooo` `|` `_____` `|` `_____`
`_____` `|` `_oooo` `|` `_____`
`__oo_` `|` `__oo_` `|` `_____`

How many orderings are there?

We have 4 balls, 2 dividers.

So we have $6!$ ways of ordering? We have 4 indistinct balls => This is ordering **of** indistinct items. **Permutations of Indistinct Objects.**

And still based on the above example, no matter how we change the position of divider, the unique assignment remains the same => We have 2 indistinct dividers.

Conclusion: The number of ways to put 4 indistinct objects into 3 distinct buckets.
$$
\frac{6!}{2!4!}
$$

## 4. The divider method.

The number of ways to distribute _n_ indistinct objects into _r_ distinct buckets is equivalent to the number of ways to permute _n + r - 1_ objects such that
	_n_ are indistinct objects, and
	_r - 1_ are indistinct dividers:

Inherit from **Permutations of Indistinct Objects.**

Total =
$$
\frac{(n + r - 1)!}{n!(r-1)!}
$$
# Problem statement.

How many ways to put _n_ distinct objects into _r_ distinct buckets?

Let's come up with:
	4 distinct objects: A, B, C, D
	3 distinct buckets: Red, Green, Blue
Each object **picks** a bucket.
Object A has 3 ways, **object** B has 3 ways,... and so on.

So the number of unique orderings **is** $3 \times 3 \times 3 \times 3 = r^n$

## 5. Put objects in _r_ buckets.

**Definition:** With _n_ distinct objects and _r_ distinct buckets, the total ways to put _n_ distinct objects into _r_ distinct buckets are:
$$
r^n
$$