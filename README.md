# Multi-Class Image Classification using Pretrained ResNet-18 & VGG16

This project was completed as part of **GIKI Advanced AI Bootcamp 2025 — Week 02**.  
It focuses on **transfer learning** by fine-tuning ResNet-18 and VGG16 on a **3-class subset of CIFAR-10** (airplane, automobile, bird) using **PyTorch**.

---

## Problem Statement

The goal was to fine-tune two pretrained convolutional neural networks — **ResNet-18** and **VGG16** — for a small, fast-to-train dataset.  
We compare their performance using accuracy, precision, recall, F1-score, and confusion matrices.

---

## Dataset

- **Name:** CIFAR-10 (subset: airplane, automobile, bird)
- **Source:** `torchvision.datasets.CIFAR10`
- **Train samples:** 15,000
- **Test samples:** 3,000

**Why this dataset?**

- Small & clean — ideal for fast training
- Balanced classes
- Easy to load in PyTorch

---

## Methodology

1. **Data Loading & Preprocessing**
   - Resize to `224×224`
   - Normalize with ImageNet mean & std
   - Batch size: `32`
2. **Model Setup**
   - **ResNet-18:** Replace final FC layer → 3 outputs
   - **VGG16:** Replace last classifier layer → 3 outputs
   - Optimizer: Adam (lr=0.001)
   - Loss: CrossEntropyLoss
3. **Training**
   - Epochs: 10 for each model
   - GPU acceleration
   - Monitored training loss & test accuracy
4. **Evaluation**
   - Accuracy, precision, recall, F1-score
   - Confusion matrix visualizations
5. **Overfitting Check**
   - Compared train & test accuracy
   - No strong overfitting detected

---

## Results

| Model     | Train Acc | Test Acc | Avg Precision | Avg Recall | Avg F1 |
| --------- | --------- | -------- | ------------- | ---------- | ------ |
| ResNet-18 | 99.33%    | 96.33%   | 0.96          | 0.96       | 0.96   |
| VGG16     | 91.32%    | 89.03%   | 0.89          | 0.89       | 0.89   |

