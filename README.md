# CDC Diabetes Risk Prediction Using Machine Learning

## Overview
This project builds and evaluates multiple machine learning models to predict diabetes status using the CDC Behavioral Risk Factor Surveillance System (BRFSS) 2015 dataset. The dataset contains 253,680 survey responses with 21 health, lifestyle, and demographic features.

The primary objective is to assess whether accessible, self-reported survey data can be used as an effective first-line screening tool for identifying individuals at elevated risk of diabetes or prediabetes.

---

## Dataset
- **Source:** CDC BRFSS 2015 Health Indicators  
- **Observations:** 253,680  
- **Features:** 21  
- **Target Variable:** `Diabetes_binary`  
  - 0: No diabetes  
  - 1: Prediabetes or diabetes  

Feature types include:
- Binary health and lifestyle indicators
- Ordinal demographic and socioeconomic variables
- Continuous health measures

---

## Methods
The project follows an end-to-end data science workflow:
1. Exploratory Data Analysis (EDA)
2. Feature categorization and interaction analysis
3. Class imbalance assessment and handling
4. Model training and evaluation
5. Feature importance analysis
6. Model comparison and interpretation

Class imbalance (~14% positive class) is addressed using class weighting and recall-focused evaluation metrics.

---

## Models Implemented
The following supervised learning models were evaluated:
- Logistic Regression
- Decision Tree
- Random Forest
- XGBoost
- Neural Network

Hyperparameter tuning was performed using RandomizedSearchCV for ensemble and boosting models.

---

## Results
- Best-performing model: **XGBoost**
- ROC-AUC: **0.8274**
- Recall for diabetic/prediabetic class: **~79%**

Across models, the most influential predictors were general health status, high blood pressure, BMI, age, and high cholesterol.

---

## Key Findings
- Diabetes risk is strongly associated with both medical conditions and socioeconomic factors
- Income and education interact with age to amplify risk
- Model performance plateaus across algorithms, suggesting feature-limited predictive power
- Feature importance rankings are consistent across model types

---

## Limitations
- Data is self-reported and cross-sectional
- Medical indicators are binary rather than continuous
- Precision-recall trade-offs are inherent due to class imbalance
- Model trained on 2015 data may not reflect current population trends

---

## Future Work
- Incorporate longitudinal or clinical data
- Perform fairness and subgroup analysis
- Explore model explainability methods (e.g., SHAP)
- Optimize deployment thresholds based on screening context
- Retrain models on more recent survey data

---

## Tools and Libraries
Python, Pandas, NumPy, PandaSQL, DuckDB, Scikit-learn, XGBoost, Matplotlib, Seaborn

---

## Acknowledgments
CDC for providing the BRFSS dataset and course instructors for guidance.
