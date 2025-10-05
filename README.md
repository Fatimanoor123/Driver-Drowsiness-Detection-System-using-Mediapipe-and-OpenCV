
# 🚗 Driver Drowsiness Detection using MediaPipe & OpenCV

## 📘 Overview
This project detects driver drowsiness using **MediaPipe Face Mesh** and **OpenCV**.  
It tracks the driver’s **eye aspect ratio (EAR)** — when the eyes remain closed for too long, the system detects drowsiness.

The output video is processed frame-by-frame, and an alert message is triggered when drowsiness is detected.  
The project is implemented in **Google Colab** and saves the output video directly to Google Drive.

---

## 🎯 Objective
To ensure **road safety** by detecting if a driver is becoming sleepy or inattentive while driving.  
This project can be extended into a real-time in-vehicle monitoring system.

---

## 🧠 How It Works
1. The system captures video input (uploaded by user).
2. **MediaPipe Face Mesh** detects facial landmarks around the eyes.
3. The **Eye Aspect Ratio (EAR)** is calculated using key eye landmark distances.
4. If the EAR value stays below a threshold for a certain number of frames, the driver is classified as **drowsy**.
5. The processed video is saved with alert annotations.

---

## ⚙️ Features
✅ Real-time facial landmark detection with MediaPipe  
✅ Eye Aspect Ratio (EAR) based drowsiness detection  
✅ Automatic alert overlay on drowsy frames  
✅ Saves output video to Google Drive  

---

## 🧩 Requirements

Install dependencies in Google Colab:

```bash
!pip install opencv-python mediapipe numpy scipy
```

Import libraries:

```python
import cv2
import mediapipe as mp
import numpy as np
from scipy.spatial import distance as dist
```

---

## 📂 Folder Structure
```
Driver-Monitoring-System-YOLOv8/
│
├── drowsiness_detection.ipynb    # Main Colab Notebook
├── driver_drowsiness_input.mp4   # Input video (user-provided)
├── driver_drowsiness_output.mp4  # Output video (saved in Drive)
└── README.md                     # Documentation file
```

---

## 🚀 Steps to Run in Colab

1. Mount your Google Drive:
   ```python
   from google.colab import drive
   drive.mount('/content/drive')
   ```

2. Upload your input video to your Drive folder, e.g.:
   ```
   /content/drive/MyDrive/AI ML Projects/Driver-Monitoring-System-YOLOv8/driver_drowsiness_input.mp4
   ```

3. Run the detection code.  
   The output video will be automatically saved as:
   ```
   /content/drive/MyDrive/AI ML Projects/Driver-Monitoring-System-YOLOv8/driver_drowsiness_output.mp4
   ```

---

## 📊 Results
- Detects and highlights **drowsy driver moments**.  
- Annotates the video with alerts (“Drowsiness Detected”).  
- Saves the processed video automatically to Google Drive.
<img width="1121" height="1020" alt="image" src="https://github.com/user-attachments/assets/42f7de8f-917a-4431-a712-56d119b23475" />

---

## 🧩 Formula Used — Eye Aspect Ratio (EAR)
The EAR is calculated using the Euclidean distance between eye landmarks:

\(
EAR = rac{||p2 - p6|| + ||p3 - p5||}{2 * ||p1 - p4||}
\)

If EAR < 0.25 for several frames, drowsiness is detected.

---

## 🧭 Future Directions
🔹 Combine with **YOLOv8** for mobile phone + drowsiness multi-detection.  
🔹 Add **audio alerts** for real-time feedback.  
🔹 Integrate into a **desktop or mobile app** for driver safety monitoring.  
🔹 Train a model to detect **yawning** and **head tilt** as additional drowsiness signs.

---

## 🧑‍💻 Author
**Fatima Noor**  
📍 AI/ML Developer | Python Enthusiast  
🌐 [GitHub Repository](https://github.com/Fatimanoor123/Driver-Drowsiness-Detection-System-using-Mediapipe-and-OpenCV))

---

## 🏁 Conclusion
This project demonstrates how **computer vision** can be applied for **driver safety monitoring** using **AI-powered eye-tracking**.  
It’s a great base project for building an intelligent in-vehicle alert system.
