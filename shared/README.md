# Shared Preprocessing Work – Phase 1

This folder contains all collaborative notebooks and scripts produced during **Phase 1 (Weeks 1–5)**.
Every group member contributed; commits in this folder represent joint work.

## Contents

| File / Notebook | Description |
|---|---|
| `01_eda.ipynb` | Exploratory Data Analysis – distributions, correlations, missing-value heatmaps |
| `02_cleaning.ipynb` | Missing-value imputation, duplicate removal, outlier treatment |
| `03_encoding.ipynb` | Categorical encoding (label encoding / one-hot encoding) |
| `04_scaling.ipynb` | Feature scaling (standardisation / min-max normalisation) |
| `05_train_test_split.ipynb` | Final train/test split saved to `data/processed_dataset.csv` |

## Steps Performed

1. **Data Collection** – Raw CSV placed in `data/raw_dataset.csv`. Source and collection method documented in `01_eda.ipynb`.
2. **EDA** – Summary statistics, class-balance check, correlation matrix, visualisations.
3. **Cleaning** – Handle missing values, remove duplicates, cap/remove outliers.
4. **Encoding** – Convert categorical columns to numeric representations.
5. **Scaling** – Normalise / standardise numeric features so all models start from the same baseline.
6. **Export** – Final processed file written to `data/processed_dataset.csv`.

> **Note:** Do not modify `data/raw_dataset.csv`. All transformations are applied in these notebooks and the result is saved to `data/processed_dataset.csv`.
