# cautious-octo-eureka

# Deep Learning Project 3: Adversarial Attacks and Transferability

This project investigates the vulnerability of deep convolutional image classifiers to adversarial examples. We apply three popular attack methods—FGSM, PGD, and patch-based attacks—on a pre-trained ResNet-34 model and evaluate the transferability of these adversarial inputs to a different architecture: DenseNet-121.

## 🧪 Attack Overview

| Attack Type | ε       | Iterations | Region        | Norm     |
|-------------|----------|------------|----------------|----------|
| FGSM        | 0.02     | 1          | Whole image    | $L_\infty$ |
| PGD         | 0.02     | 10         | Whole image    | $L_\infty$ |
| Patch       | 0.3–0.4  | 20         | 32×32 patch    | $L_0$      |

## 🧾 Tasks

- **Task 1**: Evaluate ResNet-34 on clean 500-image subset (100 ImageNet-1K classes × 5 images)
- **Task 2**: Generate FGSM adversarial examples
- **Task 3**: Apply iterative PGD attacks
- **Task 4**: Perform localized patch attacks
- **Task 5**: Test cross-model transfer to DenseNet-121

## 📊 Accuracy Summary

**ResNet-34:**

| Attack Type | Top-1 Accuracy (%) | Top-5 Accuracy (%) |
|-------------|---------------------|---------------------|
| No Attack   | 75.39               | 93.87               |
| FGSM        | 3.00                | 19.00               |
| PGD         | 0.00                | 0.80                |
| Patch       | 9.80                | 38.20               |

**DenseNet-121 (Transferability):**

| Attack Type | Top-1 Accuracy (%) | Top-5 Accuracy (%) |
|-------------|---------------------|---------------------|
| FGSM        | 40.00               | 69.60               |
| PGD         | 32.20               | 68.20               |
| Patch       | 61.60               | 85.60               |

## 🖼️ Visual Examples

Each attack generates three visual outputs per image:
- Original image
- Adversarial image
- Normalized perturbation (Noise)

See:
- `fgsm_examples.png`
- `pgd_examples.png`
- `patch_examples.png`

## 📁 Repository Structure
Project3_code.ipynb ← Complete pipeline (baseline, FGSM, PGD, Patch, transfer)
Adversarial_Test_Set_1/ ← FGSM adversarial samples
Adversarial_Test_Set_2/ ← PGD adversarial samples
Adversarial_Test_Set_3/ ← Patch adversarial samples
TestDataSet/ ← Clean evaluation subset
synset_to_label.json ← Synset-to-ImageNet label mapping
baseline_accuracy.txt ← Clean model Top-1 and Top-5


## ⚙️ Dependencies

- Python 3.8+
- PyTorch ≥ 2.0
- torchvision
- matplotlib
- tqdm
- PIL

Install via pip:

```bash
pip install torch torchvision matplotlib tqdm pillow

👨‍💻 Authors

Jiale Cai, Yinuo Wang, Chen Yang
New York University — ECE 7123 Spring 2025
