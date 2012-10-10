# Morphology

Before operate morphology operations on an image, first converting the grayscale document into a binary image for further processing. A useful function is defined as follows:

    theta(f, t) = if f >= t then 1 else 0

Morphology operations is one of the most comon **binary** operations. To perform such and operation, we first convolve the binary image with a binary structuring element and then select a binary output value depending on the thresholded result of the convolution. (this is not the usual way in which these operations are described, but the author find it a nice simple way to unify the process.)

## Morphology Operations

+ **dilation:** dilate(f, s) = theta(c, 1)
+ **erosion:** erode(f, s) = theta(c, S)
+ **marjority:** maj(f, s) = theta(c, S/2)
+ **opening:** open(f, s) = dilate(erode(f, s), s)
+ **close:** close(f, s) = erode(dilate(f, s), s)
