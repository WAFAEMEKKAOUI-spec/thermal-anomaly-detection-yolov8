# Deep Learning-Based Thermal Anomaly Detection using YOLOv8

## Overview
This project presents a deep learning framework for thermal anomaly detection using the YOLOv8 object detection model. The system is designed to identify and localize objects and thermal targets in infrared imagery under low-contrast and challenging environmental conditions.

Thermal imaging is widely used in industrial monitoring, surveillance, predictive maintenance, autonomous systems, and safety inspection because it can detect heat signatures even in dark or low-visibility environments. However, thermal images usually contain low texture information, blurred object boundaries, and noise, making object detection significantly more difficult than standard RGB image detection.

To address these challenges, this project uses YOLOv8 as a lightweight and real-time object detector capable of detecting thermal objects efficiently while maintaining high inference speed.

---

## Dataset
The model was trained using the Thermal Images Dataset from Roboflow Universe.

Dataset link:  
https://universe.roboflow.com/work-xhd82/thermal-images-gdyqo/dataset/2

The dataset contains annotated infrared thermal images with bounding box labels for multiple object categories including:

- Person
- Car
- Truck
- Bus
- ATV
- Motorcyclist
- Utility Truck
- Small Bus
- Buggy
- Other thermal targets

The dataset includes images collected under different environmental conditions and viewing distances to improve model robustness and generalization.

---

## Objectives
The main objectives of this project are:

- Develop a real-time thermal object detection system
- Evaluate YOLOv8 performance on infrared imagery
- Detect low-contrast thermal targets accurately
- Achieve fast inference speed suitable for edge devices
- Build a baseline framework for future thermal anomaly research

---

## Technologies Used

- Python
- YOLOv8
- Ultralytics
- OpenCV
- PyTorch
- Roboflow
- Kaggle Notebook Environment

---

## Model Architecture
This project uses the YOLOv8 architecture provided by Ultralytics. YOLOv8 is a one-stage object detector known for its high speed and strong detection performance.

Key features include:

- Anchor-free detection
- Decoupled detection head
- Multi-scale feature extraction
- Real-time inference capability
- Lightweight deployment support

The YOLOv8n model variant was selected due to its balance between computational efficiency and detection accuracy.

---

## Data Preprocessing
Several preprocessing and augmentation techniques were applied before training:

- Image resizing
- Normalization
- Horizontal flipping
- Contrast enhancement
- Data augmentation
- Auto-orientation

These methods improve model generalization and robustness against varying thermal conditions.

---

## Training Configuration

| Parameter | Value |
|---|---|
| Model | YOLOv8n |
| Epochs | 10 |
| Image Size | 640 |
| Batch Size | 8 |
| Framework | Ultralytics YOLOv8 |
| GPU | NVIDIA Tesla T4 |

---

## Evaluation Metrics
The model was evaluated using standard object detection metrics:

- Precision
- Recall
- mAP@0.5
- mAP@0.5:0.95

### Results

| Metric | Score |
|---|---|
| Precision | 0.926 |
| Recall | 0.883 |
| mAP@0.5 | 0.919 |
| mAP@0.5:0.95 | 0.707 |

The model achieved strong detection performance while maintaining fast inference speed suitable for real-time applications.

---

## Project Structure

```bash
thermal-anomaly-detection/
│
├── notebooks/
│   └── thermal_detection.ipynb
│
├── results/
│   ├── confusion_matrix.png
│   ├── results.png
│   ├── PR_curve.png
│   └── sample_predictions.png
│
├── models/
│   └── best.pt
│
├── README.md
└── requirements.txt
