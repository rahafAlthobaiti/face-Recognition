# 👤 Face Recognition with OpenCV and Python

A simple and effective face recognition system built using OpenCV and Python. This project demonstrates how to train a facial recognition model on a custom dataset and recognize faces in real-time using a webcam.

---

## 🎯 Objectives

This project was created to:

- Build a face dataset organized by person name 
- Train a recognition model using the LBPH algorithm in OpenCV 
- Detect and identify faces in live video 
- Adjust recognition sensitivity based on confidence scores 
- Practice packaging and documenting an AI project

---

## 🧠 Overview

The core of this project is a single script: `face_recognition_project.py`, which supports two main modes:

- `train`: Loads all face images from `datasets/`, trains the LBPH model, and saves it as `trainer.yml`. It also creates a `labels.npy` file to map numeric IDs to names. 
- `recognize`: Starts the webcam, detects faces using Haar cascade, and uses the trained model to recognize them in real-time.

---

## 🧰 Technologies Used

- 🧠 OpenCV (LBPH Face Recognizer) 
- 🧮 NumPy 
- 📂 Haarcascade XML for face detection 
- 💻 Python 3.x 
- 🖥️ VS Code 
- ⚙️ Compatible with Windows, Linux, and macOS 

---

## 🧪 How It Works

### 📁 1. Dataset Preparation

- Create a folder called `datasets/` 
- Inside, create one folder per person. Each folder name is used as the person's label. 
- Place multiple images of the same person in their respective folder.

Example structure:
datasets/
├── Layla/
│ ├── 1.jpg
│ ├── 2.jpg
├── Omar/
│ ├── 1.jpg
│ ├── 2.jpg

---

### 🧠 2. Model Training

The script uses OpenCV’s `cv2.face.LBPHFaceRecognizer_create()` to train a model:

- All images are read in grayscale 
- Each face is associated with a label (based on folder name) 
- The model is saved as `trainer.yml` 
- A mapping of labels to names is saved in `labels.npy`

---

### 🎥 3. Real-Time Recognition

- Webcam feed is read frame-by-frame 
- Faces are detected using Haar cascade 
- Each detected face is passed to the recognizer 
- The model returns a label and confidence score

If confidence is **below 60**, the name is shown in green. 
If confidence is **60 or higher**, it's treated as "Unknown" and shown in red.

To adjust the strictness, change this line in code:

```python
if confidence < 60:
## 🚀 How to Run

```bash
# Step 1: Clone this repository
git clone https://github.com/rahafAlthobaiti/face-Recognition/tree/main

# Step 2: Install dependencies
pip install -r requirements.txt

# Step 3: Train on your dataset
python face_recognition_project.py --mode train

# Step 4: Start live recognition
python face_recognition_project.py --mode recognize

