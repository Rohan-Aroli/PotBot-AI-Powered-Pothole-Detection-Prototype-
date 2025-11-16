# 🚧 PotBot – AI-Powered Pothole Detection Prototype (Ongoing)

PotBot is an ongoing computer vision system designed to detect and analyze road potholes using **YOLO-based object detection**, **stereo vision depth estimation**, and **GPS-based geolocation tagging**. The long-term goal is to build a fully autonomous road-inspection device capable of mapping, reporting, and prioritizing pothole repair tasks for municipal authorities.

---

# 🧩 Project Architecture Overview

Below is the complete end-to-end pipeline showing how detection, depth estimation, GPS tagging, and reporting integrate into a single automated system:

![PotBot Architecture](https://github.com/Rohan-Aroli/PotBot-AI-Powered-Pothole-Detection-Prototype-/blob/main/assets/499813903-aa52fecf-c6e4-49fd-a77f-b189e25e06dd.png?raw=true)

---

# 🎥 Demo Output (Reference Video)

A sample detection video from the current prototype stage:

https://github.com/Rohan-Aroli/PotBot-AI-Powered-Pothole-Detection-Prototype-/blob/main/assets/pothole_output_simple.mp4

---

# 🧠 Project Description (Ongoing Work)

PotBot aims to build an **AI-driven road monitoring system** capable of automatically detecting potholes, estimating their severity through geometric depth analysis, and tagging their exact GPS coordinates for municipal reporting.

The current prototype:

- Uses **YOLOv8** to detect potholes in real-time  
- Calculates approximate depth/severity (planned via **stereo/monocular depth**)  
- Associates each detection with **GPS location metadata**  
- Logs detections into a **FastAPI backend** for centralized reporting  
- Stores structured detection data in **MongoDB** for analytics and future severity tracking  

This system is currently under development, with core detection functional and integration + automation underway.

---

# 🔄 Planned Full Flow (Detailed)

### **1. Video Capture**
- A vehicle-mounted camera (or smartphone) records the road surface.
- Frames are passed into the detection pipeline.

### **2. Real-Time Pothole Detection (Completed)**
- YOLOv8 model identifies pothole bounding boxes.
- Model used: **best.pt**  
  👉 Download: https://drive.google.com/file/d/1xzJNxZOIdpdozWMr9Vlb8x0blWOijdl-/view?usp=drive_link

### **3. Depth & Severity Estimation (In Progress)**
Two planned approaches:
- **Stereo Vision Depth** (dual-camera setup)
- **Monocular Depth Estimation** (MiDaS / DPT models)

Severity categories:
- Minor: < 3 cm  
- Moderate: 3–7 cm  
- Critical: > 7 cm  

### **4. GPS Coordinate Tagging (Planned)**
- GPS module or smartphone GPS logs coordinates
- Each detection is associated with a latitude/longitude pair

### **5. Cloud Upload (Planned)**
- FastAPI receives JSON reports:
  ```
  {
    "image_id": ...,
    "gps": { "lat": ..., "lng": ... },
    "severity": ...,
    "confidence": ...,
    "timestamp": ...
  }
  ```
- Stored in MongoDB for analysis

### **6. Reporting Dashboard (Planned)**
- A map showing all potholes detected  
- Severity color-coding  
- Auto-generated reports for municipal authorities  

---

# 🛠 Planned Hardware Stack

| Component | Purpose |
|----------|---------|
| **Raspberry Pi 4 / Jetson Nano** | Edge inference running YOLO |
| **Dual Camera Setup / Pi Cameras** | Stereo depth estimation |
| **GPS module (NEO-6M)** | Coordinate tagging |
| **Power Bank / Vehicle Power** | Field deployment |
| **Optional: IMU sensor** | Slope compensation |

The final goal is a **portable AI-powered pothole inspection unit** that can be mounted on:
- Bikes  
- Cars  
- Drones (future extension)  

---

# 🎯 Current Status
🟢 YOLO model trained  
🟢 Prototype video output generated  
🟡 Depth estimation in progress  
🟡 GPS tagging integration pending  
🔴 Full reporting dashboard in planning  

---

# 📥 Model Download
YOLO model (`best.pt`):  
https://drive.google.com/file/d/1xzJNxZOIdpdozWMr9Vlb8x0blWOijdl-/view?usp=drive_link

---

