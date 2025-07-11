
# Diabetic Patient Readmission Prediction

**Dataset:** UC Irvine Machine Learning Repository — [Diabetes 130-US Hospitals](https://doi.org/10.24432/C5230J)

## Objective

This project aims to develop machine learning models that predict 30-day hospital readmissions among diabetic patients. The models identify key clinical features that contribute to readmission risk, enabling early interventions and improved discharge planning.

## Background

Diabetes is a leading cause of hospital readmissions in the United States. In 2018, over 30% of readmissions were related to diabetes, with average hospital stays of 4.66 days and costs exceeding $12.8 billion annually. Accurately predicting readmissions is essential for reducing healthcare costs and improving patient outcomes.

## Data Overview

- **Source:** UC Irvine Machine Learning Repository  
- **Dataset:** 101,766 encounters from 130 hospitals (1999–2008)  
- **Features:** 47 clinical and demographic variables  
- **Target:** Binary classification — readmitted within 30 days vs. not readmitted

### Limitations

- Missing values in key features (e.g., race, weight, payer code)
- Imbalanced target variable: only 11% were readmitted within 30 days

## Data Preprocessing

- Removed non-informative ID columns
- Dropped columns with >95% missing data
- Encoded categorical variables and standardized numeric features
- Feature importance analysis confirmed the low predictive value of dropped columns

### Feature Importance

Key predictors:
- Number of medications
- Diagnosis codes (primary, secondary, tertiary)
- Time in hospital
- Number of lab procedures

*(Add feature importance plot here, e.g., `visuals/feature_importance.png`)*

## Class Imbalance

The dataset had significant class imbalance. SMOTE was tested but led to overfitting. Final models were trained on the original, imbalanced data to maintain real-world relevance.

## Modeling Approach

### Models Tested

- Logistic Regression
- K-Nearest Neighbors (KNN)
- Support Vector Machine (SVM)
- Random Forest
- XGBoost (with and without SMOTE)

### Evaluation

- **Train/Test Split:** 70/30
- **Cross-validation:** 5-fold
- **Metrics:** Accuracy, Recall, F1-score
- **Primary metric:** Recall (sensitivity to 30-day readmissions)

## Results

| Model              | Accuracy | Recall | F1-Score |
|--------------------|----------|--------|----------|
| Logistic Regression | 0.42     | Low    | 0.25     |
| SVM                 | 0.57     | Low    | 0.51     |
| XGBoost + SMOTE     | 0.59     | 0.40   | 0.42     |
| Random Forest       | 0.56     | 0.56   | 0.44     |

Random Forest achieved the best balance between recall and F1-score without overfitting. It handled complex relationships and variable importance effectively.

### Visualizations

<img width="800" height="600" alt="Screenshot 2025-07-11 at 11 52 53 AM" src="https://github.com/user-attachments/assets/7ea56a03-647b-4906-a49b-f9480fb6971c" />


<img width="803" height="488" alt="Screenshot 2025-07-11 at 11 54 38 AM" src="https://github.com/user-attachments/assets/1c788bd4-63d3-4c98-9da0-6db3544eb136" />

## Discussion

### Insights

- Clinical variables were more predictive than demographic features
- Random Forest provided the best performance on imbalanced data
- Number of medications and time in hospital were consistent indicators of readmission risk

### Limitations

- Data is outdated and lacks recent treatment patterns
- Missing social and behavioral health factors
- No temporal modeling of patient history

## Future Work

- Explore alternative ensemble models like LightGBM
- Include social determinants and medication adherence features
- Integrate time-series approaches such as LSTM
- Use updated hospital datasets for current relevance

## References

1. Strack et al., *Impact of HbA1c Measurement on Readmissions* — [Link](https://doi.org/10.1155/2014/781670)  
2. Soh et al., *30-day Readmission Prediction in Diabetes* — [Link](https://doi.org/10.1210/clinem/dgac380)  
3. Marafino et al., *Causal Machine Learning for Readmissions* — [Link](https://doi.org/10.1111/1475-6773.13586)  
4. Burrill, L. — [Baseline Project GitHub](https://github.com/lelandburrill/diabetes)



