# 🧠 DeepDetect: DeepFake Face Detection Using Machine Learning and Deep Learning

This project presents a comparative analysis of three different models for deepfake image detection, focusing specifically on **face images**. Deepfakes pose a significant threat in the digital world due to their ability to produce highly realistic fabricated visuals. This work evaluates and benchmarks multiple approaches to understand which model performs best for detecting manipulated human faces.

## 📌 Models Compared

### 1. **Logistic Regression**
- Binary classifier for real vs fake faces.
- Works on flattened image pixels.
- Test Accuracy: **84%**

### 2. **Support Vector Machine (SVM)**
- Kernel-based classifier using handcrafted features like HOG and LBP.
- More robust than logistic regression but struggles with complex facial artifacts.
- Test Accuracy: **76%**

### 3. **Convolutional Neural Network (CNN – ResNet-18)**
- Deep learning model capable of learning spatial and hierarchical features automatically.
- Best suited for image-related tasks.
- Test Accuracy: **96%**

## 📂 Dataset
- **Source**: [Real vs AI Generated Faces Dataset from Kaggle](https://www.kaggle.com/datasets/philosopher0808/real-vs-ai-generated-faces-dataset)
- Contains only **face images** (real and AI-generated).
- **Total Images Used: ~10,000**
  - 7,000 — Training
  - 1,500 — Validation
  - 1,500 — Test

## 🛠️ Preprocessing & Feature Engineering

### For Logistic Regression & SVM
- Resized to 128×128
- Normalization
- Handcrafted features (HOG, LBP)
- Flattened pixel vectors for logistic regression

### For CNN (ResNet-18)
- Resized to 224×224
- Normalized using ImageNet stats
- Data augmentation (flips, rotations, color jitter)
- End-to-end feature learning

## 📊 Performance Evaluation Metrics

Models were evaluated on:
- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix

# 🏆 Results Summary

| Model | Test Accuracy | Summary |
|--------|---------------|---------|
| **Logistic Regression** | **84%** | Strong baseline but limited for image complexity |
| **SVM** | **76%** | Good with handcrafted features but weaker overall |
| **CNN (ResNet-18)** | **96%** | Best performance; excels at learning facial patterns |

✔ **CNN achieved the highest accuracy (96%)**, clearly outperforming traditional models due to its strong feature extraction capabilities.

# 🔍 Key Insights

- The current system detects **only face-based deepfakes**.
- Logistic Regression and SVM cannot fully capture **complex manipulation artifacts**.
- CNN models like **ResNet-18** provide significantly better results because they learn **visual features hierarchically**.
- **Deep learning is essential** for modern deepfake detection systems.

# 🚀 Future Work

### Extend detection beyond faces:
- Full-body deepfakes  
- Video deepfakes  
- Audio-visual manipulations  

### Model & training improvements:
- Implement **ensemble models**
- Add **more advanced data augmentations**
- Experiment with **EfficientNet, MobileNet, Vision Transformers (ViT)**


# 📁 Repository Structure

```
├── Models/
│ ├── Simple_Logistic_Regression.ipynb
│ ├── Support_Vector_Machine.py
│ ├── CNN_RestNet.py
├── Gradio_Interface.ipynb
├── Results.md
├── README.md
└── requirements.txt
```
