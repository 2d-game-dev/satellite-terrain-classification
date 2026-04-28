# 🌍 Satellite Image Classification using CNN (PyTorch)

## 📌 Overview

This project implements a **Convolutional Neural Network (CNN)** from scratch using PyTorch to classify satellite images into four categories:

* 🌵 Desert
* 🌊 Water
* 🌿 Green Area
* ☁️ Cloudy

The model is trained with a **train/validation/test split**, and performance is monitored using both **accuracy** and **loss curves**.

---

## 🚀 Features

* Custom CNN architecture (built from scratch)
* GPU support using CUDA
* Train / Validation / Test split (70 / 15 / 15)
* Real-time training progress with `tqdm`
* Training vs Validation loss visualization 📈
* Final test accuracy evaluation
* Interactive demo with prediction + confidence score

---

## 🧠 Model Architecture

The CNN consists of:

* 3 Convolutional Layers:

  * `3 → 32 → 64 → 128`
* Batch Normalization after each conv layer
* ReLU activation
* Max Pooling (downsampling)
* Dropout (0.3) to reduce overfitting
* Fully Connected Layers:

  * `128 × 30 × 30 → 256 → 4 classes`

---

## ⚙️ Tech Stack

* Python 🐍
* PyTorch 🔥
* Torchvision
* NumPy
* Matplotlib
* tqdm

---

## 📂 Dataset Structure

Dataset follows `ImageFolder` format:

```
satellite/data/
│
├── desert/
├── water/
├── green_area/
└── cloudy/
```

Each folder contains images of the corresponding class.

---

## 🔄 Data Preprocessing

* Images resized to **240 × 240**
* Converted to tensors
* Normalized using:

  * Mean: `[0.485, 0.456, 0.406]`
  * Std: `[0.229, 0.224, 0.225]`

---

## 🏋️ Training Details

* Loss Function: `CrossEntropyLoss`
* Optimizer: `Adam`
* Learning Rate: `0.001`
* Scheduler: StepLR (decays every 3 epochs)
* Batch Size: `16`
* Epochs: `7`

---

## 📊 Training Monitoring

The model tracks both:

* Training Loss
* Validation Loss

These are plotted after training:

📈 **Training vs Validation Loss Curve**

This helps detect:

* Overfitting
* Underfitting
* Generalization performance

---

## 📈 Results

* ✅ Test Accuracy: ~91%
* 📉 Stable decreasing training & validation loss
* ✔️ No signs of overfitting
* ✔️ Good generalization to unseen data

---

## 🎮 Interactive Demo

After training, the model allows a simple interaction:

### Input:

```
desert / water / green_area / cloudy
```

### Output:

* Displays a random image from that class
* Predicts using trained model
* Shows confidence score

Example:
<img width="389" height="389" alt="random_desert_image" src="https://github.com/user-attachments/assets/f96cdaa0-626d-409e-8dd9-ba9bf7fe94b9" />
```
🖼️ Showing image from class: desert  
🤖 Model prediction: desert (93.45% confidence)
```

---

## ▶️ How to Run

1. Upload dataset:

```
satelliteImages.zip
```

2. Run the notebook in Google Colab:

* Extract dataset
* Train model
* View loss graph
* Check test accuracy
* Try interactive prediction

---

## 💡 Key Learnings

This project demonstrates:

* End-to-end computer vision pipeline
* CNN architecture design from scratch
* Importance of normalization
* Batch training and optimization
* Validation-based overfitting detection
* Model evaluation on unseen data

---

## 🔮 Future Improvements

* Data augmentation (flip, rotation, zoom)
* Transfer learning (ResNet, EfficientNet)
* Confusion matrix for error analysis
* Upload custom image for prediction
* Deploy as web app (Flask / FastAPI)

---

## 👨‍💻 About This Project

This project was built as a **self-learning exercise** to understand computer vision fundamentals and improve practical deep learning skills.

