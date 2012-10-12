# Ordered Samples

Consider the set or "propulation" of n elements a1, a2, ..., an. Any ordered arrangement a(j1), a(j2), ..., a(jr) of r symbols is called an **ordered sample** of size r drawn from our population.

## Notation

    (n)_r = n(n - 1)...(n - r + 1)

## Theorem

For a population of n elements and a prescribed sample size r, there exist n^r different samples with replacement and (n)\_r samples without replacement.

## Notice

Drawing in succession r elements from a population of size n is an experiment whose possible outcomes are samples of size r. Their number is n^r or (n)\_r, depending on whether or not replacement is used. In either case, our conceptual experiment is described by a sample space in which each individual point represents a sample of size r.

**Whenever we speak of random samples of fixed size r, the adjective random is to imply that all possible samples have the same probability, namely, 1 / n^r in sampling with replacement and 1 / (n)\_r in sampling without replacement.** If n is large and r relatively small, the ratio (n)\_r / n^r is near unity. This leads us to expect that, for large populations and relatively small samples, the two ways of sampling are practically equivalent.
