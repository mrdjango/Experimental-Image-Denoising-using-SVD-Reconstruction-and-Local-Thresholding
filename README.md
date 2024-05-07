# Experimental-Image-Denoising-using-SVD-Reconstruction-and-Local-Thresholding
This combined approach attempts to remove noise by selectively filtering the information captured by SVD and then refining the reconstruction with local comparisons. The effectiveness depends on the noise type, choice of ```n```, and thresholding parameters.


## Description:

This Python code addresses image denoising using a combination of techniques:

1. **Block-wise Noise Addition:** It introduces controlled noise into the image by adding random values to localized blocks of pixels. This simulates a specific type of noise where corrupted areas appear in larger patches.

2. **Singular Value Decomposition (SVD):** It performs SVD on the noisy grayscale image. SVD decomposes the image into its constituent parts, and the singular values represent the image's energy distribution. By keeping only a subset of the singular values, the code aims to remove noise while preserving the underlying image information.

3. **Thresholding for Denoising:** After reconstructing an image using a subset of singular values, a thresholding step is applied. Here, each pixel's value is compared to the average or median of its local neighborhood. If the difference exceeds a threshold, it's considered noise and adjusted towards the local average/median, effectively removing outliers caused by noise.

4. **Experimentation with Reconstruction Parameters:** The code explores multiple values for `n` (number of singular values used for reconstruction) to find a balance between noise removal and detail preservation. Visualizing the singular values can further guide this exploration.
