# XPAFT-Transformer: An Explainable Physiological Attention-Based Multimodal Transformer for Edge-Enabled Stress Detection

## Overview

Stress is a significant health concern that affects both physical and mental well-being. Early and accurate stress detection can support timely intervention and improve healthcare outcomes.

This project presents **XPAFT-Transformer**, an Explainable Physiological Attention-Based Multimodal Transformer designed for real-time stress detection using physiological biosignals. The framework combines advanced signal processing, multimodal feature fusion, Explainable AI (XAI), and Transformer-based learning to classify stress and non-stress conditions effectively.

The trained model was successfully deployed on the **NVIDIA Jetson Orin Nano** platform, demonstrating its suitability for real-time wearable healthcare and edge AI applications.

---

## Project Title

**XPAFT-Transformer: An Explainable Physiological Attention-Based Multimodal Transformer for Edge-Enabled Stress Detection**

---

## Key Features

* Multimodal Physiological Signal Analysis
* Explainable Artificial Intelligence (XAI)
* Physiological Attention Layer (PAL)
* Feature-Level Fusion
* FT-Transformer Architecture
* Edge AI Deployment
* Real-Time Stress Classification
* Wearable Healthcare Applications

---

## Dataset

### WESAD Dataset (Wearable Stress and Affect Detection)

The project utilizes the publicly available WESAD dataset.

### Signals Used

* ECG (Electrocardiogram)
* EDA (Electrodermal Activity)

### Classification Labels

* Stress
* Non-Stress

---

## Methodology

### ECG Signal Processing

* Butterworth Bandpass Filtering
* CEEMDAN Decomposition
* IMF Energy Analysis
* Wavelet Denoising
* ECG Reconstruction
* Hilbert-Huang Transform (HHT)

### EDA Signal Processing

* Butterworth Low-Pass Filtering
* SCR/SCL Decomposition
* Adaptive Peak Enhancement

### Feature Extraction

#### ECG Features

* HRV Time-Domain Features
* HRV Frequency-Domain Features
* Entropy Features
* HHT-Based Features

#### EDA Features

* SCR-Based Features
* Tonic EDA Features
* Sympathetic Activity Features
* Autocorrelation Features

### Feature Fusion

Feature-level fusion was performed by combining ECG and EDA features into a unified multimodal representation.

### Data Balancing

* SMOTE (Synthetic Minority Oversampling Technique)

### Feature Standardization

* Z-Score Normalization
* StandardScaler

---

## Proposed XPAFT-Transformer Architecture

### Input

58 Physiological Features

### Physiological Attention Layer

* Linear (58 → 58)
* ReLU
* Linear (58 → 58)
* Sigmoid

### FT-Transformer Backbone

* 4 Transformer Blocks
* Embedding Dimension: 256
* Multi-Head Self Attention
* 8 Attention Heads
* Feed Forward Dimension: 768
* ReGLU Activation
* Layer Normalization
* Dropout: 0.1

### Output

Binary Classification

* Stress
* Non-Stress

---

## Explainable AI Module

The Explainable AI component improves transparency by providing:

* Feature Importance Scores
* Attention Weight Analysis
* ECG Feature Contribution
* EDA Feature Contribution
* Model Interpretability

---

## Model Training Configuration

| Parameter        | Value             |
| ---------------- | ----------------- |
| Framework        | PyTorch           |
| Dataset          | WESAD             |
| Optimizer        | AdamW             |
| Learning Rate    | 0.0005            |
| Weight Decay     | 1e-5              |
| Loss Function    | BCEWithLogitsLoss |
| Epochs           | 50                |
| Cross Validation | Stratified 5-Fold |
| Data Balancing   | SMOTE             |
| Feature Scaling  | StandardScaler    |
| Threshold        | 0.5               |

---

## Performance Results

### Cross-Validation Performance

| Metric    | Score  |
| --------- | ------ |
| Accuracy  | 96.54% |
| Precision | 97.00% |
| Recall    | 97.00% |
| F1-Score  | 97.00% |
| AUC       | 0.9741 |

---

## Edge Deployment Results

### Platform

NVIDIA Jetson Orin Nano

### Deployment Metrics

| Metric                 | Score     |
| ---------------------- | --------- |
| Accuracy               | 99.75%    |
| Precision              | 98.00%    |
| Recall                 | 100.00%   |
| F1-Score               | 99.00%    |
| AUC                    | 0.9796    |
| Average Inference Time | 10.925 ms |

---

## Edge AI Deployment

The trained XPAFT-Transformer model was exported to ONNX format and deployed on NVIDIA Jetson Orin Nano using ONNX Runtime.

### Benefits

* Real-Time Inference
* Low Latency
* Edge Computing Support
* Wearable Healthcare Applications
* Resource-Efficient Deployment

---

## Repository Structure

```text
XPAFT-Transformer-Stress-Detection/
│
├── README.md
├── Stress_Detection.ipynb
├── requirements.txt
│
├── deployment/
│   ├── PAFT_Transformer.onnx
│   ├── scaler.pkl
│   └── harika.py
│
├── results/
│   ├── roc_curve.png
│   ├── confusion_matrix.png
│   ├── training_loss_curve.png
│   └── jetson_deployment.png
│
├── architecture/
│   ├── methodology.png
│   └── xpaft_transformer_architecture.png
│
├── technical_paper/
│   └── Technical_Paper.pdf
│
└── demo/
    └── project_demo.mp4
```

---

## Applications

* Wearable Healthcare Systems
* Stress Monitoring
* Mental Health Assessment
* Edge AI Healthcare Solutions
* Biomedical Signal Analysis
* Remote Patient Monitoring

---

## Future Scope

* Integration of PPG Signals
* Integration of EMG Signals
* Subject-Independent Stress Detection
* IoMT-Based Healthcare Systems
* Advanced Explainable AI Techniques (SHAP, LIME)
* Cross-Dataset Generalization
* Mobile and Wearable Device Deployment

---

## Technologies Used

* Python
* PyTorch
* ONNX Runtime
* NumPy
* Pandas
* Scikit-Learn
* NeuroKit2
* Matplotlib
* NVIDIA Jetson Orin Nano

---

## Author

**Harika Bhogi**

B.Tech – Computer Science and Information Technology

Maharaj Vijayaram Gajapathi Raj College of Engineering (MVGR)

Srikakulam, Andhra Pradesh, India

---

