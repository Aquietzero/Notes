# Urn Model

An urn contains b black and r red balls. A ball is drawn at random. It is replaced and, moreover, c balls of the color drawn and d balls of the opposite color are added. A new random drawing is made from the urn (now containing r + b + c + d balls), and this procedure is repeated. Here c and d are arbitrary integers. They may be chosen negative, except that in this case the procedure may terminate after finitely many drawings for lack of balls. **In particular, choosing c = -1 and d = 0 we have the model of random drawing without replacement which terminates after r + b steps.**

## Polya's Urn Scheme

Polya's urn scheme which is characterized by d = 0, c &gt; 0. Here after each drawing the number of balls of the color drawn increase, whereas the balls of opposite color remain unchanged in number. In effect the drawing of either color increases the probability of the same color at the next drawing, and we have a rough model of phenomena such as contagious diseases, where each occurrence increases the probability of further occurrences.

## Attention

In the statistical literature it has become customary to use the word contagion instead of aftereffect. The apparent aftereffect of sampling was the first misinterpreted as an effect of true contagion, and so statisticians now speak of contagion (or contagious probability distributions) in a vague and misleading manner. Take, for example, the ecologist searching for insects in a field. If after an unsuccessful period he finds an insect, it is quite likely that he has finally reached the proximity of a liiter, and in this case he may reasonably expect increased success. In other words, in practice every success increases the probability for further success, but once more this is only a side effect of the increased amount of information provided by the sampling. no aftereffect is involved, and it is misleading when the statistician speaks of contagion.
