# Image Dehazing using Deep Learning
**Low-Level Vision for Robust Perception Systems**

---

## 1. Problem Overview

Atmospheric haze significantly degrades image quality in outdoor environments due to **light scattering and absorption by suspended particles**.  
This degradation negatively impacts downstream computer vision tasks such as:

- Surveillance and security monitoring  
- Autonomous driving perception  
- Aerial and satellite imagery analysis  

The objective of this project is to **restore haze-free images from single hazy inputs** using **deep learning–based image restoration techniques**.

---

## 2. Why Image Dehazing is Hard (Real-World Context)

Image dehazing is a challenging inverse problem due to:

- Unknown and non-uniform haze density  
- Loss of contrast and color fidelity  
- Depth-dependent degradation  
- Scene-specific atmospheric conditions  

Traditional physics-based models rely on **hand-crafted priors** (e.g., Dark Channel Prior), which often fail in:
- Bright scenes
- Sky-dominant images
- Non-homogeneous haze conditions  

These limitations motivate **learning-based dehazing approaches**.

---

## 3. Dataset Description

- Combination of **synthetic and real hazy images**
- Paired hazy–clear image samples
- Diverse outdoor scenes including:
  - Urban environments
  - Natural landscapes
  - Aerial viewpoints  

The dataset is chosen to emphasize **generalization across scene types** rather than benchmark overfitting.

---

## 4. Methodology

### 4.1 Preprocessing
- Image resizing and normalization
- Color space consistency checks
- Train–validation separation to avoid scene leakage

---

### 4.2 Model Architecture

This project explores **CNN-based single image dehazing models**, focusing on:

- Encoder–decoder style architectures
- Feature extraction for haze-related artifacts
- End-to-end learning without explicit atmospheric modeling  

The model implicitly learns:
- Transmission map estimation
- Scene radiance recovery
- Contrast and color restoration

---

## 5. Training Strategy

- Supervised learning using paired data
- Loss functions emphasizing:
  - Pixel-level reconstruction
  - Structural similarity
- Regularization to prevent over-smoothing artifacts

---

## 6. Evaluation Metrics

The restored images are evaluated using:

- **PSNR (Peak Signal-to-Noise Ratio)**  
- **SSIM (Structural Similarity Index)**  

These metrics capture both:
- Numerical reconstruction accuracy
- Perceptual image quality

---

## 7. Experimental Observations

Key observations from experiments include:

- CNN-based methods outperform classical priors in dense haze
- Over-smoothing is a common failure mode
- Color distortion occurs when haze density varies sharply
- Performance degrades for extremely bright or sky-dominant regions

---

## 8. Limitations

- Performance depends on haze distributions seen during training
- Extreme haze conditions remain challenging
- Absence of explicit physical constraints may introduce artifacts
- Single-image methods ignore temporal cues available in video data

---

## 9. Deployment & System Considerations

For real-world deployment:

- Dehazing should be treated as a **preprocessing module**
- Latency constraints must be considered for real-time systems
- Confidence estimation is required before downstream usage
- Periodic retraining is needed when camera setups or environments change

---

## 10. Learning Outcomes

- Understanding low-level vision problems
- Designing CNNs for image restoration
- Evaluating perceptual quality versus numerical metrics
- Appreciating deployment challenges in vision pipelines

---

## 11. Project Type

**Student Project (Mentored)**  
Applied Computer Vision / Image Restoration

---

## 12. Mentor

**Dr. Arun Singh Pundir**  
Assistant Professor, CSE  
Computer Vision | Deep Learning | ML Systems
