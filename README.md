# Lost-In-Hyperspace - Hack The Box Solution

This repository provides the solution to the "Lost In Hyperspace" challenge on Hack The Box. The task involves using Principal Component Analysis (PCA) to reduce the embeddings and find the flag corresponding to the given tokens.

## Problem Description

You are provided with two files:
1. An array of tokens.
2. An array of embeddings.

The goal is to use PCA to reduce the dimensionality of the embeddings and plot the result with the corresponding tokens, which will help in extracting the flag.

## Principal Component Analysis (PCA)

Principal Component Analysis (PCA) is a dimensionality reduction technique that transforms data into a set of orthogonal (uncorrelated) variables called principal components. PCA projects the data along the axes that capture the most variance.

### Steps in the PCA Process

1. **Mean Centering the Data**: The data is first centered by subtracting the mean of each feature to ensure that the data has zero mean.

2. **Standardization**: The data is then standardized by scaling each feature to have unit variance.

3. **Covariance Matrix**: We calculate the covariance matrix, which measures how features co-vary.

4. **Eigenvalue Decomposition**: The eigenvalues and eigenvectors of the covariance matrix are calculated. The eigenvalues indicate the variance along each eigenvector (principal component).

5. **Sorting Eigenvalues and Eigenvectors**: The eigenvalues are sorted in descending order, and the corresponding eigenvectors are reordered.

6. **Projection onto Principal Components**: Finally, the data is projected onto the principal components corresponding to the largest eigenvalues. This reduces the dimensionality of the data.

### Mathematical Formulation

The PCA process can be described mathematically as follows:

1. **Mean Centering:**
   \[
   Z = X - \mu
   \]
2. **Standardization:**
   \[
   Z_{scaled} = \frac{Z}{\sigma}
   \]
3. **Covariance Matrix:**
   \[
   \Sigma = \frac{1}{N} Z^T Z
   \]
4. **Eigenvalue Decomposition:**
   \[
   \Sigma v = \lambda v
   \]
5. **Sort Eigenvalues and Eigenvectors:**
   \[
   \lambda_{sorted} = \text{argsort}(\lambda)[::-1]
   \]
   \[
   v_{sorted} = v[:, \lambda_{sorted}]
   \]
6. **Projection onto Principal Components:**
   \[
   X_{projected} = Z_{scaled} \cdot v_{sorted}[:, :k]
   \]

Where:
- \( X \) is the data matrix,
- \( Z \) is the mean-centered data,
- \( \mu \) is the mean vector,
- \( \sigma \) is the standard deviation vector,
- \( \Sigma \) is the covariance matrix,
- \( v \) are the eigenvectors, and
- \( \lambda \) are the eigenvalues.

## Solution
We recommened you answer this yourself.<br>
![plot_output](https://github.com/user-attachments/assets/8ba9a402-fa85-4fd8-957e-238361e1ca5c)

