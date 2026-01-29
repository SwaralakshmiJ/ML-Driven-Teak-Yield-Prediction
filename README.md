# 🌳 ML-Driven Teak(Tectona grandis) Age and Tissue Signature Prediction Using Transcriptomic Data 
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![Scikit-Learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white) ![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)

> **Goal:** Transforming complex transcriptomic (gene expression) signatures into precise yield forecasts for *Tectona grandis* using a high-fidelity Random Forest pipeline.

---

## 🎯 Business Impact
Precise yield prediction allows for optimized plantation management and resource allocation, demonstrating a data-driven approach to high-value biological asset management.

## 🛠️ The Data Science Pipeline

| Step | Action | Key Technical Detail |
| :--- | :--- | :--- |
| **01** | **Cleaning** | Handled missing values in DBH/Height metrics for 100% data integrity. |
| **02** | **Normalization** | Applied **Log1p transformation** to stabilize genomic variance. |
| **03** | **EDA** | validate data integrity and guide feature selection Exploratory data analysis was used |
| **04** | **Dimensionality** | Utilized **PCA** to reduce noise while retaining **83.2% variance**. |
| **05** | **Modeling** | **Random Forest Regressor** with Leave-One-Out (LOOP) validation. |

---

## ⚙️ The Machine Learning Pipeline

### 🌟 Step 1: Data Preprocessing & Cleaning
* **Action:** Conducted a rigorous audit of the raw dataset to identify missing values in physical tree metrics (DBH, Height) and standardized tissue nomenclature.
* **Reason:** High-integrity models require numerical continuity; cleaning prevents "Garbage In, Garbage Out" scenarios.
* **Result:** Established a 100% verified dataset, preventing model failure during the training phase.

---

### 🌟 Step 2: Log Normalization (Log1p)
* **Action:** Implemented a **Log1p transformation** ($log(1+x)$) across all high-dimensional genomic signatures.
* **Reason:** Transcriptomic data is naturally skewed; normalization stabilizes variance and prevents extreme outliers from disproportionately influencing the model.
* **Result:** Achieved a stabilized distribution, allowing for fair feature weighing and better model convergence.

---

### 🌟 Step 3: Dimensionality Reduction (PCA)
* **Action:** Utilized **Principal Component Analysis** to compress thousands of gene signatures into 5 core Principal Components.
* **Reason:** To overcome the "Curse of Dimensionality" and eliminate statistical noise while retaining core biological signals.
* **Result:** Successfully captured **83.2% of total variance** while reducing the feature space by over 95%.

<p align="center">
  <img src="https://github.com/SwaralakshmiJ/ML-Driven-Teak-Yield-Prediction/blob/main/images/01-pca_scree_plot.png" width="600" alt="Scree Plot">
</p>

---

### 🌟 Step 4: Exploratory Data Analysis (EDA)
* **Action:** Visualized multidimensional relationships between PCA components and tissue types using scatter matrices and cluster mapping.
* **Reason:** To validate that the biological signal remained intact and to identify natural groupings (e.g., Flowers vs. Roots).
* **Result:** Confirmed distinct **tissue-specific clusters**, providing the statistical proof required for predictive modeling.

<p align="center">
  <img src="https://github.com/SwaralakshmiJ/ML-Driven-Teak-Yield-Prediction/blob/main/images/03-heatmap.png" width="600" alt="Scree Plot">
</p>
<p align="center">
  <img src="https://github.com/SwaralakshmiJ/ML-Driven-Teak-Yield-Prediction/blob/main/images/02-histogram.png" width="600" alt="Scree Plot">
</p>
---

### 🌟 Step 5: Random Forest Modeling & LOOP Validation
* **Action:** Trained a **Random Forest Regressor** optimized via **Leave-One-Out (LOOP)** Cross-Validation.
* **Reason:** Random Forest effectively captures non-linear biological relationships, and LOOP validation is the gold standard for maximizing data utility in small-batch datasets (12 samples).
* **Result:** Delivered an unbiased, high-precision yield prediction model that ranks primary genomic drivers.

---

## 📂 Repository Structure
* `data/`: Raw and cleaned datasets.
* `notebooks/`: Modularized analysis files (Cleaning, PCA, RF Model).
* `images/`: High-resolution visualizations and performance plots..

  
### 1. Feature Optimization (PCA)
By condensing thousands of genomic markers into 5 Principal Components, I simplified the model without losing critical predictive signals.



### 2. Tissue Signature Mapping
The Unsupervised PCA reveals distinct clustering between tissue types (Flowers vs. Stem vs. Roots), validating the quality of the genomic signatures before modeling.


---

## 🚀 Key Results
* ✅ **83% Information Retention:** Successfully reduced dimensionality using 5-component PCA.
* ✅ **LOOCV Validation:** Ensured zero-bias performance estimation for specialized datasets.
* ✅ **Automated Pipeline:** Built a modular workflow from raw Excel data to final prediction.

---

<details>
<summary><b>View Repository Structure</b></summary>

```text
├── data/       # Raw biological datasets
├── images/     # Performance & EDA visualizations
├── notebooks/  # Modular .ipynb analysis files
└── README.md   # Project documentation

