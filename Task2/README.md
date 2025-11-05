# 🚀 Task 2 — Multi-Image Object Detection & Metric Evaluation

### 🧩 Objective
To perform **object detection** on multiple images using **YOLOv8** and evaluate the performance of the trained model using standard metrics like Precision and mAP.

---

### ⚙️ Steps Performed
1. Loaded multiple input images and ran object detection using YOLOv8.  
2. Trained and evaluated the model; YOLO automatically stored the results in:
   ```
   runs/detect/train7/
   ```
3. Retrieved performance metrics and plots for evaluation.

---

### 📊 Model Evaluation Results

| Metric | Value | Interpretation |
|--------|--------|----------------|
| **Precision** | 0.5036 | Model correctly predicts about 50% of detected objects — moderate accuracy. |
| **mAP@0.5** | 0.5036 | Model detects roughly half of the ground-truth objects with acceptable IoU (50%). |
| **mAP@0.5:0.95** | 0.3362 | Detection accuracy drops at stricter IoU thresholds — bounding boxes need improvement. |

---

### 🧠 Analysis & Insights
- The model shows **moderate detection ability** but lacks precision and localization accuracy.  
- **Bounding boxes** are not tightly aligned with actual objects (seen in lower mAP@0.5:0.95).  
- Possible reasons:
  - Class imbalance in dataset  
  - Limited training data  
  - Underfitting due to short training duration  

---

### 💡 Suggestions for Improvement
- Provide **more diverse training images** for each class.  
- Use **data augmentation** (rotation, brightness, scaling).  
- Fine-tune model using `yolov8m.pt` or `yolov8l.pt` for better accuracy.  
- Adjust **confidence thresholds** to improve recall.  

---

### 🧰 Tools Used
- Python 3.10+  
- Ultralytics YOLOv8  
- Jupyter Notebook  

---

### ✅ Conclusion
The YOLOv8 model was successfully executed on **multiple images**.  
The obtained metrics — **Precision (0.50)**, **mAP@0.5 (0.50)**, and **mAP@0.5:0.95 (0.33)** — indicate **moderate detection accuracy**.  
Further tuning and better dataset balancing can significantly improve the results.

---
