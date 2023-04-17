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
The 100x1000 correlation matrix computed using the first 100 images from the data set is shown in the figure below.
<p align="center">
  <img src="https://github.com/hhuynh000/EE399_HW1/blob/main/resources/pcolor.png"/>
</p>
<p align="center">
  Figure 3. Parameters Sweep Error Plot
</p>
