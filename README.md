# Analyzing Data with Principal Components Analysis
### Huy Huynh

## Abstract
A simple exploration of corerlation and principal components analysis (pca) to find similar features in data. PCA can be used to find feature space that described the most important relationship in the data.

## Introduction
One way to analyze the similarity between the different data points is to compute a corelation matrix. There are different ways to compute correlation, one simple way is to compute the dot product between the data points. PCA is another way to analyze the data and extract the most important components as well as reduce the dimensionality of the data. The yalefaces data set is used to explore correlation and PCA.

## Background
Correlation matrix using dot product, where each element given by:
<p align="center">
  $c_{jk} = x^{T}_{j}x_{k}$
</p>

One way to compute PCA is to find the eigenvector, eigenvalue pairs of the following matrix:
<p align="center">
  $Y = XX^{T}$
</p>

Another way to compute PCA is to use singular value decomposition (SVD):
<p align="center">
 $X = U \Sigma V^{T}$
</p>

The SVD modes are given by:
<p align="center">
 $XV = U \Sigma$
</p>

## Implementation
The numpy package is used to compute both the eigenvector, eigenvalue pairs of a matrix and SVD using np.linalg.eigh and np.linalg.svd respectively.

## Results
From the 100x100 correlation matrix there are cluster blocks of highly correlated images, which probably are group of images of the same person but in varying lighting conditions. The 100x100 computed using the first 100 images from the data set is shown in the figure below:
<p align="center">
  <img src="https://github.com/hhuynh000/EE399_HW2/blob/main/resources/corr100x100.png"/>
</p>
<p align="center">
  Figure 1. 100x100 Correlation Matrix
</p>

From the correlation matrix the two least correlated image pair is shown in the figure below:
<p align="center">
  <img src="https://github.com/hhuynh000/EE399_HW2/blob/main/resources/least_corr.png"/>
</p>
<p align="center">
  Figure 2. Least Correlated Images
</p>

From the correlation matrix the two most correlated image pair is shown in the figure below:
<p align="center">
  <img src="https://github.com/hhuynh000/EE399_HW2/blob/main/resources/most_corr.png"/>
</p>
<p align="center">
  Figure 3. Most Correlated Images
</p>

For the images 1, 313, 512, 5, 2400, 113, 1024, 87, 314, and 2005, the 10x10 correlated matrix shows that the images 87 and 314 are the most highly correlated with one another. The 10x10 correlated matrix is shown in the figure below:
<p align="center">
  <img src="https://github.com/hhuynh000/EE399_HW2/blob/main/resources/corr10x10.png"/>
</p>
<p align="center">
  Figure 4. 10x10 Correlation Matrix
</p>

Comparing the first eigenvector v1 with the first SVD mode u1, the norm of difference of their absolute values is 482.76. When reshaping the vectors into a 32x32 image, the two vectors is visually similar. In this case with yalefaces data set, the resulting PCA are the same for both SVD and egienvectors approach. The two images is shown in the figure below:
<p align="center">
  <img src="https://github.com/hhuynh000/EE399_HW2/blob/main/resources/svd_eigen.png"/>
</p>
<p align="center">
  Figure 5. Eigenvector and SVD Mode Comparison
</p>

The percentage of variance captured by each of the first 6 SVD modes are 0.1661, 0.0761, 0.0312, 0.0267, 0.0156, 0.015 in order. SVD captures the important facial features like eyes and nose as seen in mode 1. Also, SVD captures lighting condition like being half lit as seen in mode 2. The first 6 SVD modes captures a lot of the variance of the data set with a percentage of about $1/3$. The images of the first 6 SVD modes are shown in the figure below:
<p align="center">
  <img src="https://github.com/hhuynh000/EE399_HW2/blob/main/resources/svd_modes.png"/>
</p>
<p align="center">
  Figure 6. First 6 SVD Modes
</p>

## Conclusion
There are different tools like PCA and correlation matrix to analyze data. Measuring correlation with dot product is an easy way to find how similar data is to one another. In addition, PCA is especially useful in generating feature space for training machine learning model on since it extract the most important component and reducing the dimensionality.
