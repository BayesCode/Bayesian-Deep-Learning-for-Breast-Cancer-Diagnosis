# Bayesian Deep Learning for Breast Cancer Diagnosis

## Overview

This repository presents a **Bayesian Deep Learning framework for breast cancer classification using histopathological images**. The goal of this research is to improve the **reliability, interpretability, and trustworthiness of deep learning models in medical diagnosis** by incorporating predictive uncertainty estimation.

A **ResNet‑50 convolutional neural network (CNN)** is first implemented as a baseline classifier to distinguish between **benign and malignant breast cancer histopathology images**. The model is then extended into a **Bayesian Deep Learning framework using Monte Carlo Dropout**, enabling predictive uncertainty estimation alongside classification predictions.

The results demonstrate that uncertainty-aware models can provide **more reliable probability estimates and improved diagnostic transparency**, which is essential for **AI-assisted clinical decision-making systems**.

---

## Research Objectives

The main objectives of this research include:

- Developing a **deep convolutional neural network (CNN)** for breast cancer classification.
- Extending the CNN into a **Bayesian Deep Learning framework** to capture predictive uncertainty.
- Estimating uncertainty using **Monte Carlo Dropout**.
- Visualizing model decision regions using **Grad-CAM interpretability techniques**.
- Evaluating model performance using **classification and calibration metrics**.
- Comparing **deterministic deep learning models with Bayesian deep learning approaches**.

---

## Dataset

The study uses **publicly available breast cancer histopathology datasets**, such as:

- Breast Histopathology Images Dataset
- BreakHis Dataset

Each image is labeled as:

- **Benign**
- **Malignant**

The dataset was divided into:

- Training set
- Validation set
- Test set

This split ensures proper training, model tuning, and unbiased evaluation.

---

## Data Preprocessing

The following preprocessing steps were applied before model training:

- Dataset splitting into **training, validation, and test sets**
- **Class balancing using upsampling** to avoid prediction bias
- Image resizing
- Pixel normalization using **ImageNet mean and standard deviation**

---

## Data Augmentation

To improve model generalization and reduce overfitting, several augmentation techniques were applied to the training data:

- Random Horizontal Flip
- Random Vertical Flip
- Random Rotation
- Color Jitter (brightness, contrast, saturation, hue)
- Random Resized Crop

These augmentations help the model learn **robust visual features from histopathology images**.

---

## Model Architecture

### Baseline Model

A **ResNet‑50 convolutional neural network** was used as the baseline classification model.

The final fully connected layer was modified to perform **binary classification**:

- Benign
- Malignant

---

### Bayesian Deep Learning Model

The baseline CNN was extended into a **Bayesian framework** using **Monte Carlo Dropout**.

During inference:

- Multiple stochastic forward passes are performed
- Dropout remains active
- The model produces a **distribution of predictions**

This allows the model to estimate:

- Predictive mean
- Predictive uncertainty

Such uncertainty estimates are crucial for **risk‑aware medical decision-making**.

---

## Model Training

The models were trained using the following configuration:

| Parameter | Value |
|----------|------|
| Optimizer | Adam |
| Learning Rate | 1e‑4 |
| Loss Function | Cross Entropy Loss |
| Epochs | 30 |
| Early Stopping | Enabled |

Early stopping was implemented to **prevent overfitting and improve generalization**.

---

## Model Evaluation

Model performance was evaluated using both **classification metrics** and **calibration metrics**.

### Classification Metrics

- Accuracy
- F1‑Score
- Confusion Matrix
- Classification Report

### Calibration Metrics

To assess reliability of predicted probabilities:

- Expected Calibration Error (ECE)
- Brier Score

Calibration metrics are important because **high accuracy alone does not guarantee trustworthy predictions**.

---

## Model Interpretability

To improve transparency of the deep learning model:

### Grad-CAM

**Gradient-weighted Class Activation Mapping (Grad-CAM)** was used to visualize the image regions that most influenced the model's predictions.

These visualizations help verify that the model focuses on **clinically meaningful histopathological structures**.

### Uncertainty Maps

Predictive uncertainty maps were generated to highlight:

- Regions where the model is confident
- Regions where predictions are uncertain

This can help **pathologists identify diagnostically ambiguous areas**.

---

## Results Summary

### Baseline ResNet‑50

| Metric | Value |
|------|------|
| Accuracy | 94.67% |
| F1 Score | 94.66% |
| Expected Calibration Error | 0.0263 |
| Brier Score | 0.0773 |

---

### Bayesian Deep Learning Model

| Metric | Value |
|------|------|
| Accuracy | 99.87% |
| F1 Score | 0.999 |
| Expected Calibration Error | 0.0016 |

---

### Key Findings

The Bayesian deep learning model demonstrates:

- Higher classification accuracy
- Better calibrated predictions
- Reliable uncertainty estimation

This makes the model more suitable for **AI-assisted medical diagnostics** where reliability is critical.

---


## Experimental Results

### Grad-CAM Explanation

<p align="center">
  <img src="results/result 1.png" width="500">
</p>

The Grad-CAM visualization highlights the regions of the histopathological image that contributed most strongly to the model's prediction.

---

### Predictive Uncertainty

<p align="center">
  <img src="results/BDL uncertainty hist.png" width="500">
</p>

The uncertainty histogram shows the distribution of predictive uncertainty estimated using Monte Carlo Dropout.

---

### Bayessian Deep Learning Accuracy

<p align="center">
  <img src="results/BDL acc.png" width="500">
</p>

Accuracy of the model.

---

### Bayessian Deep Learning Confussion Matrix

<p align="center">
  <img src="results/BDL CM.png" width="500">
</p>



## Research Contributions

This work contributes to the field of **AI‑assisted medical imaging** by:

- Developing a **Bayesian Deep Learning framework for breast cancer diagnosis**
- Integrating **uncertainty quantification into deep neural networks**
- Providing **interpretability through Grad‑CAM visualizations**
- Demonstrating improved **model reliability and calibration**

---

## Future Work

Potential future extensions include:

- Deep ensemble methods for **uncertainty estimation**
- **Vision Transformer architectures** for medical imaging
- **Multi‑class cancer subtype classification**
- Clinical validation on **larger and more diverse datasets**

---

## Authors

This project was developed by:

- **Damilare Akinyemi**
- **Daniel Olofin**
- **Olajumoke Olajide**
- **Adebona Oreoluwa**
- **Obiri Wilson**

**Research Interests**

- Artificial Intelligence  
- Medical Imaging  
- Deep Learning  
- Bayesian Machine Learning  

---

