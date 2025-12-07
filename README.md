<div align="center">

# 🎭 Face Recognition System
### *Classical Computer Vision Pipeline*

**MediaPipe Face Detection** × **LBPH Feature Recognition**

---

[![Python](https://img.shields.io/badge/Python-3.7+-blue.svg)](https://www.python.org/)
[![OpenCV](https://img.shields.io/badge/OpenCV-4.0+-green.svg)](https://opencv.org/)
[![MediaPipe](https://img.shields.io/badge/MediaPipe-Latest-orange.svg)](https://mediapipe.dev/)

</div>

---

## 🚀 What is This?

A **zero machine learning** face recognition system built entirely with traditional computer vision algorithms. Perfect for understanding the fundamentals before diving into deep learning!

> 💡 **Core Concept**: Combines Google's MediaPipe for robust face detection with OpenCV's Local Binary Patterns Histograms (LBPH) for facial feature extraction and matching.

---

## ✨ Key Features

| Feature | Description |
|---------|-------------|
| 🎯 **No ML Required** | Pure computer vision - no neural networks needed |
| 📸 **Live Detection** | Real-time face recognition from webcam feed |
| 👥 **Multi-Person** | Train and recognize unlimited individuals |
| ⚡ **Fast Processing** | Lightweight algorithms for quick inference |
| 🎨 **Visual Feedback** | Annotated video with confidence scores |

---

## 📦 Quick Start

### Prerequisites

```bash
# Install core dependencies
pip install opencv-python mediapipe

# Install OpenCV contrib package (includes LBPH)
pip install opencv-contrib-python
```

### 🏗️ Project Architecture

```plaintext
📁 face-recognition/
│
├── 📜 capture.py          → Data collection module
├── 📜 train.py            → Model training pipeline  
├── 📜 predict.py          → Real-time recognition engine
│
├── 📂 dataset/            → Face image storage
│   └── 📂 [person_name]/  → Individual face samples
│
└── 📂 models/             → Trained model artifacts
    ├── lbph_model.xml     → LBPH classifier weights
    └── label_map.json     → Name-to-label mapping
```

---

## 🎯 How To Use

### 🔸 Phase 1: Capture Training Data

Launch the capture module to collect face samples:

```bash
python capture.py
```

**Interactive Steps:**
1. Enter the person's name when prompted
2. Look at the camera and move your head slightly
3. Press **Q** to finish capturing (~30-100 samples recommended)
4. Images auto-save to `dataset/<name>/`

---

### 🔸 Phase 2: Train Recognition Model

Build the LBPH classifier from captured data:

```bash
python train.py
```

**Output Files:**
- `models/lbph_model.xml` - Trained face recognizer
- `models/label_map.json` - Identity labels

---

### 🔸 Phase 3: Recognize Faces

Run the recognition system on live video:

```bash
python predict.py
```

**Live Display:**
- ✅ Green bounding box around detected faces
- 🏷️ Predicted identity label
- 📊 Confidence score (lower = better match)

Press **Q** to exit the application.

---

## 🔄 Recognition Pipeline

```mermaid
graph LR
    A[📹 Video Input] --> B[MediaPipe Detection]
    B --> C[Extract Face ROI]
    C --> D[LBPH Feature Extraction]
    D --> E[Compare with Trained Model]
    E --> F[🎯 Identity + Confidence]
```

---

## 🧠 Technical Details

**MediaPipe Face Mesh**
- Detects faces in real-time using pre-built detectors
- Provides 468 facial landmarks (not fully utilized here)
- Fast and robust to various lighting conditions

**LBPH Algorithm**
- Divides face into local regions
- Computes binary patterns for texture analysis
- Creates histogram-based feature representation
- Compares test faces against trained histograms

---

## 🔧 Tips & Best Practices

- ✅ Capture faces in various lighting conditions
- ✅ Include different facial expressions
- ✅ Capture at least 50+ images per person for better accuracy
- ✅ Retrain the model when adding new people
- ⚠️ LBPH works best with consistent lighting
- ⚠️ Performance degrades with significant pose variation

---

## 🎓 Educational Purpose

This project demonstrates **classical AI techniques** without relying on modern deep learning. It's ideal for:

- Understanding computer vision fundamentals
- Learning about traditional feature extraction
- Comparing classical vs. deep learning approaches
- Academic assignments focusing on non-ML algorithms

---

## 📝 Workflow Summary

```plaintext
1️⃣ Capture → Collect face images for each person
2️⃣ Train   → Generate LBPH model from dataset
3️⃣ Predict → Recognize faces in real-time

🔁 Repeat as needed to expand your recognition database!
```

---

<div align="center">

**Built with** 💻 **by Computer Vision Enthusiasts**

*No neural networks were harmed in the making of this project* 😄

</div>
