# Steerable Filter

One approach to finding the response of a filter at many orientations is to apply many versions of the same filter, each different from the others by some small rotation in angle. A more efficient approach is to apply a few filters corresponding to a few angles and interpolate between the responses. **With the correct filter set and the correct interpolation rule, it is possible to determine the response of a filter of arbitrary orientation without explicitly applying that filter.**

We use the term 'steerable filter' to describe a class of filters in which a filter of arbitrary orientation is synthesized as a linear combination of a set of 'basis filters'.
