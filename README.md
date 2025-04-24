# Catheter Placement Classification (ADS2002 Project – Monash University)

This repository presents a deep learning pipeline developed as part of the ADS2002 unit at Monash University. The goal was to build a multi-stage model for medical image analysis, specifically focused on classifying and localizing catheters in chest radiographs to support clinical decision-making and reduce risks caused by catheter misplacement.

---

## 🏥 Background

Incorrect placement of medical catheters, such as Central Venous Catheters (CVCs), Endotracheal Tubes (ETTs), and Nasogastric Tubes (NGTs), can cause severe complications, including organ damage or even death. In this project, we use deep learning to identify:
- Whether catheters are present
- Whether they are placed correctly
- The brand/type and exact position of each catheter

---

## 🎯 Objectives

- Predict correct vs incorrect catheter placement from chest X-rays
- Detect catheter type and brand using image classification
- Segment catheter locations with pixel-level annotations
- Interpret model performance and visualize learned features

---

## 📚 Dataset

The dataset used is the publicly available **[RANZCR CLiP](https://www.kaggle.com/c/ranzcr-clip-catheter-line-classification/)** dataset. It includes thousands of labeled chest X-rays with annotations indicating the presence, position, and type of multiple catheters.

---

## 🧠 Methodology

### 1. Binary Classification – Catheter Placement Accuracy
- **Model**: YOLOv8 (small, medium, large variants)
- **Data**: Reformatted X-rays labeled as “normal” or “not normal” based on positioning
- **Result**: Medium YOLOv8 model (1024px input) detected ~80% of fully abnormal cases

### 2. Multi-label Classification – Catheter Type & Brand
- **Models**: ResNet50, DenseNet121 (via Keras)
- **Metric**: AUC score (suited for imbalanced medical datasets)
- **Result**: DenseNet achieved 91% AUC; ResNet achieved 87%

### 3. Segmentation – Catheter Localization
- **Model**: U-Net with attention mechanism
- **Preprocessing**: Augmentation (rotate, brightness, contrast, noise), rescaling to 512×512
- **Loss Function**: Combined Binary Cross-Entropy and Dice Loss
- **Result**: 98% validation accuracy using only CPU training

---

## 💡 Results Summary

- All models were trained on CPU due to GPU/CUDA limitations.
- YOLOv8 showed high precision for clear abnormal placements.
- DenseNet121 was the most effective for multi-label brand classification.
- U-Net achieved fine-grained catheter localization with high segmentation quality.
- Our pipeline demonstrates the potential of CNN-based architectures for medical support tools.
- Achieved High Distinction (HD) in ADS2002


