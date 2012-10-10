# Compositing and Matting

In many photo editing and visual effects applications, it is often desirable to cut a foreground object out of one scene and put it on top of a different background. The process of extracting the object from the original image is often called **matting**, while the process of inserting it into another image (without visible artifacts) is called **compositing**. The intermediate representation used for the foreground object between these two stages is called an **alpha-matted color image**.

The **over operator** is defined as below:

    C = (1 - a)B + aF

This operator attenuates the influence of the background image B by a factor (1 - a) and then adds in the color (and opacity) values corresponding to the foreground layer F.
