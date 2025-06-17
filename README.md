# 🛡️ neural-networks-under-attack  
_Training Robust Neural Networks against Adversarial Attacks_

## 🧠 Overview

This project investigates the robustness of Convolutional Neural Networks (CNNs) against adversarial attacks using the CIFAR-10 dataset. We implement and evaluate different adversarial attack techniques (FGSM, PGD, DeepFool) and defense strategies (Adversarial Training, Randomized Networks) in two key stages:

1. **Stage 1** – Establish a baseline CNN and test it under adversarial conditions.
2. **Stage 2** – Experiment with advanced attack and defense mechanisms to improve model robustness.

📚 **Authors**: Lyna Bouikni & Arthur Mussard  
🏫 Université Paris Dauphine – Master IASD  
📅 December 2023

---

## 🎯 Objectives

- ✅ Build and evaluate baseline CNN classifiers (LeNet-style and advanced architecture)
- ✅ Implement adversarial attacks: FGSM, PGD, DeepFool
- ✅ Apply adversarial training to increase model robustness
- ✅ Test randomized networks as a defense strategy
- ✅ Compare performance degradation and recovery under adversarial stress

---

## 🧪 Dataset

- **Name**: [CIFAR-10](https://www.cs.toronto.edu/~kriz/cifar.html)
- **Description**: 60,000 32x32 RGB images in 10 classes
- **Usage**: Train/test image classifiers under adversarial conditions

---

## 📁 Repository Structure

```bash
├── models/ # Saved model architectures and weights
├── Stage1.ipynb # Baseline CNN training and FGSM/PGD attacks
├── Stage2.ipynb # Adversarial training, DeepFool, Randomized networks
├── model.py # CNN architecture definition
├── test_project.py # Testing entry point
├── requirements.txt # Required Python packages
├── Slides_Data_Lab_3 (2).pdf # Slide presentation
├── report.pdf # Final report
├── .gitignore
└── README.md
```
