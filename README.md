# Arrhythmia Identification Using Machine Learning

This repository contains the implementation of **Arrhythmia Classification** using **Machine Learning (SVM)** and **Deep Learning (CNN)**. The project compares the performance of these models using time-domain and frequency-domain features extracted from ECG signals.

## 📌 Overview
Early detection of arrhythmia is critical for heart disease diagnosis. This project aims to classify ECG signals into **normal** and **abnormal** categories using:
- **Support Vector Machine (SVM)** trained on the **MIT-BIH Arrhythmia Database** using extracted **HRV (Heart Rate Variability) features**.
- **Convolutional Neural Network (CNN)** trained on the **PTB-XL ECG Database**, which directly processes raw ECG signals.

## 📂 Dataset
We used two datasets for this study:
1. **MIT-BIH Arrhythmia Database** - Contains ECG recordings annotated for arrhythmia detection.
2. **PTB-XL ECG Database** - A larger dataset with 12-lead ECG recordings, useful for deep learning models.

## 🔧 Methodology
### 1️⃣ Preprocessing
- **Noise removal** using bandpass filters (Butterworth filter for PTB-XL).
- **Segmentation** of heartbeats using R-peak detection (NeuroKit2).
- **Time-domain** and **frequency-domain** feature extraction.

### 2️⃣ Feature Extraction
- **Time-domain features**: R-R intervals, Standard Deviation, RMS, PNN50, etc.
- **Frequency-domain features**: FFT, Power Spectral Density, LF/HF ratio.

### 3️⃣ Model Training
- **SVM (RBF Kernel)** trained on extracted HRV features.
- **CNN** trained on raw ECG signals without explicit feature extraction.

## 📊 Results
| Model  | Accuracy | Sensitivity | Specificity | F1-Score |
|--------|----------|-------------|-------------|----------|
| **SVM (Time-Domain)** | 89% | 100% | 73% | 92% |
| **SVM (Frequency-Domain)** | 78% | 90% | 72% | 85% |
| **CNN (Time-Domain)** | 91% | 95% | 92% | 90% |
| **CNN (Frequency-Domain)** | 84% | 88% | 84% | 87% |

🔹 **CNN in the time-domain performed the best, achieving 91% accuracy.**  
🔹 **SVM showed high sensitivity but lower specificity due to false positives.**

