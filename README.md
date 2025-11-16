# 🚧 PotBot – AI-Powered Pothole Detection Prototype
*A stereo-vision + YOLO based pothole detection system with GPS logging and automated reporting.*

---

## 🧠 Project Architecture Overview

Below is the high-level architecture showing the complete data pipeline — from video capture → stereo depth estimation → YOLO inference → severity classification → GPS tagging → backend logging:

![Architecture](https://raw.githubusercontent.com/Rohan-Aroli/PotBot-AI-Powered-Pothole-Detection-Prototype-/main/assets/499813903-aa52fecf-c6e4-49fd-a77f-b189e25e06dd.png)

---

## 🎥 Demo Video

**YouTube (Recommended):**  
▶ https://youtu.be/8_DhqtXMx0E  

Demonstrates detection pipeline, bounding boxes, and the early-stage prototype workflow.

---

## 📹 Best.pt (model) output on a sample pothole video:  

[![PotBot Demo](https://img.youtube.com/vi/8_DhqtXMx0E/maxresdefault.jpg)](https://youtu.be/8_DhqtXMx0E)


---

## 🧩 Model Weights (YOLO)

Trained YOLO model (`best.pt`) is hosted externally due to GitHub size limits:

📦 Download best.pt – YOLO Weights  
https://drive.google.com/file/d/1xzJNxZOIdpdozWMr9Vlb8x0blWOijdl-/view?usp=drive_link

---

## 🚀 Project Description

PotBot is an **ongoing AI-based pothole detection and reporting system** designed to automate the identification of road damage using real-time computer vision. It leverages:

- **YOLO object detection** for identifying potholes  
- **Stereo-vision depth estimation** to calculate severity (depth & contour)  
- **GPS mapping** to accurately localize each pothole  
- **FastAPI backend** for structured reporting  
- **MongoDB database** for storing detection logs  

The prototype aims to **reduce manual road inspection**, improve municipal response time, and provide a scalable, automated road-health monitoring solution.

---

## 🔄 Planned Full System Flow (End-to-End)

### **1. Video Input Layer**
- Dual-camera setup (dashcam + stereo camera)
- Continuous road footage streamed to onboard processor
- Frame synchronization for stereo depth

### **2. Pre-Processing**
- Frame resizing, denoising  
- Stereo disparity computation → depth map creation  
- Temporal smoothing to reduce false positives  

### **3. YOLO-Based Detection**
- YOLO model identifies pothole region (bounding box + confidence)
- Non-max suppression to remove duplicates

### **4. Depth & Severity Estimation**
Severity = f(depth, area, contour sharpness)

- Depth via stereo disparity  
- Area via pixel-spread inside the bounding box  
- Severity categories (tentative):  
  - **Low**: <2 cm  
  - **Medium**: 2–5 cm  
  - **High**: >5 cm  

### **5. GPS Integration**
- Each detection is geotagged  
- Route-level aggregation for municipal use  
- Clustering of repeated potholes (future feature)

### **6. Backend Logging (FastAPI)**
- REST endpoints for:  
  - `/upload_detection`
  - `/get_report`
- Auto-generation of incident packets

### **7. Database Layer (MongoDB)**
Stores:
- Coordinates  
- Severity  
- Timestamp  
- Image/frame sample  
- Road segment ID  

### **8. Web Dashboard (Planned)**
- Map visualization  
- Severity heatmaps  
- Route-wise damage index  
- Downloadable CSV/PDF reports

---

## 🔧 Planned Hardware Specification

| Component | Purpose |
|----------|---------|
| **Stereo Camera (e.g., Intel RealSense / Zed Mini)** | Depth estimation & accurate severity measurement |
| **Dashcam (1080p/60fps)** | Wide-FOV visual input for YOLO detection |
| **Raspberry Pi 4 / Jetson Nano** | On-edge inference processing |
| **GPS Module (NEO-6M)** | Real-time geolocation tagging |
| **Power Bank / Vehicle Power Tap** | Continuous power supply |
| **Vibration-damped Mount** | Stable recording during motion |

**Note:** Stereo + dashcam combination is intentional — stereo provides depth accuracy, while dashcam provides high-quality RGB footage for YOLO inference.

---

## 🛠 Tech Stack

- **YOLO (Ultralytics)** – Object detection  
- **Stereo Vision / Disparity Mapping**  
- **OpenCV** – Image processing  
- **FastAPI** – Backend API  
- **MongoDB** – Detection logs  
- **Python** – Core logic  
- **Numpy / Pandas** – Pre-processing  

---

## 📌 Status  
🔧 **Work in Progress**  
The prototype demonstrates detection, but full integration (GPS, backend, stereo depth) is in active development.

---

