📊 Data Science Week 2025 Datathon – Physiological State Classification
📍 Overview

This repository contains my work for the Data Science Week 2025 datathon at the University of Twente.

The project focuses on classifying physiological states using engineered features derived from sensor data. The task was to predict four conditions:

baseline
meditation
stress
break

I explored multiple machine learning and deep learning approaches, with a strong focus on model comparison, feature selection, and interpretability.

📂 Repository Structure
├── data/
│   └── final_engineered_data.csv

├── notebooks/
│   ├── data featuring by Yaxing Li.Rmd
│   ├── data modeling by Yaxing Li.Rmd
│   ├── random forest data modeling 2 by Yaxing Li.Rmd
│   ├── XGBoost data modeling 1 by Yaxing Li.Rmd
│   ├── deep learning data modeling 1/2/3 by Yaxing Li.Rmd

├── results/
│   ├── DSW25_rf_model_1.csv
│   ├── DSW25_rf_model_2_feature_selection.csv
│   ├── DSW25_knn_11_model_1.csv
│   ├── DSW25_knn_11_model_without_2_features_2.csv
│   ├── DSW25_XGBOOST_model_with_5_PCA.csv
│   ├── DSW25_XGBOOST_model_without_2_features_1.csv
│   ├── DSW25_CNN_model_with_kfold.csv
│   ├── DSW25_CNN_model_with_val.csv

├── plots/
│   ├── SHAP IMPORTANCE PLOT FOR XGBOOST.png
│   ├── SHAP IMPORTANCE PLOT FOR XGBOOST baseline/break/stress/meditation

└── README.md
⚙️ Data & Preprocessing
Input: final_engineered_data.csv
Contains physiological features (e.g., heart rate, temperature, BVP-derived stats)
Includes:
participant_id (group-based splitting)
chunk_id (time segments)
label (target)
Key preprocessing steps:
Group-based train/validation split (by participant)
Normalization of numeric variables
One-hot encoding for categorical variables
Removal of zero-variance features
KNN imputation (for KNN model)
🤖 Models Implemented
🌲 1. Random Forest
Implemented using tidymodels + ranger
Hyperparameter tuning:
number of trees
mtry
min_n
Feature importance extracted and used for:
Feature selection
Model refinement

📁 Outputs:

DSW25_rf_model_1.csv
DSW25_rf_model_2_feature_selection.csv
🔍 2. K-Nearest Neighbors (KNN)
Tuned number of neighbors (k)
Applied after removing low-impact features:
mean_bvp
skewness_temp

📁 Outputs:

DSW25_knn_11_model_1.csv
DSW25_knn_11_model_without_2_features_2.csv
⚡ 3. XGBoost
Gradient boosting model for improved performance
Two variations:
With PCA (dimensionality reduction)
Without low-importance features
Model interpretability via SHAP values

📁 Outputs:

DSW25_XGBOOST_model_with_5_PCA.csv
DSW25_XGBOOST_model_without_2_features_1.csv

📊 SHAP plots:

Global importance
Class-specific explanations (baseline, stress, meditation, break)
🧠 4. Deep Learning (CNN)
Convolutional Neural Network applied to structured data
Two evaluation strategies:
K-fold cross-validation
Validation split

📁 Outputs:

DSW25_CNN_model_with_kfold.csv
DSW25_CNN_model_with_val.csv
📈 Model Comparison Strategy

Across all models, I focused on:

Validation accuracy
Generalization across participants
Robustness to feature selection

Key idea:

Instead of relying on a single model, I built multiple pipelines and compared their performance systematically.

🔬 Feature Engineering & Selection
Methods used:
Random Forest feature importance
Recursive Feature Elimination (RFE)
SHAP values (for XGBoost)
Key findings:
Some features had negative impact on performance
Removing noisy variables improved generalization
Different models relied on different feature subsets