---
layout: post
title: "A Performance Benchmarking Study of Machine Learning, Deep Learning, and Zero-Shot Models on Fashion-MNIST"
date: 2025-11-25
---

### **Authors**
**SATYAJIT**, **AKSHAY**, **DHRUV**,  
**Srikar Sankranti**  
*Department of Electrical & Computer Engineering*  
*Texas A&M University*

---

## Introduction
The Fashion-MNIST dataset contains 70,000 grayscale images (28×28) across 10 fashion categories such as T-shirt, Trouser, Shirt, Coat, Sneaker, and Ankle Boot.  
This project benchmarks a variety of **machine learning algorithms**, applies **PCA for dimensionality reduction**, evaluates a **Convolutional Neural Network (CNN)**, and explores **Zero-Shot Image Classification** using a pretrained vision-language model.  
The goal is to compare performance, interpretability, training time, and generalization capabilities.



<img width="750" height="376" alt="image" src="https://github.com/user-attachments/assets/17a7fe80-4e8a-4b08-acdd-7810f197851f" />
---

## Dataset Loading
We utilized the TensorFlow dataset loader:

- **60,000** training images  
- **10,000** test images  
- 10 labeled classes  
- Images are normalized and reshaped depending on the model

This structure makes Fashion-MNIST a strong benchmark for evaluating classical ML and deep learning models.

---

## Data Preprocessing
- Pixel values scaled from **0–255 → 0–1**  
- Flattened images used for ML algorithms (KNN, SVM, RF, LR, MLP)  
- Applied **PCA (100–150 components)** to accelerate ML models  
- CNN used original **28×28×1** input format  
- Labels encoded into integer categories (0–9)


<img width="844" height="701" alt="image" src="https://github.com/user-attachments/assets/7c993ec9-cce0-464a-b9cc-da87acf16d1b" />


---

## Algorithms Used

### **1️⃣ K-Nearest Neighbors (KNN)**
- Tested with and without PCA  
- PCA version trained significantly faster  

### **2️⃣ Logistic Regression**
- With and without PCA  
- Hyperparameter tuning on **C values**

### **3️⃣ Support Vector Machines (SVM)**
- Linear SVM  
- RBF SVM  
- PCA version improved training speed and accuracy

### **4️⃣ Random Forest**
- 100-tree and 200-tree models tested  
- Poor performance due to raw pixel-format data

### **5️⃣ Multilayer Perceptron (MLP)**
- 1–2 hidden layers  
- Moderate performance but below CNN  

### **6️⃣ Convolutional Neural Network (CNN)**
- Two Conv2D layers + MaxPooling  
- Dense 128-layer  
- Adam optimizer  
- Tuned CNN gives best accuracy  

---

## 7️⃣ Zero-Shot Classification (CLIP-style Model)
Zero-shot classification uses a pretrained **vision-language** model to classify images **without any training**.

### **Method**
We created text prompts like:
- "a photo of a T-shirt"
- "a photo of a sneaker"
- "a photo of a handbag"

The model computes similarity between:
- image embedding  
- text prompt embeddings  

It predicts the closest class label.

### **Accuracy**
- **Zero-shot accuracy:** **70%**

### **Observations**
- Works well for unique shapes (sneakers, sandals, bags).  
- Struggles with ambiguous classes (shirt vs T-shirt).  
- Impressive performance without training — highlights strength of pretrained models.

---

## Results (Train, Validation, Test Accuracy)

| Model | Accuracy |
|-------|----------|
| KNN | 85.65% |
| KNN + PCA | 85.85% |
| Logistic Regression | 84.42% |
| Logistic Regression + PCA | 82.71% |
| SVM | 84% |
| SVM + PCA | 88.78% |
| CNN | 90.18% |
| **Tuned CNN** | **98%** |
| **Zero-Shot CLIP Model** | **70%** |

---

