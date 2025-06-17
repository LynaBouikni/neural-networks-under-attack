# neural-networks-under-attack

# 🛡️ Training Robust Neural Networks against Adversarial Attacks

## 🧠 Overview

This project investigates the robustness of Convolutional Neural Networks (CNNs) against adversarial attacks using the CIFAR-10 dataset. We implement and evaluate different adversarial attack techniques (FGSM, PGD, DeepFool) and defense strategies (Adversarial Training, Randomized Networks) in two key stages:

1. **Establish a baseline classifier and test its vulnerabilities** under adversarial conditions.
2. **Experiment with advanced attack and defense strategies** to improve model robustness and resilience.

📚 **Authors**: [Lyna Bouikni](https://www.linkedin.com/in/your-profile) & Arthur Mussard  
🏫 **University**: Paris Dauphine – M2 IASD  
📅 **Date**: December 2023

---

## 🎯 Objectives

- ✅ Train and evaluate baseline CNN classifiers (LeNet-style and enhanced architectures)
- ✅ Implement adversarial attacks: FGSM, PGD, DeepFool
- ✅ Apply adversarial training to enhance model robustness
- ✅ Explore randomized networks as a novel defense mechanism
- ✅ Assess performance degradation and recovery under attack scenarios

---

## 🧪 Dataset

- **Name**: [CIFAR-10](https://www.cs.toronto.edu/~kriz/cifar.html)
- **Description**: 60,000 32x32 color images across 10 classes
- **Use**: Training and testing adversarial attacks and defenses on image classification tasks

---

## 🏗️ Model Architectures

| Model | Description | Accuracy |
|-------|-------------|----------|
| **Model A** | Basic CNN (LeNet-5 style) | 40% |
| **Model B** | Conv + BN + MaxPool x3 + FC x2 | 69% |

- Batch Normalization significantly improved performance in Model B.
- Model B was used for most experiments.

---

## ⚔️ Attack Methods

### 🔸 Fast Gradient Sign Method (FGSM)

- One-step attack that perturbs the input in the direction of the loss gradient.
- Accuracy dropped from 52% → ~35% as epsilon increased.

### 🔸 Projected Gradient Descent (PGD)

- Multi-step iterative variant of FGSM.
- Stronger than FGSM: accuracy dropped to ~10% at higher perturbation levels.

### 🔸 DeepFool Attack

- Iteratively modifies inputs to cross decision boundaries with minimal changes.
- Nearly imperceptible perturbations cause significant classification errors.

---

## 🛡️ Defense Techniques

### 🔹 Adversarial Training

- Training with adversarial examples improves robustness.
- Both FGSM and PGD adversarial training lead to over 50% accuracy under attacks.
- FGSM adversarial training proved more effective overall.

### 🔹 Randomized Networks

- Introduced stochastic behavior using dropout at inference time.
- Results:
  - Accuracy on clean data: **11.57%**
  - Accuracy on perturbed (DeepFool) data: **25.07%**
- Suggests moderate gain in robustness through randomness + adversarial exposure.

---

## 📊 Results Summary

| Method | Accuracy (clean) | Accuracy (under attack) |
|--------|------------------|--------------------------|
| Model A | 40% | Very low under attack |
| Model B | 69% | Drops under FGSM/PGD/DeepFool |
| Adversarially Trained (FGSM) | ~55-60% | Higher stability across attacks |
| Randomized Network (no adv. training) | 11.57% | — |
| Randomized + DeepFool training | — | 25.07% |

---

## 🧪 Experiments & Code

Main components:
- `cnn_baseline.py`: Base CNN models (Model A & B)
- `attacks.py`: FGSM, PGD, DeepFool implementations
- `train_adv.py`: Adversarial training loops
- `randomized_network.py`: Dropout-enhanced CNN architecture

---

## 🗣️ Key Insights

- Even small perturbations can mislead standard classifiers.
- Adversarial training meaningfully boosts model robustness.
- DeepFool is particularly effective at minimalistic attacks.
- Randomized inference adds stochastic defense but benefits further from adversarial exposure.
- There's a trade-off between model complexity, training time, and robustness.

---

## 🧭 Future Work

- 🔬 Explore black-box adversarial attacks and defenses.
- 🧠 Integrate SHAP/LIME for interpretability under attack.
- ⚙️ Deploy models with robust inference pipelines.
- 📦 Package robust models for real-time applications (e.g., healthcare, autonomous driving).

---

## 📬 Contact

If you'd like to connect or ask questions:

**Lyna Bouikni**  
📧 lynabouiknia@.com  
🔗 [LinkedIn]([https://www.linkedin.com/in/your-profile](https://www.linkedin.com/in/lyna-b-231a41126/))

---

## 📚 References

- Goodfellow et al. (2014) – Explaining and Harnessing Adversarial Examples  
- Moosavi-Dezfooli et al. (2016) – DeepFool: A Simple and Accurate Method to Fool Deep Neural Networks  
- Madry et al. (2018) – Towards Deep Learning Models Resistant to Adversarial Attacks

---

_This project was completed as part of the Master IASD program at Université Paris Dauphine._
