# Deep Learning Project: Adversarial Attacks and Transferability on ResNet-34 and DenseNet-121

This project investigates the vulnerability of deep convolutional image classifiers to adversarial examples. We apply three popular attack methods—FGSM, PGD, and patch-based attacks—on a pre-trained ResNet-34 model and evaluate the transferability of these adversarial inputs to a different architecture: DenseNet-121.

## 🧪 Attack Overview

| Attack Type | ε       | Iterations | Region        | Norm     |
|-------------|----------|------------|----------------|----------|
| FGSM        | 0.02     | 1          | Whole image    | $L_\infty$ |
| PGD         | 0.02     | 10         | Whole image    | $L_\infty$ |
| Patch       | 0.4  | 30         | 32×32 patch    | $L_0$      |

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
| PGD         | 32.00               | 68.40               |
| Patch       | 61.60               | 85.60               |

## 🖼️ Visual Examples

Each attack generates three visual outputs per image:
- Original image
- Adversarial image
- Normalized perturbation (Noise)

See:
- `fgsm_examples.jpg`
- `pgd_examples.jpg`
- `patch_examples.jpg`

## 📁 Files
Project3_code.ipynb ← Complete pipeline (baseline, FGSM, PGD, Patch, transfer)\


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
```

👨‍💻 Authors

Jiale Cai, Yinuo Wang, Chen Yang
New York University — ECE 7123 Spring 2025
