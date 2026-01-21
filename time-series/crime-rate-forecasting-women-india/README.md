# Time Series Forecasting of Crime Rates Against Women in India
**Comparative Analysis using Machine Learning, Deep Learning, and Transformer Models**

---

## 1. Project Context & Motivation

Crimes against women remain a critical societal challenge in India, requiring
**proactive, data-driven interventions** rather than reactive enforcement alone.
Historical crime data exhibits strong **temporal patterns**, **regional disparities**,
and **non-linear trends**, making it suitable for advanced **time-series forecasting**.

This project applies **classical machine learning and deep learning time-series models**
to forecast future crime rates, enabling **early warnings, resource planning, and
preventive policy decisions**.

This work is based on a **mentored academic research study** conducted at  
**Thapar Institute of Engineering & Technology**.

---

## 2. Problem Definition

**Task:**  
Forecast district-wise crime rates against women using historical time-series data.

**Goal:**  
Identify the most reliable forecasting models under real-world constraints such as:
- Non-stationarity
- Seasonality
- Noisy observations
- Limited temporal depth

---

## 3. Dataset Description

- **Source:** Government Open Data Portal (*data.gov.in*)
- **Time Span:** 2001 – 2015
- **Granularity:** District-level
- **Size:** 10,677 records × 11 features

### Key Features
- State / Union Territory  
- District  
- Year  
- Crime categories:
  - Rape
  - Kidnapping & Abduction
  - Dowry Deaths
  - Assault on Women
  - Cruelty by Husband/Relatives
  - Insult to Modesty
  - Importation of Girls

---

## 4. Data Preprocessing & Time-Series Engineering

- Temporal ordering enforced (no random shuffling)
- Missing values handled using:
  - Forward filling
  - Mean imputation (where applicable)
- Date conversion using `to_datetime`
- Year-based indexing for forecasting
- Seasonal trend inspection and differencing
- Feature normalization for ML/DL models

**Strict time-aware train–test split applied**  
(Training up to 2014, evaluation on 2015)

---

## 5. Models Implemented

A **comparative evaluation of eight models** was performed:

### Classical Machine Learning
- Random Forest
- Gradient Boosting
- XGBoost

### Deep Learning Models
- Deep Neural Network (DNN)
- Recurrent Neural Network (RNN)
- LSTM
- GRU
- Transformer

This enables evaluation across **accuracy, generalization, and computational cost**.

---

## 6. Evaluation Metrics

- **RMSE (Root Mean Squared Error)**
- **R² Score**
- CPU execution time

These metrics reflect both **prediction quality** and **deployment feasibility**.

---

## 7. Results Summary

### Model Accuracy Comparison

| Model | RMSE | R² Score |
|------|------|---------|
| XGBoost | **245.98** | **0.981** |
| Gradient Boost | 191.42 | 0.97 |
| Transformer | **220.16** | **0.97** |
| Random Forest | 311.94 | 0.96 |
| GRU | 1758.36 | 0.046 |
| RNN | 1789.74 | 0.012 |
| LSTM | 1792.31 | 0.009 |
| DNN | 2012.98 | −0.062 |

### Key Observations
- **Tree-based models and Transformers outperform LSTM/RNN**
- Deep sequential models struggled due to limited temporal depth and noise
- XGBoost shows the **best accuracy–efficiency trade-off**

---

## 8. Computational Cost (CPU Time)

| Model | CPU Time (s) |
|-----|--------------|
| XGBoost | 8.77 |
| Transformer | 8.85 |
| Gradient Boost | 13.60 |
| DNN | 5.80 |
| LSTM | 144.88 |
| RNN | 143.94 |
| Random Forest | 160.58 |

---

## 9. Forecasting Results (2015)

Using **XGBoost**, the best-performing model:

- **Lowest predicted crime rate:**  
  Papum Pare Rural → **7.94 crimes / 100,000**

- **Highest predicted crime rate:**  
  Mumbai Commissionerate → **4730.30 crimes / 100,000**

District-level forecasts closely matched observed values, validating real-world usability.

---

## 10. Model Behavior Analysis

- XGBoost & Gradient Boost:
  - Stable convergence
  - Strong generalization
- Random Forest & DNN:
  - Overfitting observed
- LSTM & GRU:
  - Partial learning
  - Require longer sequences and stronger regularization

---

## 11. Limitations

- External socio-economic variables not explicitly modeled
- Reporting bias may affect accuracy
- Deep learning models need richer temporal signals
- Forecasts should assist—not replace—policy decisions

---

## 12. Deployment & Monitoring Considerations

- Periodic retraining due to data drift
- Continuous RMSE monitoring
- District-wise confidence intervals recommended
- Ethical safeguards for sensitive predictions

---

## 13. Project Classification

**Student Research Project (Mentored)**  
Time Series Forecasting | Machine Learning | Deep Learning

---

## 14. Academic Supervision

**Dr. Arun Singh Pundir**  
Assistant Professor, CSE  
Time Series Analysis | ML Systems | Responsible AI

---


