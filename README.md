🩺 ECG Arrhythmia Detection using CNN and PCA
📘 Project Overview

This project detects arrhythmias (abnormal heartbeats) from ECG signals using a hybrid deep learning and signal processing approach.
It combines wavelet denoising, R-peak detection, data augmentation, PCA-based dimensionality reduction, and a 1-D CNN classifier to achieve over 95% accuracy.





⚙️ Pipeline

Data Source: MIT-BIH Arrhythmia Database (.dat, .hea, .atr files).

Preprocessing:
Band-pass filtering (0.5–40 Hz)
Wavelet denoising (db4)
R-peak detection via adaptive thresholding

Beat Extraction:
Extracts 0.6 s segments (0.2 s pre-R, 0.4 s post-R)
Normalizes each beat

Data Augmentation:
Adds small amplitude/noise variations
Time-stretching for temporal diversity

Feature Engineering:
Standard scaling
PCA for 95 % variance retention

Modeling:
CNN for temporal feature learning
KNN cross-validation for baseline comparison
Metrics: Accuracy, Sensitivity (Recall for abnormal class)

Visualization:
Plots R-peaks and sample beats for inspection





🧠 Model Architecture (CNN)
Input (beat segment)
↓
Conv1D (32 filters, kernel=7) + ReLU
↓
MaxPooling1D
↓
Conv1D (64 filters, kernel=5) + ReLU
↓
MaxPooling1D
↓
Conv1D (128 filters, kernel=3) + ReLU
↓
GlobalAveragePooling1D
↓
Dense(128) + Dropout(0.4)
↓
Dense(1, activation='sigmoid')





Metric	Score:
Accuracy	> 98 %
Sensitivity (Abnormal Recall)	> 97 %





🚀 Future Work:
Extend CNN with LSTM for sequential modeling
Multi-class arrhythmia classification (beyond Normal/Abnormal)
Real-time ECG signal analysis via edge deployment



👨‍💻 Author
Rishabh Singh Negi
Electronics & Communication Engineering, NIT Sikkim
📧 rishabhsinghnegi57@gmail.com
