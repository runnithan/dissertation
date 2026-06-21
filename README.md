# 📘 Equity Fund Profitability and Sustainability Modelling Using Multiple-Response Regression

![Language](https://img.shields.io/badge/language-R-276DC3?logo=r&logoColor=white)
![Report](https://img.shields.io/badge/report-LaTeX-008080?logo=latex&logoColor=white)
![University](https://img.shields.io/badge/Durham%20University-Mathematical%20Sciences-680032)
![Year](https://img.shields.io/badge/submitted-May%202025-555)

Undergraduate dissertation (Durham University) investigating **Multiple-Response Regression (MRR)** models that predict the **profitability** and **sustainability** of equity funds *jointly*, exploiting the correlation between the two outcomes rather than modelling each in isolation. The repository holds the full LaTeX report, the R/Python implementation, the supporting literature, and the presentation materials.

---

## 📑 Contents

- [Project Summary](#-project-summary)
- [Methods](#-methods)
- [Dataset](#-dataset)
- [Evaluation](#-evaluation)
- [Repository Structure](#-repository-structure)
- [Reproducing the Work](#-reproducing-the-work)
- [Deliverables](#-deliverables)
- [Tools and Environment](#-tools-and-environment)
- [Disclaimer](#-disclaimer)
- [Author and Acknowledgements](#-author-and-acknowledgements)

---

## 📄 Project Summary

|              |                                                                            |
| ------------ | -------------------------------------------------------------------------- |
| **Title**    | *Equity Fund Profitability and Sustainability Modelling Using Multiple-Response Regression* |
| **Author**   | Raul Unnithan                                                              |
| **Supervisor** | Ric Crossman                                                            |
| **Department** | Mathematical Sciences, Durham University                                |
| **Submitted** | May 2025                                                                  |

The dissertation compares a range of MRR models on two **correlated** responses:

- **Return on Equity (ROE)** — profitability
- **Sustainability Score** — ESG performance (Morningstar rating)

Models span classical statistics, shrinkage estimators, and modern machine learning, all evaluated on a common footing with the **Average Normalised Root Mean Square Error (ANRMSE)**.

---

## 🔍 Methods

### 📊 Statistical Models

- **Multiple-Response Linear Regression (MRLR)**
- **Sequential MANOVA Stepwise Selection** — custom implementation using Wilks' Lambda and ANRMSE
- **Shrinkage Methods**
  - Ridge Regression
  - Reduced-Rank Ridge Regression (RRRR)
  - Multivariate Regression with Covariance Estimation (MRCE)

### 🌲 Machine Learning Models

- **Random Forests** — via Multivariate Regression Trees (MRT) and Covariance Regression Forests (CovRegRF)
- **XGBoost** — with Cholesky decomposition for multivariate (multi-target) prediction

---

## 🧪 Dataset

- Sourced from Kaggle; filtered to **equity funds only**
- **1,248 observations**, **12 predictor variables**, **2 response variables** (ROE and Sustainability Score)

**Preprocessing**

- Missing-data imputation via Random Forests and Linear Regression
- Multivariate normality assessed with **Mardia's test**
- Multicollinearity checked using the **Variance Inflation Factor (VIF)**

---

## 📈 Evaluation

- Primary metric: **ANRMSE** (Average Normalised Root Mean Square Error), enabling a fair comparison across models with differently scaled responses
- **Wilks' Lambda** used for feature selection during the stepwise procedures

Full results, derivations, and figures are in the final report — see [Deliverables](#-deliverables).

---

## 📁 Repository Structure

```plaintext
📦 dissertation/
 ┣ 📂 articles/                  # Reference papers, grouped by chapter (c1–c7)
 ┃  ┗ 📂 c4/multivariate-ridge-and-lasso/   # Deeper reading for the shrinkage chapter
 ┣ 📂 code/                      # R scripts and notebooks for the models
 ┃  ┣ 📜 calculations.R
 ┃  ┣ 📜 shrinkage_methods.R                 # Ridge / RRRR / MRCE
 ┃  ┣ 📓 manova_stepwise_selection.ipynb     # Sequential MANOVA stepwise selection
 ┃  ┣ 📓 random_forest.ipynb                 # MRT / CovRegRF
 ┃  ┗ 📓 cholesky_gaussian_xgboost.ipynb     # Cholesky-based multivariate XGBoost
 ┣ 📂 dissertation-meetings/     # Notes and feedback from supervisor meetings
 ┣ 📂 example-dissertations/     # Sample dissertations referenced for structure
 ┣ 📂 presentation-and-poster/   # Slides, poster, and their version history
 ┣ 📂 report-versions/           # Earlier drafts of the dissertation
 ┣ 📂 report-latex/              # LaTeX source for the final write-up
 ┃  ┣ 📜 main.tex                            # Entry point — compile this
 ┃  ┣ 📜 references.bib
 ┃  ┗ 📂 images/  plots/  algorithms/        # Figures referenced by main.tex
 ┣ 📄 raul_unnithan_dissertation.pdf         # Final dissertation report
 ┣ 📄 raul_unnithan_poster.pdf               # Academic poster
 ┣ 📄 raul_unnithan_presentation.pdf         # Final presentation slides
 ┣ 📄 raul_unnithan_chalkdust_article.pdf    # Companion Chalkdust article
 ┗ 📜 README.md
```

> **Naming convention:** folders use `kebab-case`, files use `snake_case`.

---

## 🔁 Reproducing the Work

### Build the report (LaTeX)

```bash
cd report-latex
latexmk -pdf main.tex      # or: pdflatex main.tex && bibtex main && pdflatex main.tex && pdflatex main.tex
```

`main.tex` is the entry point; all figures resolve from `images/`, `plots/`, and `algorithms/`.

### Run the models (R / Jupyter)

The `code/` directory holds the analysis:

- **R scripts** (`*.R`) — run with `Rscript code/shrinkage_methods.R`, or open in RStudio.
- **Notebooks** (`*.ipynb`) — open in Jupyter; the R cells require an R kernel (e.g. [IRkernel](https://irkernel.github.io/)).

See [Tools and Environment](#-tools-and-environment) for the package list.

---

## 📦 Deliverables

| File | Description |
| ---- | ----------- |
| [`raul_unnithan_dissertation.pdf`](raul_unnithan_dissertation.pdf) | Final dissertation report |
| [`raul_unnithan_poster.pdf`](raul_unnithan_poster.pdf) | Academic poster |
| [`raul_unnithan_presentation.pdf`](raul_unnithan_presentation.pdf) | Final presentation slides |
| [`raul_unnithan_chalkdust_article.pdf`](raul_unnithan_chalkdust_article.pdf) | Companion Chalkdust article |

---

## 🧰 Tools and Environment

- **Language:** R (with Python/Jupyter notebooks for some models)
- **Key libraries:** `car`, `glmnet`, `xgboost`, `ranger`, `psych`, `keras`, `tensorflow`, `tidyverse`
- **Report:** LaTeX (`latexmk` / `pdflatex` + `bibtex`)

---

## 🛡️ Disclaimer

This work was completed as part of an undergraduate degree and is intended for **academic and illustrative purposes only**. It is **not financial advice**.

---

## 🙏 Author and Acknowledgements

**Raul Unnithan** — Department of Mathematical Sciences, Durham University.
Supervised by **Ric Crossman**, whose guidance shaped the direction of this project.
