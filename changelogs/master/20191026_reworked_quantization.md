# Reworked Quantization

* Renamed `imgaug.augmenters.color.quantize_colors_uniform(image, n_colors)`
  to `imgaug.augmenters.color.quantize_uniform(arr, nb_bins)`. The old name
  is now deprecated.
* Renamed `imgaug.augmenters.color.quantize_colors_kmeans(image, n_colors)`
  to `imgaug.augmenters.color.quantize_kmeans(arr, nb_clusters)`. The old name
  is now deprecated.
* Improved performance of `quantize_uniform()` by roughly 10x (small images
  around 64x64) to 100x (large images around 1024x1024).
* Added argument `to_bin_centers=True` to `quantize_uniform()`, controling
  whether each bin `(a, b)` should be quantized to `a + (b-a)/2` or `a`.