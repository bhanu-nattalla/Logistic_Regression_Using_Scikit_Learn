# Framingham Heart Study: Heart Disease Risk Analysis

Identifying key risk factors for ten-year heart disease risk using the Framingham Heart Study dataset, with a Logistic Regression model built for both interpretation and prediction.

---

## Table of Contents

- [Framingham Heart Study: Heart Disease Risk Analysis](#framingham-heart-study-heart-disease-risk-analysis)
  - [Table of Contents](#table-of-contents)
  - [1. Project Overview](#1-project-overview)
  - [2. Data Understanding \& Quality Assessment](#2-data-understanding--quality-assessment)
  - [3. Data Cleaning \& Preprocessing](#3-data-cleaning--preprocessing)
  - [4. Exploratory Data Analysis (EDA)](#4-exploratory-data-analysis-eda)
  - [5. Statistical Analysis](#5-statistical-analysis)
  - [6. Logistic Regression \& Model Interpretation](#6-logistic-regression--model-interpretation)
  - [7. Feature Selection](#7-feature-selection)
  - [8. Model Training \& Evaluation](#8-model-training--evaluation)
  - [9. Conclusion](#9-conclusion)

---

## 1. Project Overview

This project analyzes the Framingham Heart Study dataset to identify key risk factors associated with the likelihood of developing heart disease within ten years. A Logistic Regression model was built to both interpret the impact of medical features and predict heart disease risk.

## 2. Data Understanding & Quality Assessment

The dataset was examined for structure, data types, missing values, and overall quality.

- No duplicate records were found.
- Several medical variables contained missing values:
  - Cholesterol
  - Glucose
  - Heart rate
  - Body mass index (BMI)
  - Cigarettes per day

## 3. Data Cleaning & Preprocessing

| Feature Type | Method |
|---|---|
| Continuous medical variables | Imputed with the **mean** |
| Categorical variables | Imputed with the **most frequent value** |
| Cigarettes per day | Imputed with **gender-based averages** to preserve behavioral differences |
| Education | **Removed** due to limited medical relevance |

After preprocessing, the dataset was complete and ready for modeling.

## 4. Exploratory Data Analysis (EDA)

Clear differences emerged between individuals who developed heart disease and those who did not. Patients with heart disease tended to have:

- Higher average age
- Higher blood pressure
- Higher cholesterol
- Higher cigarette consumption
- Higher heart rate

Gender-based comparisons also showed differences in heart disease prevalence, highlighting the importance of demographic factors.

## 5. Statistical Analysis

Statistical tests were used to validate the observed relationships:

- **Chi-square test:** strong univariate association between diabetes and heart disease.
- **T-test:** statistically significant difference in average heart rate between affected and unaffected individuals.

These results supported the initial EDA findings.

## 6. Logistic Regression & Model Interpretation

Logistic Regression was used to assess the independent effect of each feature while controlling for the others.

- Some variables that appeared significant in univariate analysis **lost significance** in the multivariate model.
- This was due to **multicollinearity**, where multiple features carry overlapping medical information.

## 7. Feature Selection

Selection was guided by statistical significance, medical reasoning, and redundancy reduction.

- Features that added no independent information were removed.
- Example: **diabetes** was excluded because it is a general diagnosis, while **glucose** gives a more precise, continuous measure of blood sugar.
- This improved model interpretability and stability.

## 8. Model Training & Evaluation

The data was split into training and testing sets for unbiased evaluation.

**Metrics used**

- **Accuracy:** overall performance
- **Confusion matrix:** analysis of prediction errors
- **Precision, Recall, F1-score:** class-level performance

> Given the medical context, special emphasis was placed on **Recall** for heart disease cases to minimize missed diagnoses.

## 9. Conclusion

Age, blood pressure, glucose level, cholesterol, and smoking behavior significantly influence heart disease risk. The project demonstrates the importance of distinguishing between simple statistical associations and independent predictors in multivariate models.

The final Logistic Regression model balances predictive performance with interpretability, making it suitable for both analytical insight and practical risk assessment.