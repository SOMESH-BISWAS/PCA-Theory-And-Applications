# Principal Component Analysis (PCA): Theory and Applications

A comprehensive, self-contained study of **Principal Component Analysis (PCA)** from first principles, balancing rigorous mathematical derivation with practical, real-world applications. This project showcases the mathematical optimization behind dimensionality reduction and demonstrates its performance on both classic morphometric data and high-dimensional image compression.

## 👥 Authors & Contributors
Developed as a collaborative project by:
* **Aklanta Borah** 
* **Amartya Amritanshu** 
* **Rajveer Vora** 
* **Somesh Biswas** 

---

## 📌 Project Overview

This repository contains the complete pipeline for our PCA research project, including theoretical derivations, implementation scripts, a comprehensive academic report, and presentation slides. 

### Core Objectives
1. **Theoretical Derivation**: Formulating and solving the formal variance-maximization problem subject to unit-norm constraints using Lagrange Multipliers.
2. **Lossless Transformation Proof**: Demonstrating that PCA performs a rigid coordinate system rotation that redistributes total variation across uncorrelated axes without losing structural information.
3. **Morphometric Analysis**: Evaluating low-dimensional clustering and diagnostic metrics (scree plots, correlation circles) using the Fisher Iris dataset.
4. **Image Compression & Low-Rank Approximation**: Applying a rank-$q$ reconstruction framework to the high-dimensional ZIP handwritten-digit dataset.

---

## 🛠️ Mathematical Foundations Covered

* **Variance Maximization**: 
  $$\max_{\delta} \text{Var}(\delta^T X) \quad \text{subject to} \quad \|\delta\|^2 = \delta^T\delta = 1$$
* **The Eigenvalue Problem**: Solving via the Lagrangian function $\mathcal{L}(\delta, \lambda) = \delta^T\Sigma\delta - \lambda(\delta^T\delta - 1)$ to yields the fundamental spectral equation:
  $$\Sigma\delta = \lambda\delta$$
* **Empirical Matrix Centering**: Transforming the $n \times p$ data matrix $\mathcal{X}$ using the centering matrix $\mathcal{H} = \mathcal{I} - (n-1)^{-1}\mathbf{1}_n\mathbf{1}_n^\top$:
  $$\mathcal{S} = (n-1)^{-1}\mathcal{X}^\top\mathcal{H}\mathcal{X}$$
* **Low-Rank Reconstructions**: Rebuilding compressed image frames using $q \ll p$ principal axes:
  $$\hat{\mathcal{X}}_{(q)} = \mathbf{1}_n\bar{x}^T + \mathcal{Y}_{(q)}\mathcal{G}_{(q)}^T$$

---

## 📊 Application Highlights

### 1. Fisher Iris Dataset (Morphometric Evaluation)
* Transformed a 4D feature cloud into a readable 2D embedding space.
* The first two principal components jointly captured **97% of total variance** ($PC1 = 92\%$, $PC2 = 5\%$).
* Emerged unsupervised, cleanly separated biological clusters for *Iris setosa*, *Iris versicolor*, and *Iris virginica* without using class labels during training.
* Mapped structural variable influences using standard diagnostic **Correlation Circles**.

### 2. ZIP Handwritten Digits (Image Reconstruction)
* Applied PCA to a $650 \times 256$ matrix representing flattened $16 \times 16$ greyscale images of the digit "3".
* Evaluated compression performance across varying threshold sizes ($q$).
* **Key Result**: Retaining just **10 principal components** (utilizing only **3.9%** of original pixel data dimensions) successfully preserved enough structural signal to keep the handwritten text perfectly legible while filtering out pixel-level noise.

---

## 🗂️ Repository Structure

```text
├── PCA_Report.pdf       # Full academic project report (Abstract to Conclusion)
├── pca_slides_shared.pdf # Presentation slide deck featuring assigned speaker sections
├── PCA_Codes.Rmd        # Source R Markdown document containing code & explanations
└── README.md            # Project documentation and summary
