**Date:** 2025-03-22  
**Topics:** PCA, Principal Component Analysis, Least Squares, Eigenvalue Decomposition, Singular Value Decomposition (SVD)  
**Tags**: {#ML #Linear_Algebra #Data_Science}

---

### Lecture 5: PCA

#### Overview
- **Objective**: Find the most significant components that describe the dataset.
- **Goal**: Reduce dimensionality by projecting data into a lower-dimensional space.

---

### Finding Significant Components

#### Least Squares Approach
- Use least squares to find the most significant direction (i.e., the direction of maximum variance).
- Represent the dataset as an $N \times M$ matrix $A$, where:
  - $N$: Number of instances.
  - $M$: Number of features.
- Perform PCA using eigenvalue decomposition of the covariance matrix $AA^T$:
  - The covariance matrix captures correlations among data points.
  - Eigenvalues and eigenvectors represent patterns in the data as an orthogonal basis.

#### Eigenvalue Decomposition
- Eigen decomposition of $A$ is given by:
  $$
  A = Q \Lambda Q^T
  $$
  - $Q$: An $n \times n$ orthogonal matrix whose columns are the eigenvectors $q_i$ of $A$.
  - $\Lambda$: A diagonal matrix where the $i$-th diagonal element $\lambda_i$ is the $i$-th eigenvalue.
- Retain the eigenvectors associated with the $k$ largest eigenvalues.

---

### Singular Value Decomposition (SVD)
- SVD provides an alternative approach to PCA without explicitly computing the covariance matrix.
- Decompose $A$ as:
  $$
  A = U \Sigma V^T
  $$
  - $U$: An $m \times m$ orthogonal matrix (left singular vectors).
  - $\Sigma$: An $m \times n$ diagonal matrix containing the singular values of $A$.
  - $V$: An $n \times n$ orthogonal matrix (right singular vectors).

#### Steps for SVD-based PCA
1. Compute the SVD of $A$:
   $$
   A = U \Sigma V^T
   $$
2. Identify the $k$ largest singular values in $\Sigma$.
3. Extract the corresponding columns of $V$ (associated with the largest singular values).
4. Project the data onto the reduced subspace:
   $$
   AV_k
   $$
   - $V_k$: Matrix formed by the columns of $V$ associated with the $k$ largest singular values.

---

### Summary
- PCA aims to reduce dimensionality while retaining the most significant information.
- Eigenvalue decomposition and SVD are two methods to achieve this:
  - Eigenvalue decomposition works directly on the covariance matrix.
  - SVD avoids explicit computation of the covariance matrix and is often more efficient for large datasets.

---

### Key Equations
1. Eigenvalue decomposition:
   $$
   A = Q \Lambda Q^T
   $$
2. Singular value decomposition:
   $$
   A = U \Sigma V^T
   $$

---

### Notes
- PCA is widely used in data preprocessing, visualization, and feature extraction.
- Choosing the appropriate number of principal components ($k$) is crucial and depends on the explained variance threshold.
- SVD is computationally efficient and numerically stable, making it a preferred choice for large datasets.

---