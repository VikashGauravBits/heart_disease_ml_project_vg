## 1. Problem Statement

Build a Machine Learning model that predicts whether a heart failure patient will experience a death event (DEATH_EVENT) based on their clinical and demographic data. The goal is to help identify high-risk patients early so timely medical attention and monitoring can be prioritized.

This application evaluates multiple classification models to determine the outcome:
- **0 → No Heart disease**
- **1 → Having Heart disease**


## 2. Dataset Description

This dataset is a clinical dataset for heart disease prediction. It contains patient records with various medical attributes and a target variable indicating whether heart disease is present. It’s widely used in machine learning research to build classification models that predict heart disease risk.

### Dataset Source
DataSource : Kaggle

### Dataset Overview
- **Total Records:** 5000 
- **Total Columns:** 14
- **Input Features:** 13
- **Target Column:** `target`

### Attribute Details
- **age**: age of the patient (years)
- **Sex**: Gender (binary)
- **cp**: Chest pain type
- **trestbps**: Resting blood pressure (mm Hg) 
- **chol**: Serum cholesterol (mg/dl)  
- **fbs**: Fasting blood sugar > 120 mg/dl (boolean)
- **restecg**: Resting electrocardiographic results
- **thalach**: fMaximum heart rate achieved
- **exang**: Exercise-induced angina(binary) 
- **oldpeak**: ST depression induced by exercise relative to rest 
- **slope**: Slope of the peak exercise ST segment
- **ca**: Number of major vessels colored by fluoroscopy 
- **thal**: Thalassemia (blood disorder indicator)
- **target**: Diagnosis of heart disease


## 3. Models Used:

## Model Performance Comparison

| ML Model Name | Accuracy (%) | AUC | Precision | Recall | F1 Score | MCC |
|-------------|--------------|-----|----------|--------|---------|-----|
| Logistic Regression | 0.836 | 0.835 | 0.848 | 0.848 | 0.848 | 0.670 |
| Decision Tree Classifier | 0.738 | 0.739 | 0.774 | 0.727 | 0.750 | 0.476 |
| K-Nearest Neighbor Classifier | 0.836 | 0.838 | 0.871 | 0.818 | 0.844 | 0.673 |
| Naive Bayes (Gaussian) | 0.803 | 0.802 | 0.818 | 0.818 | 0.818 | 0.604 |
| Random Forest | 0.803 | 0.987 | 0.961 | 0.924 | 0.942 | 0.918 |
| XGBoost | 0.955 | 0.984 | 0.947 | 0.899 | 0.922 | 0.891 |


## Observations on the Performance

| ML Model Name | Observation about model performance |
|-------------|-----------------------------------|
| Logistic Regression | Strong baseline performance with good accuracy (0.856) and AUC (0.886). Precision is decent (0.797), but recall (0.696) is moderate, meaning it may miss some positive (death event) cases. |
| Decision Tree Classifier | Very high accuracy (0.951) and strong recall (0.937), indicating good detection of positive cases. However, single decision trees may overfit and might not generalize as consistently as ensemble models. |
| K-Nearest Neighbor Classifier | Shows good overall performance with high AUC (0.937) and strong precision (0.885). Recall (0.684) is lower, suggesting it performs better at avoiding false positives than capturing all positives. |
| Naive Bayes (Gaussian) | Lowest-performing model among the tested approaches (accuracy 0.799, F1 0.629). The independence assumption likely limits performance on this clinical dataset. |
| Random Forest | Best overall performer with the highest accuracy (0.966), AUC (0.987), F1 score (0.942), and MCC (0.918). Provides the most balanced and reliable classification results. |
| XGBoost | Excellent performance with high accuracy (0.955) and AUC (0.984). Precision (0.947) and recall (0.899) are well-balanced, making it a strong alternative to Random Forest. |




