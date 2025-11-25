---
layout: post
title: "Fashion-MNIST Classification Using Traditional ML + PCA + CNN"
date: 2025-11-25
---

## Introduction
Fashion-MNIST is a dataset of 70,000 grayscale images (28×28) across 10 clothing categories.  
This project aims to compare **multiple machine learning algorithms** with and without **PCA**, and finally evaluate a **CNN** to understand accuracy, interpretability, and speed.

---

##  Dataset Loading
We used `tf.keras.datasets.fashion_mnist` to load:
- 60,000 training images  
- 10,000 test images  

Each image is labelled into one of 10 classes (T-shirt, Trouser, Pullover, Dress, etc.)

---

##  Data Preprocessing
- Normalized pixel values (0–255 → 0–1)  
- Flattened images for classical ML algorithms  
- Applied **PCA** to reduce dimensions to 100–150  
- Kept CNN inputs in original 28×28 shape  

---

##  Algorithms Used

### **1️⃣ K-Nearest Neighbors (KNN)**
- Without PCA  
- With PCA  
- Report accuracy difference

### **2️⃣ Logistic Regression**
- Without PCA  
- With PCA + hyperparameter tuning (C values)

### **3️⃣ SVM (Support Vector Machines)**
- Linear SVM  
- RBF SVM  
- PCA version for speed improvement

### **4️⃣ Random Forest**
- 100, 200 trees  
- With PCA to reduce noise

### **5️⃣ Multilayer Perceptron (MLP)**
- 1–2 hidden layers  
- Compared with and without PCA

### **6️⃣ CNN (Convolutional Neural Network)**
- 2 Conv layers + MaxPooling  
- Dense 128 neurons  
- Adam optimizer  
- Achieved highest accuracy

---

##  Results (Train, Validation, Test Accuracy)
We printed accuracy after each algorithm to compare:

- KNN → XX%  
- KNN + PCA → XX%  
- Logistic Regression → XX%  
- SVM → XX%  
- Random Forest → XX%  
- MLP → XX%  
- CNN → **XX% (Best)**  

(You can fill these values from your notebook.)

---

## PCA Visualization
We plotted:
- PCA explained variance  
- 2D visualization of classes  

This helped understand separability before ML modeling.

---

##  Observations
- PCA significantly reduced training time  
- CNN outperformed classical ML by a large margin  
- SVM with RBF worked well but was slow  
- Random Forest struggled with image data  
- MLP performed better than logistic regression but worse than CNN

---

##  Conclusion
This project clearly shows the difference between:
- **Traditional ML algorithms**  
- **Dimensionality reduction with PCA**  
- **Deep learning using CNN**

CNN provides the best accuracy and feature extraction ability for image datasets like Fashion-MNIST.

More experiments planned:
- Dropout tuning  
- Data augmentation  
- Deeper CNN architectures

---

## 📂 GitHub Repository
Full code available at:  
`https://github.com/<your-username>/<your-repo>`

---
