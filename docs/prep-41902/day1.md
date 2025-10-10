---
title: Day 1 - Project Setup
parent: Stat Learning
nav_order: 1
math: true
toc: true
---

# Day 1: Project Setup & Exploratory Foundations
{: .no_toc}

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

You’ll start by **designing, structuring, and documenting** a reproducible data-science project pipeline.
Future days (linear regression, classification, CV, regularization, etc.) will *add models, analysis, and extensions* to this same codebase.

Below is a **project-oriented assignment instruction** for **Day 1**.

## 🎯 Objective

Build a fully-structured Python project called **`statlearn-pipeline`** that will:

1. Load and preprocess multiple real datasets from ISLP.
2. Support modular experiments (you’ll add models in later days).
3. Produce standardized reports (plots, tables, metrics).
4. Be reproducible, version-controlled, and ready for extensions (ridge, SVM, etc.).

## 📚 Part 0 - Reading

1. ISL Chap 1
2. ISL Chap 2.1 - 2.2

## 🗂️ Part 1 – Project Architecture

Create a clean, professional repository structure:

```
stat-learn/
├── data/
│   ├── raw/              # unprocessed CSVs
│   ├── processed/        # clean data saved as parquet/csv
│   └── external/         # optional external sources (e.g. Yahoo Finance, Kaggle)
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   └── ...   # to be used later
├── src/
│   └── stat_learn/
│       ├── __init__.py
│       ├── data.py
│       ├── features.py
│       ├── visualization.py
│       ├── models/
│       │   ├── __init__.py
│       │   ├── baseline.py
│       │   └── metrics.py
│       └── config.py
├── reports/
│   ├── figures/
│   └── summaries/
├── pyproject.toml
├── .venv
├── .gitignore
└── README.md
```

This structure ensures scalability when you add more models (ridge, trees, etc.) later.

## ⚙️ Part 2 – Environment & Data Access

1. Create a **Conda or virtualenv** called `islp-env`.
   Include `numpy`, `pandas`, `matplotlib`, `seaborn`, `scikit-learn`, `jupyter`, `pyarrow` and `islp`.

2. In a startup script (`src/config.py`), define path constants that your other scripts will import — no hard-coded file paths.

3. Verify that you can access ISLP datasets (e.g., `Advertising`, `Wage`, `Smarket`).

## 🧩 Part 3 – Dataset Integration and Documentation

You’ll begin with **two datasets** that will serve different modeling purposes later:

| Dataset       | Used later for                | Variables to note                   |
| ------------- | ----------------------------- | ----------------------------------- |
| `Advertising` | Regression (predicting Sales) | `TV`, `Radio`, `Newspaper`          |
| `Smarket`     | Classification                | `Lag1`–`Lag5`, `Today`, `Direction` |

**Tasks**

1. Write a loader that fetches each dataset from the ISLP package and saves it under `/data/raw/`.
2. Generate a `DATA_DICTIONARY.md` file summarizing:

   * variable names, types, and short descriptions
   * intended modeling goals (`target` vs `features`)
   * shape and number of missing values
3. Log metadata (e.g., shape, null count) automatically each time you load a dataset.

## 📊 Part 4 – Exploratory Data Analysis (EDA)

In `notebooks/01_data_exploration.ipynb`, perform **data-driven storytelling**, not just plots:

1. **Overview summary**: shape, numeric summaries, missing data, correlations.
2. **Visual intuition**:

   * scatterplots of `Sales` vs each ad medium (Advertising)
   * pairplot or heatmap for Smarket’s lag variables
3. **Feature notes:** write 1–2 sentences about trends, possible nonlinearity, or collinearity.
4. **Create helper functions** in `src/visualization/plots.py`:

   * reusable plotting API: scatter, correlation matrix, pairwise density.

End EDA by exporting:

* `reports/figures/advertising_eda.png`
* `reports/figures/smarket_eda.png`
* `reports/summaries/day1.md` (include your observations).

## 🧮 Part 5 – Foundational Implementation Tasks

You’ll implement minimal reusable code that later chapters will extend:

1. **Data container class**

   * `DatasetWrapper` storing `.X`, `.y`, `.feature_names`, `.target_name`
   * Include a `.split(train_ratio)` method returning train/test sets.

2. **Metrics utilities**

   * Write function signatures (no implementations yet) for:

     * `mean_squared_error(y_true, y_pred)`
     * `accuracy_score(y_true, y_pred)`
     * `bias_variance_decomp(...)` placeholder for Day 7.

3. **Version control**

   * Initialize Git repo.
   * Commit after each milestone.
   * Write a concise README explaining your project scope, dataset purpose, and next steps (e.g., “next we’ll fit a linear model on the Advertising dataset”).

## 🧠 Part 6 – Conceptual Reflection

In `reports/summaries/day1.md`, include short answers:

1. What is the **statistical learning problem** formalized as ( Y = f(X) + \varepsilon )?
   Explain how `Advertising` fits this form.
2. Define *supervised* vs *unsupervised* learning in your own words, using the ISLP datasets as examples.
3. What are the sources of **error** in prediction? (Briefly discuss reducible vs irreducible.)
4. Describe your plan for model versioning and experiment tracking going forward.

## 🧱 Deliverables (End of Day 1)

* [ ] Project directory (version-controlled, reproducible)
* [ ] Two cleaned datasets in `/data/processed`
* [ ] Reusable EDA notebook and visualization helpers
* [ ] Metadata + summary markdown file
* [ ] Placeholder Python modules (`DatasetWrapper`, metrics skeletons)
* [ ] Conceptual summary connecting data to ISLP Ch. 2 ideas