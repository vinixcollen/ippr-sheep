# 🐑 HOG + SVM for Aerial Sheep Detection

A computer vision project that implements a **Histogram of Oriented Gradients (HOG) + Support Vector Machine (SVM)** pipeline for detecting sheep in aerial imagery. This project was developed as part of a university course (Image Processing and Pattern Recognition)

## 📌 Project Overview

This project demonstrates a traditional computer vision approach to object detection using:
- **HOG** for feature extraction
- **Linear SVM** for classification
- **Two-tier evaluation strategy** to test generalization across different datasets

## 🎯 Key Features

- **Complete preprocessing pipeline** including CLAHE enhancement, noise reduction, and sharpening
- **Automatic patch extraction** from annotated aerial images
- **Data augmentation** (flipping, brightness adjustment, rotation)
- **Two-tier evaluation**:
  - **Tier 1**: Same-domain testing (Roboflow dataset)
  - **Tier 2**: Cross-domain testing (Kaggle dataset)
- **Comprehensive visualization** at every pipeline stage
- **Threshold tuning** using precision-recall analysis

## 📊 Datasets Used

1. **Roboflow Aerial Sheep Dataset** (Primary)
   - Used for training, validation, and Tier 1 testing
   - Contains annotated aerial sheep images
   - 70/15/15 train/val/test split

2. **Kaggle Sheep UAV Dataset** (Secondary)
   - Used exclusively for Tier 2 cross-domain evaluation
   - Tests model generalization to different aerial imagery


## 🔧 Technical Implementation

### Preprocessing Pipeline
1. **Image Resizing & Padding** (512×512)
2. **CLAHE Contrast Enhancement**
3. **Gaussian Noise Reduction**
4. **Sharpening Filter**
5. **Patch Extraction** (128×128 patches)
6. **Normalization** (grayscale, 0-1 range)

### Feature Extraction
- **HOG Parameters**:
  - Orientations: 9
  - Pixels per cell: 8×8
  - Cells per block: 2×2

### Model Training
- **Classifier**: Linear SVM with balanced class weights
- **Validation**: 5-fold cross-validation
- **Threshold Tuning**: Optimal F1-score based on precision-recall curve

## 📈 Performance Metrics
<img width="436" height="77" alt="Screenshot 2026-01-02 at 9 58 08 pm" src="https://github.com/user-attachments/assets/935ef3c6-938f-427e-a3e2-9b8306a26d31" />

