---
tags:
  - "#Statistics"
  - Counting
Date: 2025-10-28
Relevant:
---
![[Pasted image 20251028221838.png]]

A man has 3 blue shirts and 2 white shirts, how many choices can he make?

# What is counting?

![[Pasted image 20251028222056.png]]

![[Pasted image 20251028222343.png]]

---
## 1. Counting with Steps.

**Definition**: Step Rule of Counting (aka Product Rule).

If an experiment has 2 steps, where:
- The first step's outcomes are from set A, $|A| = m$ and the second step's outcomes are from set $B, |B| = n$.
- $|B|$ is unaffected by the outcomes of first step. The first choice doesn't affect how many other choices remaining in our second choice.
Then the number of outcomes of this experiment is: $|A||B| =mn$

**Notation:**
- $|X|$ represents size of a specific set - all the outcomes of step $X$.


>[!question]
>What does `$|B|$ is unaffected by the outcomes of first step.` mean?

It mean that no matter what happens in Step 1, the number of possible choices in Step 2 remains the same.

E.g., You're choosing an outfit.  
1. Step 1: Choose a T-shirt - 3 choices.  
2. Step 2: Choose trousers - 2 choices.  
No matter which T-shirt you choose in the first step, the number of possible choices in Step 2 is still 2.

>[!question]
>How many unique images?

![[Pasted image 20251028224320.png]]

Each pixel can be one of 17 million distinct colors.

There are 256 options for RED, 256 options for GREEN, 256 options for BLUE.
The process of choosing color is choosing red -> green -> blue = 256 x 256 x 256 = ~17 million.

So for answering this question, 12 pixels.
In pixel 1, to determine the color, we have 17 million distinct colors, we also have the same 17 million distinct colors to choose in pixel 2, and so on.
So there are $17.000.000^{12}$ pictures we can generate from 12 pixels.

>Philosophy: We live in a world where there might be finite things but there's infinite combinations of those things.

## 2. Counting with 'OR'.

**Definition:** The Sum Rule of Counting.
The outcomes can either come from set A or from set B.
If there are no element that in both, mutually exclusive then there are $|A\ or \ B|= |A| + |B|$.
If $A \cap B$ may not be empty, then the number of outcomes of this experiment is:
$$
N = |A| + |B| - |A \cap B|
$$
## 3. Difference between Counting with “OR” and Counting with Steps (Product Rule)

- Counting with “OR” (Sum Rule)  
    → The number of unique outcomes can come from A _or_ B.  
- Counting with Steps (Product Rule)   
    → The number of unique outcomes must come from Step A _then_ Step B.    
## 3. Practicing.

[[1. Counting problem.]]