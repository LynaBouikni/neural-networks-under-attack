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

---

## 🏗️ Models

| Model | Architecture | Accuracy |
|-------|--------------|----------|
| Model A | Basic CNN (LeNet-5 style) | ~40% |
| Model B | Conv + BN + MaxPool ×3 + FC ×2 | ~69% |

---

## ⚔️ Attack Implementations

- **FGSM** – Fast Gradient Sign Method  
- **PGD** – Projected Gradient Descent (iterative FGSM)  
- **DeepFool** – Minimal perturbations for misclassification

All attacks are implemented and tested within `Stage1.ipynb` and `Stage2.ipynb`.

---

## 🛡️ Defense Strategies

### 🔹 Adversarial Training
- Integrates FGSM/PGD-generated images during training.
- Yields improved robustness (~55–60% accuracy under attack).

### 🔹 Randomized Networks
- Dropout layers used during both training and inference.
- Slight robustness boost: e.g., accuracy under DeepFool increases from ~11.6% → 25% after training.

---

## 📊 Results Summary

| Method                     | Accuracy (Clean) | Accuracy (Attacked) |
|----------------------------|------------------|----------------------|
| Basic CNN (Model A)        | 40%              | ↓ drastically        |
| Improved CNN (Model B)     | 69%              | ~10–35% (FGSM/PGD)   |
| Adversarial Training (FGSM)| ~60%             | ↑ stability          |
| Randomized + DeepFool      | —                | ~25%                 |

---

## 📂 How to Run

> Clone the repo and install dependencies:

```bash
git clone https://github.com/yourusername/neural-networks-under-attack.git
cd neural-networks-under-attack
pip install -r requirements.txt
```
Then run:
```bash
Stage1.ipynb: Baseline training + FGSM/PGD attacks

Stage2.ipynb: Advanced defense & DeepFool testing
```

🖼️ Visual Example

Adversarial examples crafted using DeepFool: imperceptible to the human eye, but fooling the network.

🗝️ Key Takeaways
Small perturbations can have major effects on standard CNNs.

Adversarial training increases resilience but may reduce accuracy on clean inputs.

Randomized inference introduces unpredictability, making attacks harder.

DeepFool is especially dangerous due to its subtlety.

🧭 Future Directions
Try ensemble models or Bayesian uncertainty modeling.

Implement SHAP/LIME to visualize decision boundaries under attack.

Investigate black-box attacks (transferability, query-based).

Build a real-time adversarial detection system.

📬 Contact
Lyna Bouikni
📧 lynabouiknia@.com
🔗 LinkedIn

📚 References
Goodfellow et al. (2014). Explaining and Harnessing Adversarial Examples

Moosavi-Dezfooli et al. (2016). DeepFool: A Simple and Accurate Method to Fool Deep Neural Networks

Madry et al. (2018). Towards Deep Learning Models Resistant to Adversarial Attacks

This project was completed as part of the Master IASD program at Université Paris Dauphine.
