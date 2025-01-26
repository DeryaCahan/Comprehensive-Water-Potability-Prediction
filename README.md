# Water Potability Prediction

Understanding water potability is a critical issue for human health and sustainability. Leveraging modern machine learning techniques to ensure the safety of drinking water through detailed analysis. This model can assist water treatment facilities or environmental agencies in creating secure water resources by analyzing environmental data and identifying risks effectively.


## Contents
- [Introduction](#introduction)
- [Dataset Description](#dataset-description)
  - [Overview of the Dataset](#overview-of-the-dataset)
  - [Dataset Variables](#dataset-variables)
- [Data Preprocessing](#data-preprocessing)
  - [Handling Missing Values](#handling-missing-values)
  - [Handling Outliers](#handling-outliers)
  - [Feature Engineering](#feature-engineering)
  - [Encoding and Scaling](#encoding-and-scaling)
- [Modeling and Evaluation](#modeling-and-evaluation)
  - [Selected Algorithms](#selected-algorithms)
  - [Performance Metrics](#performance-metrics)
  - [Comparison of Models](#comparison-of-models)
- [Conclusion](#conclusion)

---

## Introduction
This project aims to develop a high-performance machine learning model to predict water potability using complex and imbalanced datasets. The primary objectives include handling missing and outlier values, applying data balancing, feature engineering, dimensionality reduction, and hyperparameter optimization. Performance metrics such as accuracy, precision, recall, F1-score, and ROC-AUC are used to evaluate and compare models.

---

## Dataset Description

### Overview of the Dataset
The **Water Potability** dataset from Kaggle is used in this project. The dataset evaluates the potability of water based on various chemical and physical properties.

- **Total Observations:** 3276
- **Number of Features:** 10 (9 independent variables, 1 target variable)
- **Target Variable:** Potability (0: Not Potable, 1: Potable)

### Dataset Variables
- **ph (float):** The pH level of water.
- **Hardness (float):** The hardness of water.
- **Solids (float):** Total dissolved solids in water.
- **Chloramines (float):** Chloramine levels in water.
- **Sulfate (float):** Sulfate concentration in water.
- **Conductivity (float):** Water conductivity.
- **Organic_carbon (float):** Organic carbon concentration.
- **Trihalomethanes (float):** Trihalomethane concentration.
- **Turbidity (float):** Turbidity level of water.

---

## Data Preprocessing

### Handling Missing Values
- **Missing Data:**
  - ph: 491 missing values
  - Sulfate: 781 missing values
  - Trihalomethanes: 162 missing values
- **Solution:** Missing values were filled using the mean of each feature.

### Handling Outliers
Outliers were identified and adjusted using interquartile range (IQR) limits to maintain the dataset's stability.

### Feature Engineering
New features were engineered based on domain-specific insights:
- **PH_CAT:** Categorical variable indicating acidic, neutral, or basic pH levels.
- **OKE_CAT:** Organic Pollution Index combining organic_carbon, trihalomethanes, and chloramines.
- **MDE_CAT:** Mineral Balance Index derived from hardness and sulfate levels.

### Encoding and Scaling
- **Encoding:** One-hot encoding was applied to categorical features.
- **Scaling:** Features were normalized ([0,1]) and standardized (mean=0, std=1) to enhance model performance.

---

## Modeling and Evaluation

### Selected Algorithms
1. **K-Nearest Neighbors (KNN)**
2. **Support Vector Machine (SVM)**
3. **Random Forest (RF)**
4. **XGBoost**

### Performance Metrics
- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC

### Comparison of Models
- **XGBoost:** Achieved the highest performance across all metrics, excelling in imbalanced datasets.
- **Random Forest:** Showed balanced and consistent results, performing well in various scenarios.
- **SVM:** Moderate performance, particularly effective with balanced data.
- **KNN:** Limited performance on high-dimensional and imbalanced datasets.

---

## Conclusion
XGBoost was the most successful model, demonstrating superior performance in all metrics, especially with balanced datasets. Random Forest provided a strong alternative with its robust ensemble structure. Data preprocessing steps like normalization, standardization, and dimensionality reduction (t-SNE) significantly improved model accuracy and generalization.


