# AI vs Human Review Classification
**Comparative Analysis of Machine Learning and Transformer Models for NLP Text Classification**

---

## 1. Project Overview

Online marketplace reviews strongly influence consumer trust and purchasing behavior.
With the rapid advancement of Large Language Models (LLMs), generating highly fluent
and persuasive **fake reviews** has become trivial, making manual or heuristic detection
ineffective.

This project presents an **in-depth comparative study** of:
- Classical Machine Learning models
- GPU-accelerated ML using RAPIDS AI
- Deep Learning transformer-based models

for the task of **classifying reviews as AI-generated or human-written**.

---

## 2. Problem Statement

AI-generated reviews are increasingly:
- Grammatically correct
- Semantically coherent
- Emotionally neutral

This makes them difficult to distinguish from genuine human reviews.

### Objective
To systematically evaluate **accuracy, execution time, and memory usage** of different
ML and DL approaches and identify the most effective models for large-scale deployment.

---

## 3. Dataset Description

A **self-created dataset** was used, consisting of approximately **54,700 reviews**.

| Dataset Property | Value |
|------------------|------|
| Total reviews | 54,700 |
| Human-written reviews | 31,678 |
| AI-generated reviews | 23,022 |
| Maximum review length | 8,166 words |
| Minimum review length | 3 words |
| Average word count | ~74 |

- Human reviews were collected via **web scraping**
- AI reviews were generated using **ChatGPT-3.5**
- Labels: `human` and `AI`

---

## 4. Methodology

### 4.1 Text Preprocessing
- Lowercasing
- Tokenization
- Stopword removal
- Lemmatization

### 4.2 Feature Extraction (ML Models)
- **TF-IDF vectorization**
- Polarity-based auxiliary features

---

## 5. Machine Learning Models (scikit-learn – CPU)

The following models were evaluated:

- Logistic Regression
- Naïve Bayes
- Decision Tree
- Random Forest
- KNN
- Gradient Boosting
- AdaBoost
- XGBoost
- MLP
- SVM

### Key Results (scikit-learn)

| Model | Accuracy |
|-----|---------|
| Decision Tree | **97.43%** |
| SVM | **98.64%** |
| MLP | **98.70%** |
| Random Forest | 98.48% |

Decision Trees and SVM demonstrated an excellent balance between accuracy and efficiency.

---

## 6. GPU-Accelerated ML (RAPIDS AI)

The same ML models were evaluated using **RAPIDS AI (cuML)** on GPU.

### Key Results (RAPIDS AI)

| Model | Accuracy |
|-----|---------|
| SVM | **96.99%** |
| Logistic Regression | 96.72% |
| Random Forest | 94.42% |

RAPIDS AI significantly reduced execution time while maintaining competitive accuracy.

---

## 7. Deep Learning & Transformer Models

Transformer and neural models evaluated:

- 1D-CNN
- LSTM
- BERT
- GPT-2

### DL Results Summary

| Model | Accuracy |
|------|---------|
| GPT-2 | **97.50%** |
| LSTM | 96.88% |
| BERT | 96.78% |
| 1D-CNN | 94.87% |

GPT-2 achieved the **highest accuracy**, but with higher computational cost.

---

## 8. Comparative Analysis

Key observations:

- Classical ML models remain **highly competitive** for text classification
- SVM performs consistently well across CPU and GPU
- Transformer models capture deeper semantic patterns
- Trade-offs exist between **accuracy, execution time, and memory usage**

Model choice should be driven by **deployment constraints** and scale requirements.

---

## 9. Limitations

- Dataset limited to English-language reviews
- AI reviews generated from a single LLM version
- Transformer models require substantial compute
- Rapid evolution of LLMs may reduce model generalization over time

---

## 10. Production Considerations

- Continuous dataset refresh to track AI writing evolution
- Drift monitoring for language style changes
- Balanced false-positive control to protect genuine users
- Ethical deployment in trust & safety pipelines

---

## 11. Project Type

**NLP Research & Comparative Analysis Project (Mentored)**  
Text Classification | Trust & Safety | ML Systems

---

## 12. Mentorship

**Dr. Arun Singh Pundir**  
Assistant Professor, CSE  
NLP • Generative AI • ML Infrastructure

---


