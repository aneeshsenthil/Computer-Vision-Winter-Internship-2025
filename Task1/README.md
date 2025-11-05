# 🚀 Task 1 — YOLOv8 Installation & Testing

### 🧩 Objective
To install and verify the working of **Ultralytics YOLOv8** by performing **object detection and segmentation** on sample images.  
This task confirms successful environment setup and model functionality.

---

### 🧠 Steps Performed
1. Created a Python virtual environment  
2. Installed the `ultralytics` package using:
   ```bash
   pip install ultralytics

3.Imported the YOLO model:
  ```bash
  from ultralytics import YOLO
  model = YOLO('yolov8n.pt');
  ```
4.Tested the model on multiple sample/test images:
  ```bash
results = model('https://ultralytics.com/images/bus.jpg')
results[0].show()
 ```
Also tested on 3–4 local images like street.jpeg, dog.jpg, and high.jpg.

5.Verified successful detections by viewing labeled bounding boxes and segmentation masks.

🖼️ Results

Objects such as cars, buses, and people were correctly detected.
The output images display clear bounding boxes and confidence scores.
All results are included in this folder as screenshots or saved images.

🧰 Tools Used
Python 3.10
Ultralytics YOLOv8
Jupyter Notebook


🧾 Sample Code
 ```bash
from ultralytics import YOLO

model = YOLO('yolov8l.pt')
path1 = r"C:\Users\anees\OneDrive\Pictures\Images\street.jpeg"

results = model(path1)
results[0].show()
 ```

✅ Conclusion

The YOLOv8 model was successfully installed and tested.
It accurately detected objects in different images, confirming that the environment and dependencies are correctly configured.



