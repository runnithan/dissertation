# 📘 Equity Fund Profitability and Sustainability Modelling Using Multiple-Response Regression

This repository contains the code, data, and final report for my undergraduate dissertation at Durham University. The project investigates **Multiple-Response Regression (MRR)** models for predicting both profitability and sustainability metrics of equity funds, using a real-world dataset and advanced statistical and machine learning methods.

## 📄 Project Summary

**Title:** *Equity Fund Profitability and Sustainability Modelling Using Multiple-Response Regression*  
**Author:** Raul Unnithan  
**Supervisor:** Ric Crossman  
**Submitted:** May 2025  
**Department:** Mathematical Sciences, Durham University

This dissertation compares the effectiveness of multiple MRR models in predicting two correlated outcomes:  
- **Return on Equity (ROE)** (profitability)
- **Sustainability Score** (ESG performance)

The models include classical statistical methods, shrinkage approaches, and modern machine learning models, all evaluated using **Average Normalised Root Mean Square Error (ANRMSE)**.

---

## 🔍 Methods Used

### 📊 Statistical Models

- **Multiple-Response Linear Regression (MRLR)**  
- **Sequential MANOVA Stepwise Selection**  
  Custom implementation using Wilks' Lambda and ANRMSE  
- **Shrinkage Methods**  
  - Ridge Regression  
  - Reduced-Rank Ridge Regression  
  - Multivariate Regression with Covariance Estimation (MRCE)

### 🌲 Machine Learning Models

- **Random Forests** (via Multivariate Regression Trees & Covariance Regression)  
- **XGBoost** with Cholesky Decomposition for multivariate prediction

---

## 🧪 Dataset

- Sourced from Kaggle; filtered to include equity funds only  
- **1248 observations**, **12 predictor variables**
- **2 response variables**:
  - **Return on Equity (ROE)**  
  - **Sustainability Score** (Morningstar ESG rating)

**Preprocessing Includes:**
- Imputation via Random Forests & Linear Regression  
- Multivariate normality tested via Mardia's test  
- Multicollinearity checked using VIF

---

## 📈 Evaluation Metric

All models are compared using:
- **ANRMSE** (Average Normalised Root Mean Square Error)  
- Supplemented by **Wilks’ Lambda** for feature selection during stepwise procedures

---

## 🧰 Tools and Environment

- **Language:** R  
- **Libraries:** `car`, `glmnet`, `xgboost`, `ranger`, `psych`, `keras`, `tensorflow`, `tidyverse`, etc.

---

## 🛡️ Disclaimer

This work was completed as part of my undergraduate degree and is intended for academic and illustrative purposes only. Not financial advice.

---

## 📁 Repository Structure

```plaintext
📦dissertation/
 ┣ 📂articles/                   # Reference papers and supporting articles
 ┣ 📂code/                      # All R scripts and notebooks for model implementation and evaluation
 ┣ 📂dissertation-meetings/     # Notes and summaries from supervisor meetings
 ┣ 📂example-dissertations/     # Sample dissertations for reference
 ┣ 📂presentation-and-poster/   # Presentation slides and academic poster work
 ┣ 📂report-versions/           # Drafts and prior versions of the dissertation
 ┣ 📂report-latex/              # LaTeX source code for dissertation write-up
 ┣ 📜README.md                  # This file
 ┣ 📄raul_unnithan_dissertation.pdf   # Final dissertation report
 ┣ 📄raul_unnithan_poster.pdf         # Academic poster for research presentation
 ┗ 📄raul_unnithan_presentation.pdf   # Final presentation slides
