# 📌 Face Detection Project

## 📖 Overview

This project demonstrates **Face Detection and Object Detection** using various computer vision techniques. It uses **OpenCV**, **Haar Cascade Classifier**, and **Dlib (HOG & CNN)** to detect faces and other objects like eyes, cars, clocks, and full bodies in images.

The project also explains how images are processed at the pixel level and how features are extracted and matched for detection.

---

## 🎯 Objectives

* Understand image processing using pixel values (0–255)
* Perform face detection using Haar Cascade
* Detect facial features like eyes
* Explore detection parameters (scaleFactor, minNeighbors, etc.)
* Implement object detection (cars, clocks, full body)
* Compare different detection techniques:

  * Haar Cascade
  * HOG (Histogram of Oriented Gradients)
  * CNN (Deep Learning)

---

## 🛠️ Technologies Used

* Python
* OpenCV (`cv2`)
* Matplotlib
* Dlib
* NumPy

---

## 📂 Project Structure

```
Face-Detection/
│
├── Data Set/
│   ├── people1.jpg
│   ├── people2.jpg
│   ├── people3.jpg
│   ├── car.jpg
│   ├── clock.jpg
│
├── Cascades/
│   ├── haarcascade_frontalface_default.xml
│   ├── haarcascade_eye.xml
│   ├── cars.xml
│   ├── clocks.xml
│   ├── fullbody.xml
│
├── Weights/
│   ├── mmod_human_face_detector.dat
│
├── main.py
└── README.md
```

---

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/your-username/face-detection.git
cd face-detection
```

### 2. Install dependencies

```bash
pip install opencv-python matplotlib dlib numpy
```

---

## 🚀 How It Works

### 1. Image Processing

* Images are read using OpenCV
* Pixel values range from **0 (white) to 255 (black)**
* Images are converted:

  * BGR → RGB
  * RGB → Grayscale

### 2. Face Detection using Haar Cascade

* Pre-trained XML classifier is used
* Detects faces based on features
* Returns coordinates: `(x, y, width, height)`

```python
face_detector = cv2.CascadeClassifier('haarcascade_frontalface_default.xml')
detections = face_detector.detectMultiScale(image_gray)
```

---

## 🔍 Detection Parameters

### 🔹 scaleFactor

* Controls image scaling
* Smaller value → more accurate but slower

### 🔹 minNeighbors

* Reduces false positives
* Higher value → fewer but better detections

### 🔹 minSize & maxSize

* Defines object size range

---

## 👁️ Eye Detection

* Uses `haarcascade_eye.xml`
* Detects eyes within detected faces

---

## 🚗 Other Object Detection

### ✔ Car Detection

* Uses `cars.xml`

### ✔ Clock Detection

* Uses `clocks.xml`

### ✔ Full Body Detection

* Uses `fullbody.xml`

---

## 🧠 Advanced Techniques

### 🔹 HOG + Dlib

* Uses Histogram of Oriented Gradients
* Faster than CNN
* Good for real-time detection

```python
face_detector_hog = dlib.get_frontal_face_detector()
detections = face_detector_hog(image, 1)
```

---

### 🔹 CNN + Dlib

* Deep learning-based detection
* More accurate but slower
* Uses pre-trained model

```python
cnn_detector = dlib.cnn_face_detection_model_v1('mmod_human_face_detector.dat')
```

---

## 📊 Comparison of Methods

| Method       | Speed  | Accuracy | Use Case              |
| ------------ | ------ | -------- | --------------------- |
| Haar Cascade | Fast   | Medium   | Basic projects        |
| HOG          | Medium | Good     | Real-time apps        |
| CNN          | Slow   | High     | High accuracy systems |

---

## 🖼️ Output

* Faces and objects are detected and highlighted using rectangles
* Coordinates are printed for each detection

---

## 📌 Key Features

✔ Face Detection
✔ Eye Detection
✔ Car Detection
✔ Clock Detection
✔ Full Body Detection
✔ Multiple Algorithms (Haar, HOG, CNN)
✔ Parameter Tuning for Accuracy

---

## ⚠️ Limitations

* Haar Cascade may give false positives
* CNN model is slower and requires more resources
* Works best with clear images

---

## 📚 Future Improvements

* Real-time face detection using webcam
* Face recognition (identify person)
* Integration with deep learning frameworks (TensorFlow/PyTorch)
* Improve accuracy using custom-trained models

---

## 👨‍💻 Author

**Darshan Yalkar**
