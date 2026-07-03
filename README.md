# Detecting Suspicious Financial Transactions Using Machine Learning

## Overview

Financial institutions process millions of transactions daily, and manually
reviewing all of them for money laundering activity is infeasible. This
project builds a machine learning classifier that flags financial
transactions as **suspicious / high-risk**, based on historical labeled
data covering a range of AML typologies (e.g. structuring, layering,
cross-border cash movements).

**Important note:** This model predicts a *suspicious / high-risk flag* for
further review by an AML analyst. It does **not** predict, automate, or
replace the decision to file a Suspicious Activity Report (SAR) — that
remains a human, legal, and regulatory decision made by a compliance
analyst after full investigation. The model's role is limited to
**alert generation / transaction triage**, not regulatory determination.

## Problem Statement

Money laundering causes an estimated 2–5% of global GDP in illicit flows
each year. Traditional AML systems rely heavily on static, rule-based
transaction monitoring, which tends to generate large volumes of false
positives and misses more sophisticated typologies. This project explores
whether supervised machine learning can improve on rule-based detection by
learning patterns directly from labeled transaction data, while explicitly
accounting for the extreme class imbalance inherent to AML data (suspicious
transactions typically make up far less than 1% of all transactions).

## Dataset

**SAML-D — Synthetic Transaction Monitoring Dataset for AML**
Source: [Kaggle — berkanoztas/synthetic-transaction-monitoring-dataset-aml](https://www.kaggle.com/datasets/berkanoztas/synthetic-transaction-monitoring-dataset-aml)

- ~9.5M synthetic but realistically-modeled transactions
- 12 features: timestamp, sender/receiver account & bank location, amount,
  payment type, currencies, etc.
- Binary label (`is_suspicious`) plus a `Typology` column describing the
  specific behavioral pattern (11 normal + 17 suspicious typologies)
- Highly imbalanced: suspicious transactions are ~0.1% of the dataset
- 
**Sampling Strategy**

Due to the extreme class imbalance of the original dataset, a stratified sampling strategy is applied by retaining all suspicious transactions and a representative subset of normal transactions. This produces a computationally manageable dataset while preserving meaningful class proportions for model training and evaluation.

## Approach

The project follows a standard supervised machine learning workflow:

- Exploratory Data Analysis (EDA) and class imbalance analysis
- Stratified sampling to obtain a computationally manageable dataset while preserving all suspicious transactions
- Data preprocessing (encoding, scaling, train/test split)
- Feature engineering based on transaction characteristics
- Principal Component Analysis (PCA) for dimensionality reduction
- Model training using Logistic Regression, Decision Tree, Random Forest and Support Vector Machine
- Model evaluation using Precision, Recall, F1-score, ROC-AUC and confusion matrices
- Comparison of model performance and business interpretation of the results

## Results



## How to Run

jupyter notebook notebook.ipynb


## References

- Oztas, B. et al. (2023). *Enhancing Anti-Money Laundering: Development of a Synthetic Transaction Monitoring Dataset.* IEEE ICEBE 2023.
- Dataset: https://www.kaggle.com/datasets/berkanoztas/synthetic-transaction-monitoring-dataset-aml
