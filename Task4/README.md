# 🦾 Rod Count Using Computer Vision (YOLOv8)

## 📌 Project Overview
This project focuses on automatically **detecting and counting rods in images** using **computer vision and deep learning**.  
A custom dataset was created and labeled using **Label Studio**, and a **YOLOv8 object detection model** was trained to accurately identify individual rods, even in **overlapping and dense arrangements**.

The final output displays bounding boxes around each rod and provides the **total rod count** for the input image.

---

## 🎯 Objectives
- Detect individual rods in images
- Accurately count the number of rods
- Handle overlapping rods and varying orientations
- Achieve real-time detection using YOLOv8

---

## 🧠 Technologies Used
- **Python**
- **YOLOv8 (Ultralytics)**
- **OpenCV**
- **Label Studio** (for dataset labeling)
- **NumPy**

---

## 🗂️ Dataset Preparation

### 📸 Image Collection
- 100-120 rod images collected
- Images include:
  - Top-view rod ends
  - Overlapping and stacked rods
  - Different lighting and backgrounds

### ✍️ Image Labeling
- Tool used: **Label Studio**
- Each rod was labeled **individually**
- Single class used: `rod_end`
- Labels exported in **YOLO format**

---

## 🖼️ Image Preprocessing
Since images were already colored and clear, minimal preprocessing was applied:
- **Resizing images to 640×640 pixels** (YOLO input size)
- **Image sharpening** to enhance rod edges

These steps improved detection accuracy and ensured consistent model input.

---

## 🏗️ Model Training

- Pretrained model: `yolov8n.pt`
- Framework: **Ultralytics YOLOv8**
- Training performed on the custom labeled dataset

### Training Command:
```bash
yolo detect train model=yolov8n.pt data=dataset.yaml epochs=50 imgsz=640
```
### Rod Detection & Counting
	- The trained YOLOv8 model detects rods in test images
	-	Each detected rod is marked with a bounding box
	-	Rod count = number of detected bounding boxes
### Results
	•	Successfully detects and counts rods in most test images
	•	Performs well even when rods overlap or are densely packed
	•	Suitable for real-time rod counting applications

### Limitations
	•	Accuracy may reduce in extremely dense stacks
	•	Very small or heavily occluded rods can be missed

### Future Improvements
	•	Use instance segmentation for better separation of touching rods
	•	Increase dataset size for higher accuracy
	•	Deploy model as a web or mobile application
	•	Add real-time video stream support
  
### Conclusion
This project demonstrates how deep learning and computer vision can be used to solve practical industrial problems such as rod counting.
By leveraging YOLOv8 and a custom-labeled dataset, the system achieves accurate and efficient rod detection and counting.
