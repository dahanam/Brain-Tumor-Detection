# Brain Tumor Detection

Deep learning models for binary classification of brain MRI scans — detecting the presence or absence of a tumor. Five model architectures are compared, with accuracy ranging from **75% to 90%**.

Presented at the **35th GMIS Conference (CAHSI)**, Kean University.  

---

## Models

| Model | Framework | Notes |
|---|---|---|
| VGG-16 | Keras/TF | Transfer learning with brain crop preprocessing |
| VGG-19 | Keras/TF | Deeper architecture; higher overfitting risk on small datasets |
| ResNet-50 | Keras/TF | Skip connections; strong generalization |
| EfficientNetB3 | TensorFlow | Most parameter-efficient |
| Custom CNN | Keras/TF | High-level API baseline |

Testing accuracy ranged from **75% to 90%** across all models.

---

## Dataset

**Brain MRI Images for Brain Tumor Detection** — Kaggle  
Two classes: `yes` (tumor present) · `no` (no tumor)

Dataset: [Kaggle — Brain MRI Images for Brain Tumor Detection](https://www.kaggle.com/datasets/navoneel/brain-mri-images-for-brain-tumor-detection)

---

## Notebook

`brain_tumor_detection.ipynb` — all 5 approaches in one merged notebook.

| Section | Description |
|---|---|
| 1. Setup | Installs, Drive mount, imports |
| 2. Load & Explore | Sample MRI grid, class counts |
| 3. Preprocessing | Brain crop pipeline with step-by-step visualization |
| 4. Shared Utilities | Confusion matrix and training curve helpers |
| 5. VGG-16 | With augmentation and early stopping |
| 6. VGG-19 | Pretrained ImageNet weights |
| 7. ResNet-50 | Pretrained ImageNet weights |
| 8. EfficientNetB3 | Categorical mode, Adamax optimizer |
| 9. Custom CNN (PyTorch) | 5-block grayscale architecture |
| 10. Inference | Single image prediction with confidence score |
| 11. Results Summary | Cross-model comparison |

---

## Preprocessing

MRI images are cropped to remove empty border space using contour detection before being fed into any model:

1. Convert to grayscale and apply Gaussian blur
2. Threshold + erode/dilate to remove noise
3. Find the largest contour (the brain)
4. Crop to the extreme points of that contour

This consistently improves model focus on relevant tissue.

---

## Setup

1. Open `brain_tumor_detection.ipynb` in Google Colab
2. Place dataset at `/content/drive/MyDrive/BTD_Notebook/brain_tumor_dataset/`
3. Run all cells top to bottom

**Note:** `.h5` and `.pth` model weight files are not included in this repo due to file size. They are saved locally when you run the notebook.

---

## Tech Stack

Python · TensorFlow · Keras · PyTorch · scikit-learn · OpenCV · Google Colab

---

## References

- [Brain MRI Dataset — Kaggle](https://www.kaggle.com/datasets/navoneel/brain-mri-images-for-brain-tumor-detection)
- [Keras Applications](https://keras.io/api/applications/)
- [Keras Pretrained Models — Kaggle](https://www.kaggle.com/datasets/gaborfodor/keras-pretrained-models)
