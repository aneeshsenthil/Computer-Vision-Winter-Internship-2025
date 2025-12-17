Here is a comprehensive and professional README.md file structure. It includes detailed sections for environment setup, the specific Label Studio export workflow, and a robust Python script for counting.

🏗️ Rod Detection & Automated Counting System
A complete end-to-end computer vision pipeline using YOLOv8 for real-time detection and counting of metal/industrial rods. This project covers everything from raw image annotation in Label Studio to deploying an automated counter.

📋 Table of Contents
Features

Installation

Data Preparation (Label Studio)

Model Training

Inference & Counting

Results & Evaluation

✨ Features
High Precision: Uses YOLOv8 (You Only Look Once) for fast and accurate detection.

Custom Labeling: Integrated workflow for custom datasets using Label Studio.

Automated Counting: Logic to count instances and display the total on the output image/video.

Batch Processing: Ability to process entire folders of images and export results to CSV.

⚙️ Installation
1. Clone the Repository
Bash

git clone https://github.com/yourusername/rod-detection-yolov8.git
cd rod-detection-yolov8
2. Setup Environment
It is recommended to use a virtual environment:

Bash

python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install ultralytics label-studio opencv-python pandas
🏷️ Data Preparation (Label Studio)
1. Launch Labeling Tool
Bash

label-studio start
Open http://localhost:8080.

Create a new project named "Rod Detection".

In Labeling Setup, choose Object Detection -> Bounding Boxes.

Add your label: rod.

2. Exporting for YOLOv8
Once labeling is complete:

Click the Export button.

Select the YOLO format.

Download the .zip and extract it into a folder named dataset.

3. Directory Structure
Organize your files as follows:

Plaintext

/dataset
  ├── /images
  │    ├── train/
  │    └── val/
  ├── /labels
  │    ├── train/
  │    └── val/
  └── data.yaml
🏋️ Model Training
Create a data.yaml file to point to your dataset:

YAML

path: ./dataset
train: images/train
val: images/val

names:
  0: rod
Run the training script:

Python

from ultralytics import YOLO

# Load a pretrained model (YOLOv8 Small is recommended for speed/accuracy balance)
model = YOLO('yolov8s.pt')

# Train
model.train(
    data='data.yaml',
    epochs=100,
    imgsz=640,
    batch=16,
    device=0 # Set to 'cpu' if no GPU available
)
🔍 Inference & Counting
Use the following script to detect rods and overlay the total count on the image:

Python

import cv2
from ultralytics import YOLO

# Load your custom model
model = YOLO('runs/detect/train/weights/best.pt')

# Run inference
img_path = 'test_image.jpg'
results = model(img_path)

# Process results
for r in results:
    count = len(r.boxes)
    print(f"Detected {count} rods.")
    
    # Plot results on image
    res_plotted = r.plot()
    
    # Add text overlay for count
    cv2.putText(res_plotted, f"Total Rods: {count}", (50, 50), 
                cv2.FONT_HERSHEY_SIMPLEX, 1, (0, 255, 0), 2)
    
    cv2.imshow("Rod Count", res_plotted)
    cv2.waitKey(0)
📊 Results & Evaluation
After training, check the runs/detect/train/ folder for:

results.png: Loss curves and mAP metrics.

confusion_matrix.png: To see if the model is confusing rods with background elements.

val_batch0_labels.jpg: To verify the ground truth vs. predictions.

📜 License
Distributed under the MIT License. See LICENSE for more information.
