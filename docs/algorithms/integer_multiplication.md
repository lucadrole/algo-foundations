# Integer Multiplication

## Problem Statement

**Input:** Two $n$-digit nonnegative integers, $x$ and $y$.

**Output:** The product $x \times y$.

## Grade-school approach
Let's frame some primitive operations:

- adding two single-digit numbers
- multiplying two single-digit numbers
- adding a 0 at the beginning or end of a number

Complexity analysis: computing a partial product requires $n$ multiplications and $n$ addition (at most). At most $2n$ primitives. With $n$ partial products we need $2n^2$ primitives. To add them up we need a comparable number.

**Total operations:** 

$$T \leq 4n^2$$

>"Perhaps the most important principle for the good algorithm designer is to refuse to be content.” - Ao, Hopcroft, Ullman

## Doing better: Karatsuba Multiplication

Given two 4-digit numbers, split them by digits (e.g., 5678 becomes $a=56$ and $b=78$).

1. $a \cdot c$
2. $b \cdot d$
3. $(a+b) \cdot (c+d)$
4. Step 3 - Step 1 - Step 2
5. $10^4 \cdot \text{Step 1} + 10^2 \cdot \text{Step 4} + \text{Step 2}$

Why does this work? We will see later.

## Recursive Algortihm


References:

- Tim Roughgarden, [*Algorithms Illuminated: Part 1 – The Basics* (2017)](http://103.203.175.90:81/fdScript/RootOfEBooks/E%20Book%20collection%20-%202024%20-%20B/CSE%20%20IT%20AIDS%20ML/Algorithms%20Illuminated%20Part%201%20The%20Basics%20-%20Roughgarden.pdf).  See especially Chapter 1.  
