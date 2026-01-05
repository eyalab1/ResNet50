# 🌍 Scene Classification using ResNet50 (Transfer Learning)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/eyalab1/ResNet50/blob/main/ResNet50.ipynb)
![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![PyTorch](https://img.shields.io/badge/Framework-PyTorch-red)
![Deep Learning](https://img.shields.io/badge/Skill-Transfer%20Learning-orange)

## 📌 Project Overview
This project demonstrates a **Computer Vision** pipeline for scene classification.
I utilized **Transfer Learning** with the **ResNet50** architecture (pre-trained on ImageNet) to classify images into **6 distinct categories** of natural and urban scenery.

The challenge was to distinguish between visually similar classes (such as *Glacier vs. Mountain* or *Street vs. Buildings*) using a relatively small dataset.

## 📂 Dataset: Intel Image Classification
* **Source:** [Intel Image Classification (Kaggle)](https://www.kaggle.com/datasets/puneet6060/intel-image-classification)
* **Task:** Multi-class classification of 6 scene types:
  * 🏢 **Buildings**
  * 🌲 **Forest**
  * ❄️ **Glacier**
  * 🏔️ **Mountain**
  * 🌊 **Sea**
  * 🛣️ **Street**

## ⚙️ Methodology

### Architecture
* **Base Model:** ResNet50 (Pre-trained on ImageNet).
* **Strategy:** I froze the feature extraction layers and replaced the final Fully Connected (FC) head to map to the 6 target classes.
* **Fine-Tuning:** Unfroze the last convolutional block to adapt the high-level features to the specific textures of the dataset.

### Key Steps
1.  **Preprocessing:** Resized all images to **224x224** and applied normalization (Mean/Std) matching ImageNet statistics.
2.  **Data Augmentation:** Used `RandomHorizontalFlip`, `RandomRotation`, and `ColorJitter` to improve robustness.
3.  **Training:** Optimized using **Adam** with a learning rate scheduler to converge smoothly.

## 📊 Results
The model achieved an impressive **92.70% accuracy** on the test set.

| Metric | Score |
| :--- | :--- |
| **Test Accuracy** | **92.70%** |
| **Weighted F1 Score** | **0.93** |
| **Precision** | **0.93** |

### Insights
* 🌲 **Best Performance:** The model achieved **99% F1-score** on the **Forest** class.
* ❄️ **Challenging Cases:** The **Glacier** class had a lower score (87%), likely due to visual similarities with the **Mountain** class.

## 🚀 How to Run
1.  Click the **"Open in Colab"** badge above.
2.  The notebook will download the dataset directly using the Kaggle API.
3.  Run all cells to train the model or load weights.

---
*Created by [Eyal Abisdris](https://github.com/eyalab1)*
