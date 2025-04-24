# Catheter Placement Classification (ADS2002 Project)

This project was developed as part of the ADS2002 unit at Monash University. The goal was to build a deep learning model that can identify the presence of various catheters and lines in chest X-ray images, and further detect whether they are correctly positioned.

## 📌 Project Objective

Incorrect placement of medical lines such as nasogastric or endotracheal tubes can lead to serious complications. This project aims to automate the detection and positioning of these lines from chest radiographs using deep learning models.

The tasks include:
- Classifying the presence of different types of catheters and tubes.
- Identifying whether any of them are malpositioned.
- Interpreting model behavior using saliency maps and occlusion.
- Evaluating model performance in a multi-label classification setting.

## 🗃️ Dataset

We used the [RANZCR CLiP](https://www.kaggle.com/c/ranzcr-clip-catheter-line-classification/) dataset, which includes annotated chest X-rays for multiple catheter types. Only the training dataset was used in this project.

## 🧠 Methodology

- Image preprocessing and feature extraction
- Model training using:
  - ResNet for image-level classification
  - U-Net for segmentation and tube tip localization
- Combined outputs for malposition detection
- Model interpretability with Grad-CAM and image occlusion
- Evaluation using multi-label metrics (e.g., F1 score, AUC)

## 🏆 Results

- Achieved High Distinction (HD) in ADS2002
- Successfully identified multiple catheter types with reasonable accuracy
- Demonstrated early understanding of model interpretability techniques



