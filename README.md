```markdown
# ISIC Skin Classification

A multi-class skin lesion classification project using deep learning and dermoscopic images. This project compares a custom CNN trained from scratch against three ImageNet-pretrained transfer-learning architectures.

## Project Overview

The objective is to classify dermoscopic images into **nine skin lesion categories** using PyTorch.

Four architectures were implemented and evaluated:

- BaseCNN (trained from scratch)
- ResNet50
- EfficientNet-B0
- DenseNet121

## Dataset

The project uses an ISIC-based skin lesion dataset.

- Original training images: 2,239
- Test images: 118
- Valid training-pool images after excluding one corrupted image: 2,238
- Training split: 1,790 images
- Validation split: 448 images
- Number of classes: 9

### Classification Categories

1. Actinic Keratosis
2. Basal Cell Carcinoma
3. Dermatofibroma
4. Melanoma
5. Nevus
6. Pigmented Benign Keratosis
7. Seborrheic Keratosis
8. Squamous Cell Carcinoma
9. Vascular Lesion

## Methodology

The project follows these main stages:

1. Image preprocessing and resizing to 224 × 224.
2. Stratified 80:20 training-validation split using random seed 42.
3. ImageNet normalization and data augmentation.
4. Class-weighted cross-entropy to address class imbalance.
5. Training and fine-tuning of four CNN architectures.
6. Evaluation on a separate held-out test set.

### Model Architectures

| Model | Training Approach |
|---|---|
| BaseCNN | Trained from scratch |
| ResNet50 | ImageNet transfer learning |
| EfficientNet-B0 | ImageNet transfer learning |
| DenseNet121 | ImageNet transfer learning |

## Results

Performance on the held-out test dataset:

| Model | Accuracy (%) | Precision (%) | Recall (%) | F1 (%) | ROC-AUC (%) |
|---|---:|---:|---:|---:|---:|
| BaseCNN | 43.22 | 48.85 | 50.46 | 45.40 | 84.76 |
| ResNet50 | 61.02 | 62.41 | 62.04 | 59.96 | 91.70 |
| EfficientNet-B0 | 61.02 | 62.28 | 62.05 | 60.88 | 91.67 |
| DenseNet121 | 59.32 | 63.13 | 65.66 | 62.78 | 91.97 |

DenseNet121 achieved the highest recall, precision, F1 score, and ROC-AUC among the evaluated models. ResNet50 and EfficientNet-B0 achieved the highest test accuracy.

## Technologies Used

- Python
- PyTorch
- Torchvision
- NumPy
- Pandas
- Matplotlib
- Scikit-learn
- Google Colab
- NVIDIA Tesla T4 GPU

## Repository Contents

- `ADLProject.ipynb` — Complete implementation, training, and evaluation.
- `ISIC_Skin_Lesion_Classification_Project_Report.pdf` — Detailed project report, methodology, results, and analysis.

## Limitations

- Relatively small dataset compared with the complete ISIC 2019 dataset.
- Class imbalance across diagnostic categories.
- Only three test images each for Seborrheic Keratosis and Vascular Lesion.
- Image-level splitting may allow images from the same lesion to occur in different subsets.
- No ensemble learning or clinical metadata was incorporated.

## Future Work

- Experiment with larger datasets and higher image resolutions.
- Implement lesion-level data splitting.
- Explore focal loss and other class-balancing techniques.
- Investigate ensemble architectures.
- Incorporate Grad-CAM for model explainability.
- Perform external validation on an independent dataset.

## Disclaimer

This project is an academic deep learning experiment and is not intended for clinical diagnosis or medical decision-making.
```
