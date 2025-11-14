# 🧪 Deepfake Detection Model Comparison – Results

This document presents a performance comparison of three machine learning models used for deepfake **face** detection:

- **Logistic Regression**
- **Support Vector Machine (SVM)**
- **Convolutional Neural Network (CNN – ResNet-18)**

All models were trained and tested on the same dataset of ~10,000 real and AI-generated face images, with identical train/validation/test splits.

## 📊 1. Overall Performance Comparison

| Model | Type | Test Accuracy | Strengths | Weaknesses |
|-------|------|----------------|-----------|------------|
| **Logistic Regression** | Linear model | **84%** | Fast, simple baseline, good on clean and linearly separable data | Struggles with complex image features; no spatial understanding |
| **SVM** | Kernel-based ML | **76%** | Works well with handcrafted features (HOG/LBP), handles high-dimensional data | Depends heavily on feature quality; more misclassifications |
| **CNN (ResNet-18)** | Deep Learning | **96%** | Learns deep spatial features automatically; highest accuracy | Requires GPU; longer training |

## 🧠 2. Why CNN Performs the Best

CNNs especially ResNet-18 achieve superior deepfake detection because they:

- Learn **spatial facial patterns** such as edges, textures, distortions, and artifacts.
- Extract **hierarchical features**, from pixels → facial structures → deepfake anomalies.
- Are optimized for image tasks through convolutional and residual layers.

Traditional models like Logistic Regression and SVM lack spatial feature extraction capability.

## 🔍 3. Metric Comparison

> Only accuracy values are highlighted here (84%, 76%, 96%), but the models were also assessed using precision, recall, F1-score, and confusion matrices.

### **Accuracy Comparison**

| Metric | Logistic Regression | SVM | CNN (ResNet-18) |
|--------|----------------------|-----|------------------|
| **Accuracy** | **84%** | **76%** | **96%** |
| Precision | Moderate | Low–Moderate | High |
| Recall | Moderate | Low–Moderate | High |
| F1-Score | Good baseline | Lower | Excellent |
| Confusion Matrix | Moderate confusion | Higher confusion | Minimal confusion |

## 📁 4. Model-Specific Performance

### 4.1 Logistic Regression
- Uses flattened pixel features or simple extracted features.
- Performs surprisingly well for a basic linear classifier.
- **Accuracy:** **84%**
- Struggles to detect subtle deepfake manipulations.
- Best used as a **baseline model**.

### 4.2 Support Vector Machine (SVM)
- Utilizes handcrafted features such as:
  - **HOG (Histogram of Oriented Gradients)**
  - **LBP (Local Binary Patterns)**
- Effective at detecting texture-level patterns.
- **Accuracy:** **76%**
- Performance heavily depends on feature quality and preprocessing.

### 4.3 CNN – ResNet-18
- End-to-end training with convolutional filters.
- Learns meaningful deepfake-specific facial features.
- **Accuracy:** **96%**
- Best generalization and detection quality among all three models.

## 🏁 5. Conclusion

- Logistic Regression and SVM provide helpful baselines but **cannot match the capability of CNNs** for image-based deepfake detection.
- ResNet-18 significantly outperforms them, achieving **96% accuracy**.
- Deep learning is essential for detecting the complex artifacts present in deepfakes.

## 🚀 6. Future Improvements

- Expand detection beyond **face-only deepfakes**.
- Experiment with advanced models:
  - EfficientNet  
  - MobileNetV3  
  - Vision Transformers (ViT)
- Explore GAN-based anomaly detection.
- Use ensemble models or hybrid architectures.
- Improve dataset diversity and augmentation.
