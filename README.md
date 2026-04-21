# Responsible ML – Homework 4  
Explaining the COMPAS Replacement Model

## Files
- `L4_Jessie_Hsu_ASSN4.ipynb`: Full analysis and code

## Overview

This project evaluates a predictive model built on the COMPAS dataset through a series of Responsible Machine Learning analyses. The goal is not only to assess predictive performance, but also to understand how the model behaves under different conditions, how stable it is, and whether its behavior is consistent across different groups.

Rather than focusing on a single metric, this analysis examines the model from multiple perspectives, including generalization, feature influence, robustness, and slice-based performance.

---

## Model and Setup

The analysis is based on a classification model trained to predict two-year recidivism.

Key components:
- Model: Logistic Regression
- Features include demographic and criminal history variables (e.g., priors_count, age, sex, race)
- Evaluation metrics: Accuracy, AUC, Log Loss, Brier Score

All experiments are conducted using the same base pipeline to ensure consistency across different analyses.

---

## Analysis Structure

The notebook is organized into five main parts:

### Part A – Distribution Drift
Examines whether the training and test data differ significantly.  
This helps determine whether performance metrics are evaluated under comparable conditions.

### Part B – Generalization
Compares model performance between training and test sets.  
A small gap indicates that the model generalizes well and is not overfitting.

### Part C – Counterfactual Analysis
Tests how predictions change when specific features are altered (e.g., flipping sex or race).  
This helps identify whether the model is sensitive to certain attributes.

### Part D – Robustness
Evaluates how stable the model is under input perturbations.  
This includes testing both small and larger changes to key features.

### Part E – Slice-Based Evaluation
Analyzes model performance across different demographic groups.  
This reveals whether the model behaves consistently across populations.

---

## Key Findings

Several consistent patterns emerge across the analyses:

- The model generalizes well, with only a small gap between training and test performance  
- Predictions are strongly influenced by a small number of features, especially priors_count  
- The model is stable under small input changes, but more sensitive under larger perturbations  
- Performance varies across groups, particularly for race and age  
- Some results are based on low-support groups and should be interpreted cautiously  

---

## Recommended Actions

Based on the findings, the following steps are recommended before deployment:

- Monitor key features (e.g., priors_count) due to their strong influence on predictions  
- Track model performance across demographic groups rather than relying on aggregate metrics  
- Investigate low-support groups separately to avoid misleading conclusions  
- Test model behavior under larger input changes to better understand potential instability  

These steps would help improve both the reliability and transparency of the model.

---

## Notes

- All analyses are implemented in the notebook using a consistent pipeline  
- Results should be interpreted in context, especially when sample sizes are small  
- This project focuses on model behavior rather than optimizing performance
