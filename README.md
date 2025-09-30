# 🩺 Heart Disease Prediction Project

## Overview
This project focuses on developing and evaluating various machine learning models to predict the presence of heart disease using clinical data. The goal was to identify the most performant model for accurate and reliable prediction.

## 💾 Dataset
* [cite_start]**Source:** UCI Machine Learning Repository (Heart Disease Dataset) [cite: 1]
* [cite_start]**Features:** The analysis utilized **13 original features** along with **one-hot encoded categorical features**, resulting in a **final feature count of 18**[cite: 1].

## 💻 Models Evaluated
The following supervised machine learning algorithms were trained and evaluated on the dataset:
1.  [cite_start]**Logistic Regression** [cite: 1]
2.  [cite_start]**Decision Tree** [cite: 1]
3.  [cite_start]**Random Forest** [cite: 1]
4.  [cite_start]**Support Vector Machine (SVM)** [cite: 1]

## 🛠 Preprocessing and Setup
* [cite_start]**Feature Encoding:** Nominal features were encoded using **OneHotEncoder**[cite: 7].
* [cite_start]**Feature Scaling:** Scaling was applied specifically for **Logistic Regression** and **SVM** models, but was not needed for the tree-based models (Decision Tree and Random Forest)[cite: 7].
* [cite_start]**Reproducibility:** A complete pipeline (including preprocessing and the final model) was saved to ensure the results are reproducible[cite: 8].

---

## ⭐ Best Performing Model
[cite_start]The **Random Forest Classifier** was identified as the best overall model[cite: 1]. [cite_start]It achieved the highest performance across several key metrics, including Accuracy, Recall, and F1-Score[cite: 5].

### Best Model Parameters (Random Forest)
The model was fine-tuned with the following hyper-parameters:
* [cite_start]`n_estimators` = 100 [cite: 1]
* [cite_start]`max_depth` = 8 [cite: 1]
* [cite_start]`min_samples_split` = 2 [cite: 1]
* [cite_start]`min_samples_leaf` = 2 [cite: 1]
* [cite_start]`max_features` = "log2" [cite: 1]
* [cite_start]`bootstrap` = False [cite: 1]
* [cite_start]`random_state` = 42 [cite: 1]

---

## 📈 Evaluation Metrics (Test Set)

| Model | Accuracy | Precision | Recall | F1-Score | AUC |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Random Forest** | **0.93** | **0.90** | **0.96** | **0.93** | **0.96** |
| SVM | 0.92 | 0.87 | 0.96 | 0.92 | 0.93 |
| Logistic Regression | 0.90 | 0.87 | 0.93 | 0.90 | 0.96 |
| Decision Tree | 0.85 | 0.85 | 0.82 | 0.84 | 0.88 |

### Key Observations
* [cite_start]**Random Forest** achieved the best overall performance[cite: 5].
* [cite_start]**Logistic Regression** also performed strongly while maintaining an advantage in model interpretability[cite: 5].
* [cite_start]**SVM** delivered a high **Recall** score ($\approx 0.96$) [cite: 2, 3][cite_start], which is valuable for applications where minimizing **False Negatives** (failing to detect disease) is critical[cite: 6].
* [cite_start]**Decision Tree** had the weakest performance among the models evaluated, though it remains highly interpretable[cite: 6].

---

## 🎯 Confusion Matrix (Random Forest)
The confusion matrix for the Random Forest Classifier on the test set is as follows:

| | Predicted Negative | Predicted Positive |
| :--- | :--- | :--- |
| **Actual Negative** | 30 (True Negatives) | [cite_start]3 (False Positives) [cite: 4] |
| **Actual Positive** | 1 (False Negative) | [cite_start]27 (True Positives) [cite: 4] |

### Matrix Interpretation
* **True Negatives (30):** Correctly predicted as not having heart disease.
* **False Positives (3):** Incorrectly predicted as having heart disease (Type I Error).
* [cite_start]**False Negative (1):** Incorrectly predicted as not having heart disease (Type II Error)[cite: 4].
* **True Positives (27):** Correctly predicted as having heart disease.
