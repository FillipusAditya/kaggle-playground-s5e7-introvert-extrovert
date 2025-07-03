# Kaggle Playground Series S5E7 — Predict Introverts vs Extroverts

[![Kaggle](https://img.shields.io/badge/Kaggle-Playground%20Series%20S5E7-blue)](https://www.kaggle.com/competitions/playground-series-s5e7)

---

## 📌 Competition Overview

Welcome to the Kaggle **Playground Series - Season 5, Episode 7**!  
In this competition, the goal is to **predict whether a person is an Introvert or Extrovert**, based on their **social behavior** and **personality traits**.

- **Target:** `Personality` (`Introvert` or `Extrovert`)
- **Data:** Synthetic dataset generated from real-world behavioral patterns
- **Evaluation Metric:** Accuracy Score

📅 **Competition timeline:**  
- Start: June 30, 2025  
- End: July 31, 2025  

---

## ⚙️ My Solution Workflow

This repository contains my complete pipeline from **EDA** to **submission**, implemented in a single notebook using:

- 📊 Exploratory Data Analysis (EDA)
- 🔍 Missing value handling with `IterativeImputer`
- ⚙️ Label Encoding for categorical features
- 🔄 Box-Cox transformation to reduce skewness
- 🔧 Hyperparameter tuning using **Optuna**
- 🧩 Ensemble learning with **Random Forest, AdaBoost, CatBoost, LightGBM, XGBoost**
- 🏆 **StackingClassifier** as final ensemble
- 📈 Cross-validation with **RepeatedStratifiedKFold**

---

## 🗂️ Features Used

| Feature | Description |
|--------------------------|-----------------------------------------------|
| `Time_spent_Alone`       | Time an individual spends alone |
| `Stage_fear`             | Encoded stage fear level |
| `Social_event_attendance`| Frequency of attending social events |
| `Going_outside`          | Frequency of going outside |
| `Drained_after_socializing` | Encoded feeling after socializing |
| `Friends_circle_size`    | Size of friend circle |
| `Post_frequency`         | Frequency of posting on social media |

---

## 📊 Hyperparameter Tuning

Each base model was optimized with **Optuna** for best `accuracy`:
- `RandomForestClassifier`
- `AdaBoostClassifier`
- `CatBoostClassifier`
- `LightGBMClassifier`
- `XGBoostClassifier`

Cross-validation:  
> 10-fold Repeated Stratified CV

---

## 🔗 Final Stacking Ensemble

Base Learners:
- Random Forest
- AdaBoost
- CatBoost
- LightGBM
- XGBoost

Meta Learner:
- Logistic Regression

---

## ✅ Results

| Model         | CV Accuracy (Mean ± Std) |
|---------------|--------------------------|
| Random Forest | 0.969 ± 0.003 |
| AdaBoost      | 0.969 ± 0.003 |
| CatBoost      | 0.969 ± 0.003 |
| LightGBM      | 0.969 ± 0.003 |
| XGBoost       | 0.969 ± 0.003 |
| **Stacking**  | **0.969 ± 0.003** |

**Final Submission Accuracy on Public LB:** `0.975708`

---

## 📝 Submission Format

The final prediction was saved as `submission.csv` with format:
