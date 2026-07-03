# Detecting Suspicious Financial Transactions Using Machine Learning

## Overview

Financial institutions process millions of transactions daily, making manual review for potential money laundering activity increasingly impractical. This project develops a supervised machine learning classifier capable of identifying **potentially suspicious / high-risk financial transactions** based on historical labeled transaction data representing various Anti-Money Laundering (AML) typologies.

**Important note:** This model predicts a *high-risk transaction flag* for further review by an AML analyst. It does **not** predict, automate, or replace the decision to file a Suspicious Activity Report (SAR). Filing a SAR remains a legal and regulatory decision performed by a compliance analyst after a complete investigation. The purpose of this model is limited to **transaction triage and alert generation**.

---

## Problem Statement

Money laundering is estimated to account for approximately **2–5% of global GDP** each year. Traditional AML transaction monitoring systems rely primarily on predefined business rules, which often generate large numbers of false positive alerts while failing to detect increasingly sophisticated laundering techniques.

This project investigates whether supervised machine learning algorithms can improve suspicious transaction detection by learning patterns directly from historical labeled transaction data. Special attention is given to the severe class imbalance naturally present in AML datasets, where laundering transactions represent only a very small proportion of all transactions.

---

## Dataset

**SAML-D — Synthetic Transaction Monitoring Dataset for Anti-Money Laundering**

**Source:** https://www.kaggle.com/datasets/berkanoztas/synthetic-transaction-monitoring-dataset-aml

Dataset characteristics:

- Approximately **9.5 million** synthetic financial transactions
- 12 transaction-related features
- Binary target variable **`Is_laundering`**
- **`Laundering_type`** column describing the laundering typology associated with suspicious transactions
- Highly imbalanced dataset with approximately **0.1% laundering transactions**

---

## Sampling Strategy

Because the original dataset contains approximately **9.5 million transactions**, directly training machine learning models would be computationally expensive and unnecessarily time-consuming for this project.

A representative sample dataset was therefore created by:

- retaining **all 9,873 laundering transactions**
- randomly selecting **190,000 normal transactions**

The resulting dataset contains **199,873 transactions**, providing a significantly improved class distribution while preserving realistic transaction characteristics for machine learning experiments.

---

## Approach

The project follows a standard supervised machine learning workflow:

- Creation of a representative sample dataset
- Exploratory Data Analysis (EDA)
- Data preprocessing (encoding, scaling and train/test split)
- Feature engineering based on transaction characteristics
- Principal Component Analysis (PCA)
- Model training using:
  - Logistic Regression
  - Decision Tree
  - Random Forest
  - Support Vector Machine (SVM)
- Model evaluation using:
  - Precision
  - Recall
  - F1-score
  - ROC-AUC
  - Confusion Matrix
- Comparison of model performance and business interpretation of the results

---

## Results

The results section will be completed after training and evaluating the machine learning models.

---

## Repository Structure

```
Project 3.ipynb
create_sample_dataset.ipynb
README.md
```

- **create_sample_dataset.ipynb** generates a representative dataset (`AML_sample.csv`) from the original SAML-D dataset.
- **Project 3.ipynb** contains the complete machine learning workflow, including data analysis, preprocessing, model training and evaluation.

---

## How to Run

1. Download the original **SAML-D** dataset from Kaggle.
2. Run **create_sample_dataset.ipynb** to generate `AML_sample.csv`.
3. Open **Project 3.ipynb** and execute all cells to reproduce the complete machine learning pipeline.

---

## References

- Oztas, B. et al. (2023). *Enhancing Anti-Money Laundering: Development of a Synthetic Transaction Monitoring Dataset*. IEEE ICEBE 2023.
- SAML-D Dataset: https://www.kaggle.com/datasets/berkanoztas/synthetic-transaction-monitoring-dataset-aml
