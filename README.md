# Advanced Linear Algebra: PCA from Scratch
### Exploring Financial Inclusion in Africa

## 📌 Project Overview
This repository contains a manual implementation of **Principal Component Analysis (PCA)** as part of a Formative Assignment for Advanced Linear Algebra. 

Unlike standard implementations that rely on libraries like `sklearn`, this project builds the PCA algorithm from the ground up using **NumPy** and linear algebra principles (Eigendecomposition, Covariance Matrices, and Orthogonal Projections).

The goal was to reduce the dimensionality of a complex, real-world African dataset while preserving the maximum amount of information (variance).

## 🌍 The Dataset: Financial Inclusion in Africa
* **Source:** [Zindi / Kaggle - Financial Inclusion in Africa](https://zindi.africa/competitions/financial-inclusion-in-africa)
* **Context:** The dataset captures demographic information from **Kenya, Rwanda, Tanzania, and Uganda** to predict the likelihood of an individual having a bank account.
* **Why this data?**
    * **African Context:** Relevant to the continent's economic development.
    * **Complexity:** Contains >10 columns with a mix of categorical (Job, Marital Status) and numerical (Age, Household Size) features.
    * **Real-World Messiness:** Handles actual missing values (`NaN`) and discrete data types.

## ⚙️ Technical Implementation
The project follows a strict step-by-step mathematical derivation:

1.  **Data Preprocessing:**
    * Handling "hidden" missing values (converting "Don't Know" responses to `NaN`).
    * Imputation using Mode (for categoricals) and Mean (for numericals).
    * One-Hot Encoding to convert categorical features (e.g., "Rural/Urban") into numeric matrices.
2.  **Standardization:**
    * Manual implementation of Z-score normalization: $z = \frac{x - \mu}{\sigma}$
3.  **Covariance Matrix Computation:**
    * Calculating the relationship between variables: $\Sigma = \frac{X^T X}{n-1}$
4.  **Eigendecomposition:**
    * Deriving Eigenvalues ($\lambda$) and Eigenvectors ($v$) to identify principal directions of variance.
5.  **Dimensionality Reduction:**
    * Projecting the high-dimensional data (30+ features) onto the top 2 Principal Components.

## 📊 Key Results & Insights
### 1. Visualization
* **Original Space:** The raw data (plotted as Household Size vs. Age) exhibited a grid-like lattice structure due to the discrete integer nature of the survey responses.
* **PCA Space:** The projected data formed distinct diagonal striations. This visualization confirms that PCA successfully captured the variance introduced by the categorical variables (like Job Type and Education).

### 2. Explained Variance
* **Dynamic Selection:** The algorithm dynamically calculated that **[Insert Your Number Here, e.g., 20]** components are required to explain **90%** of the dataset's variance.
* **Class Overlap:** The visualization showed significant overlap between the "Bank Account: Yes" and "No" classes, indicating that financial inclusion is a complex, non-linear problem not defined by simple demographic boundaries.

## 🛠️ Dependencies
To run this notebook, you will need:
* Python 3.x
* NumPy (for Linear Algebra)
* Pandas (for Data Manipulation)
* Matplotlib & Seaborn (for Visualization)

```bash
pip install numpy pandas matplotlib seaborn
