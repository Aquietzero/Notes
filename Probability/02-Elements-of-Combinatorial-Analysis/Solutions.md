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

## Problem 15

This is a basic supergeometric problem. The probability is

    P = C(10, 90) / C(10, 100)

## Problem 17

1. Choose r persons between A and B, C(r, n - 2)
2. Permutate them, C(r, n - 2)r!
3. Permutate the rest persons, (n - r - 2)!
4. Separate the rest persons into two groups, one on the left of A and the rest right of B, (n - r - 2)!(n - r - 1) = (n - r - 1)!
5. Switch A and B.

So the probability is

       2 C(r, n-2)r! (n-r-1)!   2 (n-2)_r (n-r-1)!   2 (n-r-1)
    P = --------------------- = ------------------ = ---------
                 n!                     n!             n(n-1)

For the second part of the problem, please refer to my blog.

## Problem 24

(a) The problem is similar to randomly place n different balls into n different boxes, so the probability is 12!/12^12.
(b) Firstly, the total permutation is 12^6. Then consider the problem as follows: (1) Choose 2 months from the 12 months of the year. Then we have C(2, 12) choices. (2) Each of the 6 person have two choices from these 2 months, which generates 2^6 permutations. But there are 2 special permutations in it, the first one is all 6 persons are both in the first month, the second one is that they both born in the second month. So the final probability is

    P = C(2, 12) (2^6 - 2) / 12^6

## Problem 26

Let's denote the shoes in the following way:

    a1, a2, a3, ... , an
    b1, b2, b3, ... , bn

(a) Since there are no pairs, so each selected shoe belongs to different pairs of shoes. Hence we can choose 2r shoes from the n pairs of shoes, which gives the permutation of C(2r, n). Then since each pair of shoes has two shoes, we can choose one of them to represent a pair of shoes, which gives the permutation of 2^2r. So the final probability is

       C(2r, n) 2^2r
    p = ------------
         C(2r, 2n)

(b) We can first choose the pair of shoes from those n pairs of shoes, then we choose 2r - 2 shoes from the left n - 1 pair of shoes. For the same reason, each pair of shoes has two shoes, which gives the final probability as follows:

       n C(2r-2, n-1) 2^2r
    p = -----------------
            C(2r, 2n)

(c) The method is quite similar to the above problem.

       C(2, n) C(2r-4, n-2) 2^2r
    p = -----------------------
              C(2r, 2n)

## Problem 27

After the car owner returns, there are r cars still there. So we have to decide which cars have left, which has C(r-1, n-1) permutations since the car owner's car is there for sure. Then, since the car takes three parking places, its own place and two empty places next to it. So the permutation of the rest r - 1 cars is C(r-1, n-3). Hence, the probability is

       C(r-1, n-3)
    p = ---------
       C(r-1, n-1)

## Problem 28

Select 2N children from the 4N children group to form group 1. Then in group 1, N boys are chosen from the 2N boys while N girls are chosen from the 2N grils. So the probability is

    P = C(N, 2N) C(N, 2n) / C(2N, 4N)

Using Stirling's formula to simplify the above formula, we have

    P = C(N, 2N) C(N, 2n) / C(2N, 4N)
            [(2N)!]^4
      = ---------------- = sqrt(2/Nπ)
         [(N!)]^4 (4N)!
