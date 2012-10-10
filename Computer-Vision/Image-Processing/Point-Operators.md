# Point Operators

The simplest kinds of image processing transforms are point operators, where each output pixel's value depends on only the corresponding input pixel value (plus, potentially, some globally collected information or parameters).

## Pixel Transforms

A general image processing operator is a function that takes one or more input images and produces an output image. In the continuous domain, this can be denoted as:

    g(x) = h(f(x)) or g(x) = h(f0(x), f1(x), ... fn(x))

For discrete(sampled) images, the domain consists of a finite number of pixel locations, x = (i, j), and we can write:

    g(i, j) = h(f(i, j))

Two commonly used point processes are multiplication and addition with a constant,

    g(x) = af(x) + b

The parameters a &gt; 0 and b are often called the **gain** and **bias** parameters; sometimes these parameters are said to control **contrast** and **brightness**, respectively. Of course, the bias and gain parameters can also be spatially varying.

    g(x) = a(x)f(x) + b(x)

Another commonly used dyadic operator is the **linear blend** operator,

    g(x) = (1 - a)f0(x) + af1(x)

One highly used non-linear transform that is often applied to images before further processing is **gamma correction**, which is used to remove the non-linear mapping between input radiance and quantized pixel values.
