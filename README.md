# Tree-Based Classification Model for Predicting User Churn in the Waze App

## Project Overview
The goal of this data analytics project was to identify the key factors driving user churn for the Waze app and ultimately build a predictive model. Two final models were developed: a Random Forest model and an XGBoost model. Ultimately, both models did not perform well enough for practical application. The final XGBoost model achieved an accuracy of 70% and a recall of 50%, which is critical for this context. Several features showed predictive value, including 'km_per_hour', 'n_days_after_onboarding', and 'percent_sessions_in_last_month'; however, the overall performance suggests that improvements are necessary. Many of the top features identified in the importance rankings were engineered.

## Business Understanding
The key stakeholders for this project are the Waze team, as the insights derived from this analysis will help them re-evaluate various aspects of the app to reduce user churn.

## Data Understanding
The dataset consists of 14999 rows and 13 features, which include various data types such as int64, float64, and object. Prior to model development, data cleaning was performed, which involved handling missing values, duplicates, and zeros, as well as engineering new variables from existing ones. Given the robustness of tree-based models to multicollinearity, features were retained without being dropped based on a correlation heatmap or Variance Inflation Factor (VIF). The outcome variable exhibited moderate imbalance, but this did not necessitate upsampling methods; the model can manage the imbalance through configuration.

## Modeling and Evaluation
Both Random Forest and XGBoost models were developed, with the XGBoost model performing slightly better. However, both models significantly underperformed according to the recall metric. False negatives are particularly problematic in this context, as misclassifying a user who is likely to churn as one who will stay can have serious implications for the company.

### Feature Importances
- activity_days: 0.210597
- n_days_after_onboarding: 0.055661
- driving_days: 0.052251
- device2: 0.050452
- percent_of_sessions_to_favorite: 0.048494
- km_per_hour: 0.047914
- total_navigations_fav1: 0.047816
- km_per_driving_day: 0.047345
- drives: 0.046707
- total_sessions_per_day: 0.046533
- total_sessions: 0.046145
- duration_minutes_drives: 0.045808
- km_per_drive: 0.044167
- total_navigations_fav2: 0.043946

After determining the optimal decision threshold based on the precision-recall curve, the final scoring metrics of the model were slightly improved compared to previous iterations, but they still do not meet the standards required for reliable use in a production environment.

### Model Scoring Metrics
- Accuracy: 0.7041
- Precision: 0.2994
- Recall: 0.4990
- F-score: 0.3742

## Conclusion
The final iteration of this set of models cannot be deployed in a production environment until performance improvements are achieved. It is recommended to explore additional methods for enhancement, such as further parameter tuning, feature selection, additional variable engineering, and gathering more data. The analysis also concluded that the newly engineered variables constituted a significant portion of the features that demonstrated predictive power.
