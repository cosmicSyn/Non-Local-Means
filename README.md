## Image Denoising
NLM is a method for image denoising. This method is based on a simple principle: replacing the color of a pixel with an average of the colors of similar pixels. But the most similar pixels to a given pixel have no reason to be close at all. It is therefore licit to scan a vast portion of the image in search of all the pixels that really resemble the pixel one wants to denoise.

### Implementation Notes

- All images were scaled up by a factor of 2 before performing computations for showing the difference between NLM and Gaussian Filter.
- The results depend on the amount of noise in the image. In some cases where the noise is very high, it is not possible to improve image quality beyond a certain limit as there is not sufficient information to find the missing pixels accurately.
- When taking the weighted pixels, the weights were divided by h instead of h x h. This is done from an experimentation point of view as this gives slightly more control over the tunable parameter as the exponential function decays slower for the same increase in h. The functioning of the algorithm will however remain the same since the order of h will simply change to obtain the same level of filtering.
- The tunable parameters of the NLM filter are the values of the window sizes, and the value of h. To obtain the previous results, fixed values were used for all images.
- An additional image apart from the one given in the dataset was added. This image is the classic `Lena` image used widely in image processing!

### References
[1] A. Buades, B. Coll and J. -. Morel, "A non-local algorithm for image denoising," 2005 IEEE Computer Society Conference on Computer Vision and Pattern Recognition (CVPR'05), San Diego, CA, USA, 2005, pp. 60-65 vol. 2, doi: 10.1109/CVPR.2005.38

[2]  Palou, G. (2015, July 07). An approach to Non-Local-Means denoising. Retrieved November 16, 2020, from http://dsvision.github.io/an-approach-to-non-local-means-denoising.html
