# Occupancy Problems

In the case of placing randomly r balls into n cells, in many situations it is necessary to treat the balls as indistinguishable. For example, in statistical studies of the distribution of accidents among weekdays, or of birthdays among calendar days, one is interested only in the number of occurrences, and not in the individuals involved. Again, throwing r dice is equivalent to a placement of r balls into n = 6 cells. Although it would be possible to keep track of the r individual results, one prefers usually to specify only the numbers of aces, twos, etc. In such situations we may still suppose the balls numbered, but we focus our attention on events that are independent of the numbering. Such an event is completely described by its **occupancy numbers** r1, r2, ..., rn, where rk stands for the number of balls in the kth cell. Every n-tuple of integers satisfying

    r1 + r2 + ... + rn = r

describes a possible configuration of occupancy numbers. **With indistinguishable balls two distributions are distinguishable only if the corresponing n-tuples (r1, ..., rn) are not identical.**

(i) The number of distinguishable distributions is

    A(r, n) = / n + r - 1 \ = / n + r - 1 \
              \     r     /   \   n - 1   /

(ii) The number of distinguishable distributions in which no cell remains empty is

    / r - 1 \
    \ n - 1 /

## Proof

We represent the balls by stars and indicate the n cells by the n spaces between n + 1 bars. Thus |\*\*\*|\*||||\*\*\*\*| is used as a symbol for a distribution of r = 8 balls in n = 6 cells with occupancy numbers 3, 1, 0, 0, 0, 4. Such a symbol necessarily starts and ends with a bar, but the remaining n - 1 bars and r stars can appear in an arbitrary order. In this way it becomes apparent that the number of distinguishable distributions equals the number of ways of selecting r places out of n + r - 1, namely A(r, n).

The condition that no cell be empty imposes the restriction that no two bars be adjacent. The r stars leave r - 1 spaces of which n - 1 are to be occupied by bars: thus we have (ii) choices and the assertion is proved.
