# Human Detection from Drone View
 
**Real-time aerial human detection using YOLOv5 Nano, optimized for Raspberry Pi and edge devices.**
 
---
 
## Overview
 
This project implements a lightweight human detection pipeline trained on aerial drone footage. Using **YOLOv5 Nano** and grayscale preprocessing, the system is designed for efficient real-time inference on resource-constrained hardware such as the Raspberry Pi.
 
The model was trained on the [VisDrone Dataset](https://github.com/VisDrone/VisDrone-Dataset) and fine-tuned specifically for aerial surveillance scenarios.
 
---
 
## Features
 
- Human detection from drone footage
- YOLOv5 Nano lightweight architecture
- Grayscale image preprocessing for reduced compute
- Raspberry Pi and edge-device compatible
- Real-time inference pipeline
---
 
## Technology Stack
 
| Technology | Purpose |
|---|---|
| Python 3.10 | Primary language |
| YOLOv5 Nano | Object detection model |
| OpenCV | Image processing |
| PyTorch | Deep learning framework |
| NumPy | Numerical computation |
| Google Colab | GPU-accelerated training |
 
---
 
## Dataset
 
**VisDrone Dataset**
Repository: https://github.com/VisDrone/VisDrone-Dataset
 
### Structure
 
```
dataset/
├── images/
│   ├── train/
│   └── val/
└── labels/
    ├── train/
    └── val/
```
 
---
 
## Model
 
### YOLOv5 Nano (YOLOv5n)
 
YOLOv5 Nano was selected for its balance of speed and accuracy on low-power hardware:
 
- Minimal memory footprint
- Fast inference on CPU
- Suitable for Raspberry Pi deployment
- Strong edge-device compatibility
### Grayscale Preprocessing
 
Drone frames are converted to grayscale prior to inference, reducing computational load while maintaining detection accuracy. Benefits include:
 
- Lower memory bandwidth usage
- Faster preprocessing pipeline
- Improved suitability for real-time edge deployment
---
 
## Project Structure
 
```
Human-Detection-from-drone-view/
├── dataset_sample/
├── outputs/
│   ├── result1.jpg
│   └── result2.jpg
├── screenshots/
│   ├── training_results.png
│   └── detection_output.png
├── models/
│   └── best.pt
├── detect.py
├── visdrone.yaml
├── requirements.txt
├── README.md
└── LICENSE
```
 
---
 
## Installation
 
### 1. Clone the Repository
 
```bash
git clone https://github.com/AarshK17/Human-Detection-from-drone-view.git
cd Human-Detection-from-drone-view
```
 
### 2. Install Dependencies
 
```bash
pip install -r requirements.txt
```
 
### Requirements
 
```
torch
opencv-python
numpy
matplotlib
PyYAML
tqdm
pandas
seaborn
```
 
---
 
## Usage
 
### Training
 
Train the model from scratch using the VisDrone dataset:
 
```bash
python train.py --img 640 --batch 16 --epochs 30 --data visdrone.yaml --weights yolov5n.pt
```
 
### Detection
 
Run inference on an image, video, or live camera feed:
 
```bash
# Image
python detect.py --weights models/best.pt --source path/to/image.jpg
 
# Video
python detect.py --weights models/best.pt --source path/to/video.mp4
 
# Webcam / live feed
python detect.py --weights models/best.pt --source 0
```
 
---
 
## Results
 
The trained model demonstrates reliable human detection from aerial imagery with inference speed suitable for edge deployment.
 
**Capabilities:**
 
- Single and multi-person detection
- Real-time inference on Raspberry Pi
- Lightweight deployment via YOLOv5 Nano
---
 
## Raspberry Pi Deployment
 
The inference pipeline is configured for Raspberry Pi using:
 
- YOLOv5 Nano weights (`best.pt`)
- OpenCV for frame capture and rendering
- Grayscale preprocessing to reduce CPU load
- Lightweight inference loop without GPU dependency
---
 
## Roadmap
 
- Thermal camera integration
- Live drone feed support
- GPS-based human tracking
- Emergency alert system
- TensorRT / ONNX optimization for faster inference
- Autonomous drone navigation integration
---
 
## Acknowledgements
 
- [Ultralytics YOLOv5](https://github.com/ultralytics/yolov5)
- [VisDrone Dataset](https://github.com/VisDrone/VisDrone-Dataset)
- OpenCV and PyTorch communities
---
 
## Author
 
**Aarsh Khadgi**
GitHub: https://github.com/AarshK17
Project: https://github.com/AarshK17/Human-Detection-from-drone-view
