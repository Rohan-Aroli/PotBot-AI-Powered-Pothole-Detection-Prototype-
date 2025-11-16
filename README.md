# 🕳️ PotBot – AI-Powered Pothole Detection & Severity Estimation System  
### *(Ongoing Project – Computer Vision + Stereo Depth + Geolocation + FastAPI Backend)*  

---

## 🧩 **Project Architecture Overview**
A high-level architecture diagram showing the complete planned pipeline can be viewed here:  
📌 **Architecture Image:**  
https://drive.google.com/file/d/1mWoFDJ442COOgtwaNZdPMP_I2RyniQRL/view?usp=drive_link  

---

## 🎥 **Demo / Reference Output**
You can watch the reference detection video here:  
📌 **Output Video:**  
https://drive.google.com/file/d/1ZVvBiK187UkO3EI_vcNbVqKvMKAh_wfU/view?usp=drive_link  

---

## 🎯 **Project Overview**

PotBot is an **AI-driven pothole detection and severity analysis system** currently under development.  
It uses **YOLO-based object detection**, **stereo-vision depth estimation**, and **GPS geolocation tagging** to automatically identify potholes on roads and forward structured reports to municipal authorities.

The goal is to build a **real-time, end-to-end road-monitoring pipeline** that drastically reduces manual inspection and accelerates road maintenance workflows for smart-city applications.

---

## 🚀 **Features (Planned + Implemented)**

### ✅ **Implemented**
- YOLO model trained for pothole detection  
- Real-time detection on video input  
- Extraction of bounding-box frames  
- Coordinate logging + preliminary severity mapping  
- FastAPI backend (initial version)  
- MongoDB as the central datastore  
- Video-based inference pipeline  

### 🔜 **In Progress / Upcoming**
- Stereo camera–based 3D depth estimation  
- Severity classification (shallow / medium / deep)  
- GPS automatic tagging from external module  
- Auto-report generator (PDF + JSON)  
- Web dashboard to visualize pothole map  
- Integration with municipal reporting portal  

---

## 🧠 **Model Download (best.pt)**  
Model weights are not uploaded to GitHub due to size limits.  
Download the trained YOLO weight file here:  

📌 **best.pt (YOLO Model):**  
https://drive.google.com/file/d/1xzJNxZOIdpdozWMr9Vlb8x0blWOijdl-/view?usp=drive_link  

Place it inside the `/model/` folder before running inference.

---

## 🔄 **Planned System Flow (Full Deep Breakdown)**

### **1️⃣ Video Capture / Camera Feed (Real-time or Offline)**  
PotBot accepts:  
- Real-time camera stream from a vehicle  
- Drone-mounted camera  
- Pre-recorded dashcam footage  

Frames are extracted at a fixed interval (≈ 15–30 FPS).

---

### **2️⃣ YOLO Detection Stage**  
Each frame is passed to a **YOLO model** specialized for pothole detection.  
Output includes:  
- Bounding box  
- Confidence score  
- Class label (“pothole”)  

This stage identifies *where* the pothole is in the frame.

---

### **3️⃣ Stereo-Depth Estimation (Planned)**  
Using a stereo camera pair, disparity maps will be generated.  
This gives:  
- Depth of pothole  
- Approx. volume  
- Severity class  
- Surface deviation map  

Depth calculation pipeline:  
`Disparity Map → Depth Calculation → Severity Classification`

---

### **4️⃣ GPS Mapping (Planned)**  
A GPS module will capture:  
- Latitude  
- Longitude  
- Timestamp  

This links each pothole to a **real-world road location**.

---

### **5️⃣ FastAPI Backend → MongoDB**  
All detection events are stored in MongoDB using a FastAPI service:  
- Image snapshot  
- Confidence  
- Severity rating  
- Geo-coordinates  
- Time of detection  

This creates a permanent searchable database.

---

### **6️⃣ Auto-Generated Pothole Report (Planned)**  
For municipal use, PotBot will generate:  
- Excel / JSON data tables  
- Severity distribution  
- Geo-pin map  
- Pothole IDs  
- Before–after repair tracking (future enhancement)

Reports will be exportable as:  
- PDF  
- JSON  
- CSV  

---

### **7️⃣ Smart Dashboard (Planned)**  
A future web dashboard will show:  
- Map with all detected potholes  
- Severity color codes  
- Timeline of detections  
- Map layers (heatmaps, clustering)  
- Playback of detection footage  

---

## 🧪 **Tech Stack**

### **AI & Computer Vision**
- YOLOv8  
- OpenCV  
- NumPy  

### **Backend**
- FastAPI  
- Python  
- MongoDB  

### **Planned Hardware**
- Raspberry Pi 4 or Jetson Nano  
- Stereo Camera (OV9281 / ZED Mini / Intel RealSense)  
- USB GPS module (NEO-6M)  
- Power bank + vehicle mount  
- 128GB storage  

---

## ▶️ **Running PotBot (Current Version)**

```
python detect.py --weights model/best.pt --source path/to/video.mp4
```

---

## ⭐ **Status**
🚧 **Ongoing development**  
More features being added every week.

---

## 🤝 Contributing  
Pull requests and suggestions for improvement are welcome!

