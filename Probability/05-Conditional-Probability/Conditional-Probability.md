# Conditional Probability

## Definition

Let H be an event with positive probability. For an arbitrary event A we shall write

    P{A|H} = P{AH} / P{H}

The quantity so defined will be called the conditional probability of A on the hypothesis H (or for given H).

## A Simple Formula

Let H1, ... , Hn be a set of mutually exclusive events of which one necessarily occurs (that is, the union of H1, ... , Hn is the entire sample space). Then any event A can occur only in conjunction with some Hj, or in symbols,

    A = AH1∪ AH2∪ ...∪ AHn.

Since the AHj are mutually exclusive, their probabilities add. Applying `P{AH} = P{A|H}P{H}` and adding, we get

    P{A} = sum(P{A|Hi}P{Hi})
