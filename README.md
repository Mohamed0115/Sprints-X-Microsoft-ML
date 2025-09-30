# 🩺 Heart Disease Prediction Project

## Overview
This project focuses on developing and evaluating various machine learning models to predict the presence of heart disease using clinical data. The goal was to identify the most performant model for accurate and reliable prediction.

## 💾 Dataset
* **Source:** UCI Machine Learning Repository (Heart Disease Dataset) 
* **Features:** The analysis utilized **13 original features** along with **one-hot encoded categorical features**, resulting in a **final feature count of 18**.

## 💻 Models Evaluated
The following supervised machine learning algorithms were trained and evaluated on the dataset:
1.  []**Logistic Regression** 
2.  []**Decision Tree** 
3.  []**Random Forest** 
4.  []**Support Vector Machine (SVM)** 

## 🛠 Preprocessing and Setup
* []**Feature Encoding:** Nominal features were encoded using **OneHotEncoder**.
* []**Feature Scaling:** Scaling was applied specifically for **Logistic Regression** and **SVM** models, but was not needed for the tree-based models (Decision Tree and Random Forest).
* []**Reproducibility:** A complete pipeline (including preprocessing and the final model) was saved to ensure the results are reproducible.

---

## ⭐ Best Performing Model
The **Random Forest Classifier** was identified as the best overall model. It achieved the highest performance across several key metrics, including Accuracy, Recall, and F1-Score.

### Best Model Parameters (Random Forest)
The model was fine-tuned with the following hyper-parameters:
* `n_estimators` = 100 
* `max_depth` = 8 
* `min_samples_split` = 2 
* `min_samples_leaf` = 2 
* `max_features` = "log2" 
* `bootstrap` = False 
* [`random_state` = 42 

---

## 📈 Evaluation Metrics (Test Set)

| Model | Accuracy | Precision | Recall | F1-Score | AUC |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Random Forest** | **0.93** | **0.90** | **0.96** | **0.93** | **0.96** |
| SVM | 0.92 | 0.87 | 0.96 | 0.92 | 0.93 |
| Logistic Regression | 0.90 | 0.87 | 0.93 | 0.90 | 0.96 |
| Decision Tree | 0.85 | 0.85 | 0.82 | 0.84 | 0.88 |

### Key Observations
* **Random Forest** achieved the best overall performance.
* **Logistic Regression** also performed strongly while maintaining an advantage in model interpretability.
* **SVM** delivered a high **Recall** score ($\approx 0.96$) [cite: 2, 3][cite_start], which is valuable for applications where minimizing **False Negatives** (failing to detect disease) is critical.
* **Decision Tree** had the weakest performance among the models evaluated, though it remains highly interpretable.

---

## 🎯 Confusion Matrix (Random Forest)
The confusion matrix for the Random Forest Classifier on the test set is as follows:

| | Predicted Negative | Predicted Positive |
| :--- | :--- | :--- |
| **Actual Negative** | 30 (True Negatives) | [cite_start]3 (False Positives)  |
| **Actual Positive** | 1 (False Negative) | [cite_start]27 (True Positives)  |

### Matrix Interpretation
* **True Negatives (30):** Correctly predicted as not having heart disease.
* **False Positives (3):** Incorrectly predicted as having heart disease (Type I Error).
* **False Negative (1):** Incorrectly predicted as not having heart disease (Type II Error).
* **True Positives (27):** Correctly predicted as having heart disease.
