# Linear Filtering

Linear filtering operators involve weighted combinations of pixels in small neighborhoods. 

### Correlation Operator

    g(i, j) = sum(k, l)[f(i + k, j + l)h(k, l)]

### Convolution Operator

    g(i, j) = sum(k, l)[f(k, l)h(i - k, j - l)]

### Padding Modes

+ **zero:** set all pixels outside the source image to 0 (a good choice for alpha-matted cutout images).
+ **constant(border color):** set all pixels outside the source image to a specified border value.
+ **clamp(replicate or clamp to edge):** repeat edge pixels indefinitely.
+ **cyclic wrap (repeat or tile):** loop "around" the image in a "toroidal" configuration.
+ **mirror:** reflect pixels across the image edge.
+ **extend:** extend the signal by subtracting the mirrored version fo the signal rom the edge pixel value.

**An alternative to padding is to blur the zero-padded RGBA image and to then divide the resulting image by its alpha value to remove the darkening effect. The result can be quite good.**

### Separable Filtering

The process of performing a convolution requires K^2 operations per pixel, where K is the size (width or height) of the convolution kernel. In many cases, **this operation can be significantly sped up by first performing a one-dimensional horizontal convolution followed by a one-dimensional vertical convolution (which requires a total of 2K operations per pixel).** A convolution kernel for which this is possible is said to be **separable.**

The way to tell whether the given kernel K is separable or not can be done through SVD. That is, treat the 2D kernel as a 2D matrix K and to take its singular value decomposition(SVD).
