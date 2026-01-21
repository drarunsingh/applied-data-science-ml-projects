# Maths GPT
**Few-Shot Learning–Based Mathematical Reasoning using Large Language Models**

---

## 1. Project Overview

Recent advances in Large Language Models (LLMs) such as GPT have demonstrated
strong capabilities in natural language understanding and generation.
However, **mathematical problem-solving remains a challenging benchmark** due
to the need for precise reasoning, symbolic manipulation, and numerical
consistency.

This project presents **Maths GPT**, a Generative AI system designed to
**interpret and solve mathematical problems expressed in natural language**
using **few-shot learning with pre-trained math-focused LLMs**.

The system aims to bridge the gap between:
- Natural language understanding
- Mathematical reasoning
- Data-efficient learning

---

## 2. Problem Motivation

Traditional mathematical problem-solving systems rely on:
- Rule-based solvers
- Symbolic manipulation engines
- Hard-coded logic pipelines

These approaches struggle with:
- Variability in natural language expressions
- Mixed symbolic and textual reasoning
- Generalization across diverse problem types

Large Language Models offer a promising alternative by leveraging
**linguistic and contextual knowledge**, but require careful prompting and
training to avoid reasoning errors.

---

## 3. Objective

The key objectives of this project are:

- To build an LLM-based system capable of solving mathematical problems
  expressed in natural language
- To apply **few-shot learning** to reduce dependency on large labeled datasets
- To evaluate reasoning accuracy across multiple mathematical domains
- To study the strengths and limitations of LLM-based mathematical reasoning

---

## 4. Dataset Description

The dataset used in this project includes:

- A wide variety of mathematical problem types:
  - Arithmetic
  - Algebra
  - Geometry
  - Calculus
- Each data entry consists of:
  - A unique ID
  - A question written in **LaTeX format**
  - The corresponding ground-truth answer

Using LaTeX as the input format ensures:
- High precision in mathematical expressions
- Support for complex formulas and notation
- Compatibility with scientific and engineering problem statements

---

## 5. Model Selection

Two math-oriented pre-trained LLMs are used:

- **DeepSeek Math LLM**
- **Gemma 2B**

These models are selected due to:
- Strong prior exposure to mathematical text
- Proven reasoning performance
- Ability to generalize using limited examples

---

## 6. Methodology

### 6.1 Few-Shot Learning Strategy

Instead of large-scale fine-tuning, the system employs **few-shot learning**:

- A small number of solved examples are provided as context
- The model learns patterns and reasoning strategies from these examples
- This enables generalization to unseen problem types

Few-shot learning is particularly effective in scenarios where:
- Labeled data is scarce
- Rapid adaptation is required
- Computational resources are limited

---

### 6.2 Inference Pipeline

1. Mathematical question provided in LaTeX format
2. Few-shot examples injected into the prompt
3. LLM generates solution and reasoning
4. Output evaluated against ground truth

---

## 7. Evaluation Strategy

The system is evaluated on a held-out test set of **50 mathematical problems**.

### Metrics Used
- Accuracy (correct final answer)
- Qualitative analysis of reasoning correctness

### Observations
- The model successfully solved **20 out of 50 problems**
- Performance was strongest on:
  - School-level (Class 10–12) problems
  - Arithmetic and algebraic reasoning
- More complex problems exposed reasoning limitations

---

## 8. Key Findings

- Few-shot learning significantly improves performance over zero-shot
- LaTeX-based input enhances clarity and parsing accuracy
- Reasoning quality varies with problem complexity
- LLMs show promising abstraction ability but lack formal verification

---

## 9. Limitations

- No symbolic or programmatic verification of results
- Numerical inconsistencies may arise in multi-step reasoning
- Performance degrades on advanced university-level mathematics
- Model behavior is sensitive to prompt structure

---

## 10. Future Scope and Commercialization

Potential future directions include:

- Extending coverage to university-level mathematics
- Integrating code interpreters for numerical verification
- Developing a domain-specific mathematical LLM
- Applying reinforcement learning for reasoning correctness
- Exploring commercialization in:
  - Education technology
  - Intelligent tutoring systems
  - Automated problem-solving platforms

---

## 11. Learning Outcomes

- Understanding LLM limitations in mathematical reasoning
- Applying few-shot learning effectively
- Designing prompt-based reasoning systems
- Evaluating generative models beyond surface-level accuracy

---

## 12. Project Type

**Capstone Project (Mentored)**  
Generative AI | Conversational AI | Mathematical Reasoning

---

## 13. Mentorship

**Dr. Arun Singh Pundir**  
Assistant Professor, CSE  
Thapar Institute of Engineering & Technology  
*Generative AI • ML Systems • Responsible AI*

---

## 14. References

- Drori et al., *A Neural Network Solves, Explains, and Generates University Math Problems*, PNAS 2022  
- Ying et al., *InternLM-Math: Open Math Large Language Models Toward Verifiable Reasoning*, arXiv 2024
