## skimage quick guide 

```python
from skimage import data
from skimage import io

lena = data.lena()
io.imshow(lena)

# Playing with colors
from skimage import color

lena_gray = color.rgb2gray(lena)
io.imshow(lena_gray)

# Gradients
mport numpy as np
from skimage.filter.rank import gradient
# Note: across the dimention of the gradient the size of the gradient image is the size of original - 1

grad_y = np.diff(lena_gray, axis=0)
grad_x = np.diff(lena_gray, axis=1)
io.imshow(grad_x)

# Filters
from skimage import filter
filtered = filter.gaussian_filter(lena, sigma=3) #sigma=[1, 10]
io.imshow(filtered)

# Sobel edge detection
edges = filter.sobel(text)
io.imshow(edges)

# Canny edge detection
edges = filter.canny(lena_gray) # filter.canny(lena_gray, sigma=1, low_threshold=0.2, high_threshold=0.5)
io.imshow(edges) 

# Features
from skimage.feature import corner_harris, peak_local_max, corner_peaks

# Harris corner detector - corner measure based on the autocorrelation matrix
image = color.rgb2gray(data.text())
corners = corner_harris(image)
io.imshow(corners)
#  Pick the actual corners: here we simply find the miximum peaks.
coords = peak_local_max(h)
io.imshow(image)
plt.plot(coords[:, 1], coords[:, 0], '+r', markersize=10)
plt.show()
# Set blur intensity and distance between the peaks.
coords = peak_local_max(corner_harris(image, sigma=5), min_distance=10)
io.imshow(image)
plt.plot(coords[:, 1], coords[:, 0], '+r', markersize=10)
plt.show()
# A fancier corner selection technique: suppresses multiple connected peaks with corner_peaks.

# Template matching
from skimage.feature import match_template
match = match_template(image, coin)
io.imshow(match)
ij = np.unravel_index(np.argmax(match), match.shape)
x, y = ij[::-1]
# highlight matched region
hcoin, wcoin = coin.shape
rect = plt.Rectangle((x, y), wcoin, hcoin, edgecolor='r', facecolor='none')
```

