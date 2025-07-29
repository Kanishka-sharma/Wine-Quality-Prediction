# 🍷 Wine Quality Prediction

This project focuses on building predictive models for estimating the quality of Portuguese "Vinho Verde" wine samples (both red and white variants) based on their physicochemical properties. The aim is to explore and evaluate different supervised learning methods for modeling wine quality, a complex sensory output influenced by multiple chemical factors.

---

## 📊 Dataset Overview

**Source:**  
Created by Paulo Cortez (University of Minho), Antonio Cerdeira, Fernando Almeida, Telmo Matos, and Jose Reis (CVRVV) in 2009.

**Reference Publication:**  
Cortez, P., Cerdeira, A., Almeida, F., Matos, T., & Reis, J. (2009).  
*Modeling wine preferences by data mining from physicochemical properties.*  
Decision Support Systems, Elsevier, 47(4):547–553.

**Download Link:**  
[UCI Machine Learning Repository - Wine Quality Dataset](https://archive.ics.uci.edu/ml/datasets/wine+quality)

### Key Facts

- **Type:** Real-world, multivariate dataset
- **Samples:**  
  - Red wine: 1599 samples  
  - White wine: 4898 samples  
- **Features:** 11 numeric input variables + 1 output quality score (0 to 10)
- **Missing Values:** None
- **Problem Type:** Can be approached as either regression or classification

---

## 🧪 Features

| Feature                  | Description                         |
|--------------------------|-------------------------------------|
| 1. fixed acidity         | Tartaric acid concentration         |
| 2. volatile acidity      | Acetic acid level (vinegar taste)   |
| 3. citric acid           | Citric acid concentration           |
| 4. residual sugar        | Sugar remaining after fermentation  |
| 5. chlorides             | Salt concentration                  |
| 6. free sulfur dioxide   | Antimicrobial agent level           |
| 7. total sulfur dioxide  | Sum of all SO₂ forms                |
| 8. density               | Relative density of the wine        |
| 9. pH                    | Acidity/alkalinity level            |
| 10. sulphates            | Antimicrobial and wine preservative |
| 11. alcohol              | Alcohol content (% vol)             |
| 12. quality (target)     | Wine quality (0 = bad to 10 = excellent) |

---

## 🧹 Data Cleaning & Exploratory Data Analysis

- **Data Inspection:** Checked for data types and ensured numeric consistency across all features.
- **Missing Values:** Confirmed dataset has no missing values.
- **Correlations:** Visualized correlations using heatmaps and pairplots to identify multicollinearity.
- **Distributions:** Used histograms and boxplots to assess skewness, outliers, and distribution of wine quality scores.
- **Insights:**
  - Alcohol content and volatile acidity showed strong correlations with wine quality.
  - Wine quality ratings are imbalanced, with most samples concentrated around the 5–6 score range.

---

## 🧠 Modeling Approach

Two modeling strategies were applied to estimate wine quality:

### 🔹 Model 1: Elastic Net Regression
A regularized regression method combining L1 (lasso) and L2 (ridge) penalties.

- **Why?** Good for handling multicollinearity and performing automatic feature selection.
- **Result:** Moderate performance with R² of **0.281** and accuracy of **55.0%** within ±0.5 rating tolerance.

### 🔹 Model 2: Random Forest Regressor
An ensemble learning technique using bagged decision trees.

- **Why?** Captures complex, non-linear relationships and is robust to outliers.
- **Result:** Higher accuracy of **59.5%** and R² of **0.387**, outperforming the Elastic Net model.

---

## ⚖️ Model Comparison

| Metric                  | Elastic Net | Random Forest |
|-------------------------|-------------|----------------|
| R² Score                | 0.281       | 0.387          |
| Accuracy (±0.5 rating)  | 55.0%       | 59.5%          |
| Key Features Identified | Alcohol, Density, Volatile Acidity | Same + Sulphates |

> The results demonstrate that **Random Forest** outperforms the Elastic Net model, capturing the non-linear dependencies between chemical features and sensory quality more effectively.






