**Title:** Factor Augmented Sparse Throughput Deep ReLU Neural
Networks for High Dimensional Regression
**Authors:** Jianqing Fan and Yihong Gu
**Link:** https://arxiv.org/pdf/2210.02002
**Status:** Reading
**Tags:** #ML #Research #Data_Science #Stats

---

# **Fast-NN**

## **Question & Objectives**
- Utilizes [[latent factors]] and [[sparse idiosyncratic components]] for [[nonparametric regression]]

## **Summary**
- Define FAST model as $y_i = m^*(f_i, u_i, J) + \epsilon_i$ where $m*$ is the non parametric regression model, $f_i$ is the latent factor, $u_i$ is the idiosyncratic component, and $J$ is a set of indices of the significant idiosyncratic components

## **Contributions**
- Propose an estimator of Factor Augmented Sparse Throughput Neural Networks
	- The estimator is designed to capture the latent information from the covariate $x$ and use only a small set of idiosyncratic components $u$
		- Accomplished through using a diversified projection matrix and a variable selection matrix before the NN
			- Diversified projection matrix is pre-trained
			- variable selection matrix is trained jointly with the NN
- Factor Estimation Via Diversified Projection Matrix (3.1)
	- Suppose you have a large number of features, but these features might be influenced by a smaller subset of underlying factors. This step of FAST attempts to uncover these hidden factors
		- Defined by two hyperparameters, $\bar{r}$ and $r$ $(\bar{r} \geq r)$ 
			- $\bar{r}$ represents the number of features your model will use to represent the hidden factors
			- $r$ represents the minimum requirement for how many important hidden factors exist (lower bound, not defined explicitly)
		- Computed as:
			$$ \begin{align}
& \text{Input: } \mathbf{X} \in \mathbb{R}^{n \times p}, \bar{r} \in \mathbb{N} \\
& p = \text{shape}(\mathbf{X})[1] \\
& \mathbf{\Sigma}_X = \mathbf{X}^\top \mathbf{X} \\
& \lambda_i, \mathbf{v}_i = \text{eigsh}(\mathbf{\Sigma}_X, \bar{r}, \text{which='LM'}) \\
& \mathbf{W} = \frac{\mathbf{v}_i}{\sqrt{p}} \\
& \mathbf{F} = \mathbf{X} \mathbf{W} \\
& \mathbf{\Sigma}_F = \mathbf{F}^\top \mathbf{F} \\
& \mathbf{\Sigma}_{FX} = \mathbf{F}^\top \mathbf{X} \\
& \mathbf{R} = \mathbf{\Sigma}_F^{+} \mathbf{\Sigma}_{FX} \\
& \text{Return: } \mathbf{W}, \mathbf{R}
\end{align}$$
- Propose a regularization loss to encourage interpretability and efficiency in high-dimensional settings
	- Encourages sparsity & diversity
			
## **Closing Thoughts & Questions**
- These Princeton mfs added two linear layers and published at a T1 💀


