
# Solution.

## Subproblem 1.

Step 1 - Position 1 - 9 cách chọn.
Step 2 - Position 2 - 9 cách chọn.
Step 3 and so on - 9 cách chọn.
$\implies$ The number of natural numbers has 9 digits is $9^9$

## Subproblem 2.

Step 1 - Position 1 - 9 cách chọn.
Step 2 - Position 2 - 8 cách chọn (Discard the chosen number in step 1).
Step 3 - Position 3 - 7 cách chọn (Discard the chosen number in step 1 and step 2).
And so on until step 9.
$$
\prod _{i=1}^9i
$$
$\implies$ The number of natural numbers has 9 different digits is $9!$

## Subproblem 3.

Step 1 - Position 1 - 9 cách chọn.
Step 2 - Position 2 - 8 cách chọn (Discard the chosen number in step 1).
Step 3 - Position 3 - 7 cách chọn (Discard the chosen number in step 1 and step 2).
And so on until step 5.

$$
\prod _{i=5}^9i
$$
$\implies$ The number of natural numbers has 9 different digits is $9 \times 8 \times 7 \times 6 \times 5 = \frac{9!}{4!}$

## Subproblem 4.

Even number must have the last digit is divisible to 2 $\implies$ Last digit {$2, 4, 6, 8$} - 4 cách chọn.
Step 1: Choosing last number - 4 cách chọn.
Step 2: Choosing the first number - 8 cách chọn (Discard the chosen number in step 1).
Step 3: Choosing the second number - 7 cách chọn (Discard the chosen number in step 1 and 2).
And so on until step 5.
$$
\prod_{i=4}^8i 
$$
