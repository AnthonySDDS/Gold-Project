# Gold Recovery Prediction Project

[![View on GitHub](https://img.shields.io/badge/View%20Repo-GitHub-blue)](https://github.com/AnthonySDDS/Gold-Project)

This project aims to build and evaluate predictive models that estimate gold recovery efficiency at various stages of purification in a mining process. Using data from the flotation process, we trained several machine learning models and selected the most accurate based on the final **Symmetric Mean Absolute Percentage Error (sMAPE)**.

## 📁 Repository Contents

- `gold_recovery_train.csv` — training dataset with features and target values.
- `gold_recovery_test.csv` — test dataset (features only).
- `gold_recovery_full.csv` — full dataset with all known targets.
- `notebooks/` — (if added) contains development and training notebooks.
- `models/` — (optional) saved models or results.

## 🧪 Problem Overview

Gold extraction through flotation involves multiple purification stages:
1. Rougher
2. Primary Cleaner
3. Secondary Cleaner
4. Final Purification

The goal is to predict the gold recovery percentage at two key stages:
- `rougher.output.recovery`
- `final.output.recovery`

## ⚙️ Models Trained

We tested the following models using 5-fold cross-validation and sMAPE as the evaluation metric:
- ✅ **Random Forest Regressor** (Best Performer)
- Linear Regression
- Decision Tree Regressor

### 🥇 Final Results:

| Model              | Final sMAPE (%) |
|-------------------|-----------------|
| Random Forest      | ~7.43% ✅ |
| Linear Regression  | ~10.07% |
| Decision Tree      | _(Results vary depending on depth)_

## 📈 Metric: Final sMAPE

Final score was calculated by averaging the sMAPE of predictions for `rougher.output.recovery` and `final.output.recovery`.

\[
\text{final\_smape} = \frac{1}{2} (\text{sMAPE}_{\text{rougher}} + \text{sMAPE}_{\text{final}})
\]

## 📌 Key Takeaways

- The dataset included several missing values and outliers, which were addressed using median imputation and IQR-based filtering.
- The Random Forest model offered the best generalization and will be used for final test set evaluation.
- Logistic Regression was **not used** due to its inapplicability to continuous regression problems.

## 🚀 Getting Started

Clone this repo:
```bash
git clone https://github.com/AnthonySDDS/Gold-Project.git
cd Gold-Project

Install Required Packages:
pip install pandas numpy scikit-learn matplotlib plotly


Run your model script or Jupyter notebook to reproduce results.
