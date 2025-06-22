# Credit Card Fraud Detection System

This project implements a machine learning pipeline to detect fraudulent credit card transactions and exposes a real-time prediction API using FastAPI.

---

## Project Overview

Credit card fraud is a critical financial threat that affects individuals and institutions worldwide. This project builds a robust fraud detection system using:

- **Data Preprocessing**
- **Handling Class Imbalance**
- **Random Forest Classification**
- **FastAPI Deployment with Real-Time Inference**

---

## Dataset

The dataset used is based on the [Kaggle Credit Card Fraud Detection Dataset](https://www.kaggle.com/mlg-ulb/creditcardfraud).  
It contains anonymized features `V1` to `V28`, as well as `Time`, `Amount`, and the target label `Class`.

---

## Steps Involved

### 1. **Loading and Inspecting the Dataset**
- Examined class distribution: highly imbalanced (0.193% fraud).
- Identified need for resampling techniques.

### 2. **Preprocessing**
- Standardized `Time` and `Amount` features using `StandardScaler`.

### 3. **Data Splitting**
- Dropped missing values.
- Stratified split into train/test sets (80/20).

### 4. **Handling Imbalance**
- Downsampled majority class to match fraudulent samples.

### 5. **Model Training**
- Trained a `RandomForestClassifier` on the balanced data.

### 6. **FastAPI Deployment**
- Final `/predict` endpoint accepts all 30 input features (Time, Amount, V1–V28).
- Model is loaded from `.pkl` file and makes predictions with probability output.

---
