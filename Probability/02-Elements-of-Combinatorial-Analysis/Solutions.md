# Solutions for Chapter [ Elements of Combinatorial Analysis ]

## Problem 1.

(a) 26^3
(b) 26^3 + 26^2
(c) 26^4 + 26^3 + 26^2

## Problem 2.

According to the problem, the length of the Morse code for each letter can be from 1 to 10. Let Mi denote the Morse code of length i. In this case, for each position in Mi, there are two options, namely dash or dot. So the total number of letters form with ten or less symbols can be expressed as below:

    2^1 + 2^2 + 2^3 + ... + 2^10 = 2^11 - 2

## Problem 3.

If the piece of domino is marked by two different numbers, then the possiblities are

    Pd = / n \ = n(n - 1) / 2
         \ 2 /

If the piece of domino is marked by two same numbers, then the possiblities are

    Ps = n

Hence, the total number of different domino pieces is Pd + Ps = n(n + 1) / 2.

## Problem 4.

Since the numbers 1, 2, ... , n are arranged in random number, then the total number of possible permutation is n!.

(a) 1 and 2 appear as neighbours in the order named means we can regard 1 and 2 as a group, so the problem degenerates to calculating the permutation of n - 1 numbers. So the possibility is

    P12 = (n - 1)! / n! = 1 / n

(b) Quite similar to the above, the only different is to regard 1, 2, 3 as a group. Hence the possibility is

    P123 = (n - 2)! / n! = 1 / [n(n - 1)]

## Problem 5.

The possibility of A lost is that

    P(a) = (5/6)^6 = 0.3349

The possibility of B lost is that

    P(b) = (5/6)^12 + 12(1/6)(5/6)^11 = 0.3813

Since P(a) &lt; P(b), so A is more likely to win.
