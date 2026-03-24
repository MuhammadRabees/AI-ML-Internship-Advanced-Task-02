# AI-ML-Internship-Advanced-Task-02

# End-to-End ML Pipeline for Customer Churn Prediction

## Objective of the Task
[cite_start]The objective of this project is to build a reusable, production-ready machine learning pipeline that predicts telecom customer churn[cite: 26]. [cite_start]This project is part of the AI/ML Engineering Advanced Internship at DevelopersHub Corporation[cite: 5].

## Methodology / Approach
[cite_start]This project focuses on creating a robust, leak-proof workflow using Scikit-Learn's `Pipeline` API[cite: 24]:
* [cite_start]**Dataset:** Utilized the standard Telco Customer Churn Dataset[cite: 28].
* [cite_start]**Data Preprocessing:** Implemented a `ColumnTransformer` to handle different data types simultaneously[cite: 29]. 
  * [cite_start]*Numerical Features:* Missing values were imputed using the median, followed by standard scaling[cite: 29].
  * [cite_start]*Categorical Features:* Missing values were filled with a constant, followed by One-Hot Encoding[cite: 29].
* [cite_start]**Model Training & Tuning:** Integrated a `RandomForestClassifier` into the pipeline[cite: 30]. [cite_start]`GridSearchCV` was then applied across the entire pipeline to find the optimal hyperparameters (number of estimators and max depth) using 3-fold cross-validation[cite: 31].
* [cite_start]**Model Export:** The final, best-performing pipeline was serialized and exported as a `.joblib` file for immediate production deployment[cite: 32].

## Key Results or Observations
* **Model Performance:** The optimized Random Forest pipeline achieved a solid **Test Accuracy of ~79%**. 
* **Observations:** The model performs exceptionally well at identifying customers who will *not* churn (Class 0), with high precision and recall. Identifying actual churners (Class 1) is slightly more challenging, which is standard for imbalanced real-world churn datasets.
* **Production Readiness:** Because the scaling, encoding, and imputation steps are baked directly into the `.joblib` pipeline, new raw customer data can be fed directly into the exported model without requiring separate preprocessing scripts.
