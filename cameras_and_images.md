![digital_image](assets/digital_image.png)

__Intensity__: We can think of a (grayscale) image as a function $f : R^2 \rightarrow  R$ giving the intensity at position $(i, j)$

Intensity 0 is black and 255 is white.

__Filtering__:  Modify the pixels in an image based on some function of a local neighborhood of each pixel.

__Applications of Filtering__:

- denoise: Enhance an image
- template matching: Detect pattern
- Texture and edge detection: Extract info

![correlation](assets/correlation.png)

![Correlation_howto](assets/Correlation_howto.png)

![boundry_effects](assets/boundry_effects.png)

__smoothing__: removing high_frequency components from the image (low-pass filter)

![gaussian_filter](assets/gaussian_filter.png)

**Properties of the Smoothing:** (such as Gaussian filter)

- All values are positive
- They all sum to 1
- Amount of smoothing is proportional to mask size
- remove high-frequency components; (low-pass filter)

Note: This holds for smoothing filters only, not general filters

**Template Matching:**

![cross_correlation](assets/cross_correlation.png)

And put a bounding box (rectangle the size of the template) at the point!

__Convolution__:

![Convolution](assets/Convolution.png)

![correlation_vs_convolution](assets/correlation_vs_convolution.png)

**Properties of convolution:**

- Commutative
- Associative
- Distributive
- Assoc. with scalar multiplier

Note: The Fourier transform of two convolved images is the product of their individual Fourier transforms: $\mathcal{F}(f*g) = \mathcal{F}(f) . \mathcal{F}(g)$.

Note: Convolving twice with Gaussian kernel of width $\sigma$ is the same as convolving once with kernel of width $\sigma\sqrt{2}$.

__Separable Filters__: (speed-up trick!)

![separable_filter_concept](assets/separable_filter_concept.png)

- If the convolution filter is separable, the convolution can be  speed up by first performing a 1D horizontal convolution followed by a 1D vertical convolution. (requiring only $2K$ operations instead of $K^2$)  $F = v \times h^T$.

![separable_filter](assets/separable_filter.png)
