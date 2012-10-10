# Histogram

Since a histogram encodes no information about where each of its individual entries originated in the image, histograms contain no information about the spatial arrangement of pixels in the image. This is intentional since the main function of a histogram is to provide statistical information.

## Contrast

Contrast is understood as the range of intensity values effectively used within a given image, that is the difference between the image's maximum and minimum pixel values.

## Dynamic range

The dynamic range of an image is, in principle, understood as the number of distinct pixel values in an image. In the ideal case, the dynamic range encompasses all K usable pixel values, in which case the value range is completely utilized.

**While the contrast of an image can be increased by transforming its existing values so that they utilize more of the underlying value range available, the dynamic range of an image can only be increased by introducint artificial values using methods such as interpolation.**
