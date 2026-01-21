# Detecting Fake AI-Generated Marketplace Reviews using LLMs and RAPIDS AI

---

## 1. Project Motivation

Online marketplace reviews significantly influence consumer trust and purchasing
decisions. With the rise of Large Language Models (LLMs), it has become increasingly
easy to generate **synthetic reviews** that closely mimic human-written content,
posing a serious threat to platform integrity.

This project addresses the challenge of **distinguishing AI-generated reviews from
human-authored reviews** using a combination of:

- Classical Machine Learning
- Transformer-based Deep Learning models
- GPU-accelerated RAPIDS AI frameworks

---

## 2. Problem Statement

The primary challenge lies in identifying subtle linguistic, structural, and
statistical differences between:

- Human-written reviews
- AI-generated reviews produced by modern LLMs (ChatGPT-3.5)

Traditional rule-based and shallow classifiers are insufficient due to:
- High linguistic fluency of AI text
- Reduced lexical anomalies
- Neutral sentiment bias in AI-generated reviews

---

## 3. Dataset Description

A **self-curated dataset** was created consisting of approximately **54,700 reviews**:

| Attribute | Value |
|---------|------|
| Total reviews | 54,700 |
| Human-written reviews | 31,678 |
| AI-generated reviews | 23,022 |
| Average word count | 74 |
| Max review length | 8,166 |
| Min review length | 3 |

- Human reviews were collected via **web scraping**
- AI reviews were generated using **ChatGPT-3.5**
- Dataset includes sentiment polarity as an auxiliary feature

---

## 4. Exploratory Analysis

Key insights:
- Human reviews tend to be **longer and sentiment-diverse**
- AI reviews are **shorter and sentiment-neutral**
- Correlation between word count and polarity is stronger for human reviews

These statistical signals provide discriminative power for classification models.

---

## 5. Machine Learning Pipeline

### 5.1 Text Preprocessing
- Lowercasing
- Tokenization
- Stopword removal
- Lemmatization

### 5.2 Feature Engineering
- TF-IDF vectorization
- Polarity-based auxiliary features

---

## 6. Classical Machine Learning Models (CPU)

Models evaluated using **scikit-learn**:
- Logistic Regression
- Naïve Bayes
- Decision Trees
- Random Forest
- SVM
- XGBoost
- MLP

### Key Result:
- **Decision Tree achieved 97.4% accuracy**
- Logistic Regression and SVM provided strong trade-offs between speed and accuracy

---

## 7. GPU-Accelerated ML (RAPIDS AI)

RAPIDS AI models evaluated using cuML:
- Logistic Regression
- SVM
- Random Forest
- XGBoost
- KNN

### Key Observation:
- **SVM (RAPIDS)** achieved **96.9% accuracy**
- Execution time reduced significantly compared to CPU models
- Demonstrates scalability for large corpora

---

## 8. Deep Learning & Transformer Models

Models evaluated:
- 1D-CNN
- LSTM
- BERT
- GPT-2

| Model | Accuracy | Execution Time |
|-----|---------|---------------|
| GPT-2 | **97.5%** | High |
| BERT | 96.7% | Moderate |
| LSTM | 96.8% | High |
| 1D-CNN | 94.8% | Low |

### Insight:
- **GPT-2 achieves the highest accuracy**
- Computational cost and latency must be carefully considered in production settings

---

## 9. Comparative Findings

- Classical ML models remain competitive for structured review detection
- RAPIDS AI provides **significant speedups** without accuracy loss
- Transformer models excel in semantic nuance detection
- Model choice should balance **accuracy, latency, and resource cost**

---

## 10. Limitations

- Dataset bias toward English-language reviews
- Performance depends on LLM generation patterns
- Computational constraints limit transformer scalability
- Rapid evolution of generative models requires continuous retraining

---

## 11. Production & Monitoring Considerations

- Drift detection as AI-generated text evolves
- Periodic retraining with newer LLM samples
- Monitoring false positives impacting genuine users
- Ethical deployment and transparency requirements

---

## 12. Project Type

**NLP + Generative AI Research Project (Mentored)**  
Text Classification | Trust & Safety | ML Systems

---

## 13. Mentor

**Dr. Arun Singh Pundir**  
Assistant Professor, CSE  
NLP | Generative AI | ML Infrastructure
