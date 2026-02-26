# Skyland – Optimal Drone Landing System

![Drone Landing](https://img.shields.io/badge/Status-Active-brightgreen)
![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Deep Learning](https://img.shields.io/badge/Framework-PyTorch-orange)

Skyland is a deep learning–based system designed to enable safe and optimal drone landings using semantic segmentation of aerial imagery. The system identifies safe landing zones while avoiding obstacles such as buildings, vegetation, and other hazards.

---

## Overview

Skyland processes aerial images and segments terrain into safe and unsafe regions for drone landing. The project utilizes semantic segmentation architectures such as **UNet** and **PSPNet**, trained on the **Semantic Drone Dataset**, to classify terrain into 24 distinct categories. A post-processing algorithm identifies optimal landing areas based on segmentation outputs.

### Key Features

- **Semantic Segmentation**: Classifies aerial terrain into 24 classes using deep learning models.
- **Safe Landing Detection Algorithm**: Filters unsafe regions (roofs, trees, people, etc.) and prioritizes safe surfaces.
- **Model Evaluation**: Comparative analysis of Manual UNet, Fine-Tuned UNet, and PSPNet.
- **Data Processing Pipeline**: Includes data visualization, augmentation, and preprocessing for robust training.

---

## Models and Performance

### 1. Manual UNet
- Encoder-decoder convolutional architecture  
- **Test Accuracy:** 79.35%

### 2. Fine-Tuned UNet (ResNet-50 Backbone)
- UNet with ImageNet-pretrained ResNet-50 encoder  
- **Test Accuracy:** 85.99% (Best Performing Model)

### 3. Fine-Tuned PSPNet
- Pyramid Scene Parsing Network with pretrained backbone  
- **Test Accuracy:** 81.13%

The Fine-Tuned UNet achieved the highest performance and was selected as the final model.

---

## System Workflow

### 1. Data Preparation
- Uses the Semantic Drone Dataset (Kaggle).
- Includes preprocessing, augmentation, and visualization.

Dataset Link:  
https://www.kaggle.com/datasets/bulentsiyah/semantic-drone-dataset

### 2. Model Training
- Trained for multi-class segmentation (24 classes).
- Metrics tracked: Accuracy, IoU (Intersection over Union), and Loss.

### 3. Safe Landing Algorithm
- Processes segmentation outputs to determine viable landing zones.
- Safe classes (e.g., paved areas, grass) are prioritized.
- Unsafe classes (e.g., roofs, trees, humans) are excluded.

### 4. Output
- Generates a visual map highlighting optimal landing regions.
- Results are stored in the `results/` directory.

---

## Results

- Fine-Tuned UNet achieved **85.99% test accuracy**.
- The system reliably identifies obstacle-free landing regions.
- Segmentation visualizations and safe-zone outputs are included in the repository.

---

## Future Improvements

- Extend training duration and optimize hyperparameters.
- Implement real-time inference for autonomous drone systems.
- Expand dataset diversity to improve generalization.

---

## Author

**Kishor S**  
Email: kishorverse2004@gmail.com  
GitHub: https://github.com/kishorverse  

---

Skyland provides a scalable and efficient approach to autonomous drone landing using computer vision and deep learning techniques.
