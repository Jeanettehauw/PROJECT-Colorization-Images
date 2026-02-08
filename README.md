# Image Colorization Using Deep Learning (UNet-based Architectures)

This project implements an automatic image colorization system using deep learning. The task aims to restore color information from grayscale images by learning a mapping between grayscale and color image pairs using supervised learning.

The project was originally developed as a final project for the Computer Vision course and later extended to compare multiple pretrained encoder architectures combined with a UNet-style decoder.
https://github.com/angelous/Color-Restoration

---

## Objectives
- Perform image colorization using supervised deep learning
- Compare multiple pretrained encoders: VGG16, ResNet18, and DenseNet121
- Use a unified UNet decoder for fair comparison
- Evaluate model performance using PSNR and SSIM
- Analyze overfitting using training and validation loss curves

---

## Dataset
The dataset used in this project is the Image Colorization Dataset from Kaggle:

https://www.kaggle.com/datasets/aayush9753/image-colorization-dataset

### Dataset Description
- Training data:
  - 5,000 grayscale images (train_black)
  - 5,000 corresponding color images (train_color)
- Test data:
  - 739 grayscale images (test_black)
  - 739 corresponding color images (test_color)

Each grayscale image has a corresponding color image, enabling supervised learning for image-to-image translation.

### Validation Set
To monitor generalization and reduce overfitting, 50% of the test set is used as a validation dataset. The validation set is used for:
- Early stopping
- Model selection
- Monitoring training stability

---

## Model Architectures
All models follow a UNet-based encoder–decoder architecture with different pretrained encoders:

- VGG UNet (VGG16 encoder)
- ResNet UNet (ResNet18 encoder)
- DenseNet UNet (DenseNet121 encoder)

Channel adaptation layers (1×1 convolutions) are applied to align feature dimensions across skip connections, ensuring a fair comparison between models.

---

## Evaluation Metrics
The models are evaluated using:
- PSNR (Peak Signal-to-Noise Ratio)
- SSIM (Structural Similarity Index)

Both quantitative metrics and qualitative visual comparisons are provided.
