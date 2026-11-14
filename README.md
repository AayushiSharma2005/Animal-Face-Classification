# 🐾 Animal Face Classification using Deep Learning

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.x-blue?logo=python" />
  <img src="https://img.shields.io/badge/PyTorch-Deep%20Learning-orange?logo=pytorch" />
  <img src="https://img.shields.io/badge/Computer%20Vision-Image%20Classification-green" />
  <img src="https://img.shields.io/badge/Platform-Kaggle-20BEFF?logo=kaggle" />
</p>

## 📌 Project Overview

This project implements a deep learning based image classification system using **PyTorch** and the **Animal Faces HQ (AFHQ)** dataset.

The objective is to classify animal face images into three categories:

- 🐱 Cat
- 🐶 Dog
- 🐯 Wild

Two models were developed and compared:

1. Custom Convolutional Neural Network (CNN)
2. ResNet18 using Transfer Learning

## 📂 Dataset

The project uses the AFHQ dataset, containing three animal categories.

| Class | Number of Images |
|---|---:|
| 🐱 Cat | 5,653 |
| 🐶 Dog | 5,239 |
| 🐯 Wild | 5,238 |
| **Total** | **16,130** |

The provided training folder was divided into training and internal validation subsets using stratified sampling.

The official validation folder was reserved for final model evaluation.

| Split | Images |
|---|---:|
| Training | 12,435 |
| Internal Validation | 2,195 |
| Official Validation | 1,500 |

## 🛠️ Technologies Used

- 🐍 Python
- 🔥 PyTorch
- 🖼️ Torchvision
- 🔢 NumPy
- 📊 Pandas
- 📈 Matplotlib
- 🤖 Scikit-learn
- ☁️ Kaggle Notebooks
- ⚡ NVIDIA Tesla T4 GPU

## 🧹 Data Preprocessing

Images were resized to **224 × 224 pixels**.

Training data augmentation included:

- Random horizontal flipping
- Random rotation
- Color jitter

Images were converted into tensors and normalized using ImageNet mean and standard deviation values.

Evaluation images used resizing and normalization without random augmentation.

## 🧠 Model Architectures

### 1. Custom CNN

A custom convolutional neural network was implemented with four convolutional blocks.

The architecture includes:

- Convolutional layers
- Batch normalization
- ReLU activation
- Max pooling
- Adaptive average pooling
- Fully connected layers
- Dropout regularization

### 2. ResNet18 Transfer Learning

A ResNet18 model pretrained on ImageNet was used.

The original classification layer was replaced with a new classification head containing dropout and a fully connected layer for the three target classes.

The model was fine-tuned on the AFHQ dataset.

## ⚙️ Training Configuration

| Parameter | Value |
|---|---|
| Image Size | 224 × 224 |
| Batch Size | 32 |
| Optimizer | AdamW |
| Loss Function | Cross Entropy Loss |
| CNN Learning Rate | 0.001 |
| ResNet18 Learning Rate | 0.0001 |
| Epochs | 5 per model |
| Random Seed | 42 |
| Hardware | NVIDIA Tesla T4 |

## 📊 Model Evaluation

Both models were evaluated on the 1,500 images in the official validation folder.

The following metrics were calculated:

- Accuracy
- Macro Precision
- Macro Recall
- Macro F1 Score

### 🏆 Performance Comparison

| Metric | Custom CNN | ResNet18 |
|---|---:|---:|
| Accuracy | 83.93% | **99.73%** |
| Precision | 86.36% | **99.74%** |
| Recall | 83.93% | **99.73%** |
| Macro F1 Score | 84.04% | **99.73%** |

**ResNet18 achieved the best overall performance**, correctly classifying 1,496 out of 1,500 evaluation images.

## 🔍 Results and Observations

The experimental results show that ResNet18 significantly outperformed the custom CNN.

Transfer learning helped the model learn useful visual representations and achieve strong classification performance across all three animal categories.

The notebook also includes:

- Training and validation curves
- Confusion matrices
- Classification reports
- Single-image prediction

## 💾 Model Files

The repository includes the trained model weights:

- `ResNet18_final.pth`
- `CustomCNN_final.pth`

Additional files include:

- `class_names.json`
- `model_comparison.csv`

## 🚀 How to Run

1. Open the notebook in Kaggle or Google Colab.
2. Attach or upload the AFHQ dataset.
3. Update the dataset path to match your environment.
4. Install the required dependencies if they are not already available.
5. Run the notebook cells in order.

For inference using saved ResNet18 weights, recreate the same ResNet18 architecture and classification head before loading the state dictionary.

## 🔮 Future Improvements

- Add Grad-CAM visualizations for model interpretability.
- Experiment with additional pretrained architectures.
- Perform hyperparameter optimization.
- Develop a web-based image classification interface.
- Explore model deployment using FastAPI.

## 👨‍💻 Author

**Machine Learning and Deep Learning Project**

Framework: PyTorch

Dataset: Animal Faces HQ (AFHQ)

---

⭐ If you find this project interesting, feel free to explore the notebook and its implementation.
