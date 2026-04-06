# 📊 Data Science Week 2025 Datathon – Physiological State Classification
## 📍 Overview

This repository contains my work for the Data Science Week 2025 datathon at the University of Twente.

The project focuses on classifying physiological states using engineered features derived from sensor data. The task was to predict four conditions:

- baseline 
- meditation
- stress
- break

I explored multiple machine learning and deep learning approaches, with a strong focus on model comparison, feature selection, and interpretability.

## Main work

Across all models, I focused on:

Validation accuracy
Generalization across participants
Robustness to feature selection

## Key idea

Instead of relying on a single model, I built multiple pipelines and compared their performance systematically.

🔬 Feature Engineering & Selection
Methods used:
- Random Forest feature importance
- Recursive Feature Elimination (RFE)
- SHAP values (for XGBoost)

## Key findings:
Some features had negative impact on performance
Removing noisy variables improved generalization
Different models relied on different feature subsets
