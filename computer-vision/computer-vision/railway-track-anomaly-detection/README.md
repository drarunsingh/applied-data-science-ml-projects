# AI-Driven Drone-Based Railway Track Anomaly Detection
**Real-Time Object Detection using YOLOv8s**

---

## 1. Project Overview

Manual inspection of railway tracks is slow, labor-intensive, and prone to human error, especially across long track sections. Small obstructions such as stones, equipment, or construction material can easily be missed and may lead to serious safety hazards.

This project presents an **AI-based railway track monitoring system** that uses **drone-captured video** and a **ground-station inference pipeline** to automatically detect foreign objects and anomalies on or near railway tracks in near real time.

The system combines:
- A lightweight **drone-mounted camera** for video capture
- A **YOLOv8s object detection model enhanced with CBAM attention**
- A **GPU-enabled ground station** for inference, logging, and visualization

---

## 2. Problem Statement

Given a live or recorded aerial video stream of railway tracks captured from a drone, the system must:

- Detect foreign objects and obstructions on or near the rails
- Localize anomalies using bounding boxes
- Log each detection as a structured event
- Present alerts through a real-time operator dashboard

The goal is **decision support**, not autonomous control.

---

## 3. Dataset Creation

A **custom dataset** was created specifically for this project:

- Source: Drone-captured railway track videos
- Frame extraction rate: ~50 FPS
- Total images: ~2,900
- Annotation tool: CVAT
- Label scheme: Single class — **“anomaly”**
  - Objects on or dangerously close to the track

The dataset reflects **real deployment conditions** rather than curated benchmarks.

---

## 4. Model Architecture

### Baseline Model
- **YOLOv8s** (single-stage object detector)
- Chosen for:
  - Real-time inference capability
  - Strong performance on small objects

### Enhanced Model
- **YOLOv8s + Convolutional Block Attention Module (CBAM)**
- CBAM applies:
  - Channel-wise attention
  - Spatial attention
- Helps the model focus on:
  - Rails
  - Immediate surroundings
  - Suppresses irrelevant background

---

## 5. Experimental Results

The CBAM-enhanced model showed **clear improvement** over baseline YOLOv8s:

| Model | mAP@50–95 |
|------|-----------|
| YOLOv8s (Baseline) | 0.871 |
| YOLOv8s + CBAM | **0.896** |

- Precision and recall remained high
- Improvement achieved **without sacrificing inference stability**

---

## 6. Deployment Pipeline

The project goes beyond model training and implements a **full end-to-end system**:

### Ground Station Pipeline
- Accepts:
  - Offline video files
  - Live video stream (HDMI capture from drone controller)
- Performs:
  - Frame-wise inference
  - Confidence thresholding
  - Event severity assignment
  - CSV-based logging
  - Snapshot storage for each alert

### Visualization Layer
- **Flask**: Serves annotated video stream
- **Streamlit Dashboard**:
  - Total alerts
  - High-severity alerts
  - Confidence timelines
  - Latest alert snapshots
  - Searchable event logs

---

## 7. Key Contributions

- Custom **drone-view railway anomaly dataset**
- Demonstrated **effectiveness of CBAM attention** for rail scenes
- Implemented **light-drone / heavy-ground-station architecture**
- Delivered a **working prototype**, not just a trained model
- Operator-friendly real-time monitoring interface

---

## 8. Limitations

- Single-class anomaly detection
- Dataset limited to specific regions and lighting conditions
- RGB-only input (no thermal / night vision)
- Local-only dashboard (no distributed backend)

---

## 9. Future Work

- Multi-class anomaly categorization
- Night-time and thermal imaging support
- Multi-camera and multi-drone scaling
- Edge deployment comparison (Jetson vs ground station)
- Integration with railway maintenance systems

---

## 10. Project Type

**Capstone Project (Mentored)**  
Applied Computer Vision | Video Analytics | Real-Time ML Systems

---

## 11. Mentorship

**Dr. Arun Singh Pundir**  
Assistant Professor, CSE  
Thapar Institute of Engineering & Technology  
*Computer Vision • Deep Learning • ML Systems*

---

## 12. Disclaimer

This system is intended as a **decision-support prototype** and is not a replacement for certified railway safety mechanisms.
