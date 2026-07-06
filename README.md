# Detecting Suspicious Financial Transactions Using Machine Learning

## Overview

Financial institutions process millions of transactions every day, making manual review for potential money laundering activity increasingly impractical. This project develops and evaluates supervised machine learning models capable of identifying potentially suspicious (high-risk) financial transactions using historical labelled transaction data representing multiple Anti-Money Laundering (AML) typologies.

**Important note:** This model predicts a suspicious transaction flag for further review by an AML analyst. It does **not** automate or replace the decision to file a Suspicious Activity Report (SAR). Filing a SAR remains a legal and regulatory decision performed by a compliance analyst after a complete investigation. The purpose of this model is limited to transaction prioritisation and alert generation.

---

# Problem Statement

Money laundering is estimated to account for approximately 2–5% of global GDP annually. Traditional AML transaction monitoring systems rely primarily on predefined business rules, which frequently generate large numbers of false positive alerts while failing to detect increasingly sophisticated laundering techniques.

This project investigates whether supervised machine learning algorithms can improve suspicious transaction detection by learning transaction patterns directly from labelled historical data. Special attention is given to the severe class imbalance naturally present in AML datasets, where laundering transactions represent only a very small proportion of all observations.

---

# Dataset

**SAML-D — Synthetic Transaction Monitoring Dataset for Anti-Money Laundering**

Source:
https://www.kaggle.com/datasets/berkanoztas/synthetic-transaction-monitoring-dataset-aml

### Dataset characteristics

- Approximately **9.5 million** synthetic financial transactions
- 12 transaction-related features
- Binary target variable: **Is_laundering**
- Additional **Laundering_type** column describing suspicious transaction typologies
- Highly imbalanced dataset containing approximately **0.1% laundering transactions**

---

# Sampling Strategy

Because the original dataset contains approximately **9.5 million transactions**, directly training machine learning models would require substantial computational resources.

A representative sample dataset was therefore created by:

- retaining all **9,873 laundering transactions**
- randomly sampling **190,000 legitimate transactions**

The resulting dataset contains **199,873 transactions**, providing a substantially improved class distribution while preserving realistic transaction characteristics for machine learning experiments.

---

# Methodology

The project follows a complete supervised machine learning workflow:

- Creation of a representative sampled dataset
- Exploratory Data Analysis (EDA)
- Data preprocessing
  - Missing value analysis
  - Feature selection
  - Feature engineering
  - Label Encoding
  - Train/Test Split
  - Feature Scaling
- Principal Component Analysis (PCA)
- Model development using:
  - Logistic Regression
  - Decision Tree
  - Random Forest
  - Linear Support Vector Classifier (LinearSVC)
- Model evaluation using:
  - Accuracy
  - Precision
  - Recall
  - F1-score
  - ROC-AUC
  - Confusion Matrix
  - Classification Report
  - ROC Curve
  - Precision–Recall Curve
- Comparison of model performance

---

# Results

Four supervised machine learning algorithms were evaluated for AML transaction classification.

Among the evaluated models, **Random Forest** achieved the strongest overall performance by providing the highest Precision, F1-score and ROC-AUC while maintaining excellent Accuracy.

Decision Tree and Linear Support Vector Classifier achieved higher Recall by identifying a larger proportion of suspicious transactions, although this resulted in substantially more false positive predictions.

Overall, Random Forest provided the best balance between identifying suspicious transactions and minimizing false positive alerts, making it the most suitable model for this AML dataset.


# How to Run

1. Download the original **SAML-D** dataset from Kaggle.
2. Run **create_sample_dataset.ipynb** to generate **AML_sample.csv**.
3. Open **Project 3.ipynb**.
4. Execute all notebook cells sequentially to reproduce the complete machine learning workflow.

---

# Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

---

# References

- Oztas, B. et al. (2023). *Enhancing Anti-Money Laundering: Development of a Synthetic Transaction Monitoring Dataset.* IEEE ICEBE 2023.
- SAML-D Dataset:
  https://www.kaggle.com/datasets/berkanoztas/synthetic-transaction-monitoring-dataset-aml
