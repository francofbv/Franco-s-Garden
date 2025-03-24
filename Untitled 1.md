**Date:** 2025-03-22  
**Topics:** Principal Component Analysis (PCA), Dimensionality Reduction, Eigenvalue Decomposition, Singular Value Decomposition (SVD)  
**Tags:** PCA, SVD, Dimensionality Reduction, Covariance Matrix, Eigen Decomposition, Orthogonal Matrices  
**Speaker/Instructor:** [Insert Name Here]

---

# Lecture 5: Principal Component Analysis (PCA)

## Objective of PCA
- **Goal**: Reduce the dimensionality of data while retaining the most significant components that describe the dataset.
- **Outcome**: Represent the data in a lower-dimensional space effectively.

---

## Key Concepts

### 1. Finding Significant Components

#### Objective:
- Identify the most significant directions in the data.

#### Method:
1. **Matrix Representation**:
   - Represent the dataset as an **N-feature matrix M**.
   - Each row corresponds to an instance, and each column corresponds to a feature.

2. **Least Squares Method**:
   - Use the least squares method to find the most significant direction by identifying two distinct corners of the dataset.

3. **Covariance Matrix**:
   - Compute the covariance matrix **A**, which captures the correlation among data points.
   - Formula: $ A = \text{Cov}(M) $.

4. **Eigenvalue Decomposition**:
   - Perform eigen decomposition on the covariance matrix $ A $:
     $$
     A = Q \Lambda Q^T
     $$
     - $ Q $: Orthogonal matrix whose columns are the eigenvectors of $ A $.
     - $ \Lambda $: Diagonal matrix containing the eigenvalues $ \lambda_i $ of $ A $.
     - Each column $ q_i $ of $ Q $ corresponds to the $ i $-th eigenvector, and $ \lambda_i $ is the corresponding eigenvalue.

5. **Truncate Eigen Decomposition**:
   - Retain only the features associated with the **k largest eigenvalues** to capture the most significant variance in the data.

---

### 2. Singular Value Decomposition (SVD)

#### Overview:
- SVD provides an alternative approach to PCA without explicitly computing the covariance matrix.

#### Decomposition:
- Any matrix $ A \in \mathbb{R}^{m \times n} $ can be decomposed as:
  $$
  A = U \Sigma V^T
  $$
  - $ U \in \mathbb{R}^{m \times m} $ : Orthogonal matrix (left singular vectors).
  - $ \Sigma \in \mathbb{R}^{m \times n} $: Diagonal matrix containing the singular values of $ A $.
  - $ V \in \mathbb{R}^{n \times n} $: Orthogonal matrix (right singular vectors).

#### Steps for SVD-based PCA:
1. **Perform SVD** on the data matrix $ A $.
2. **Identify** the $ k $ largest singular values in $ \Sigma $.
3. **Extract** the corresponding columns of $ V $ (associated with the largest singular values).
4. **Compute** the reduced representation of the data using:
   $$
   A V_k
   $$
   where $ V_k $ contains the columns of $ V $ associated with the $ k $ largest singular values.

---

## Summary

### PCA Goal:
- Reduce dimensionality while retaining the most significant information.

### Methods:
1. **Eigenvalue Decomposition**:
   - Use the covariance matrix to identify principal components.
2. **SVD**:
   - Decompose the data matrix directly to extract principal components.

### Key Steps:
1. Compute the covariance matrix or perform SVD.
2. Identify the most significant components (eigenvalues/singular values).
3. Retain the features associated with the largest eigenvalues/singular values.
4. Project the data onto the reduced subspace.

---

This summary highlights the core ideas and techniques used in PCA, focusing on both eigenvalue decomposition and SVD approaches.