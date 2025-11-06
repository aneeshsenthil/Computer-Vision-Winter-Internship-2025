# 🎥 Video Frame-Based Object Detection Using YOLOv8 & FFmpeg

## 📋 Project Overview

This project demonstrates a complete pipeline for performing object detection on videos by converting them into image frames, processing each frame with YOLOv8, and reconstructing the processed frames back into a video format.

## 🎯 Objective

Apply object detection on video content by:
- Converting video into multiple image frames using FFmpeg
- Processing each frame with YOLOv8 object detection
- Reconstructing processed frames back into a video with detection annotations

## ⚙️ Technical Implementation

### Step 1: Frame Extraction
```bash
ffmpeg -i input_video.mp4 frames/frame_%04d.jpg
```
### Step 2: Object Detection
-Applied YOLOv8 object detection on each extracted frame
-Generated bounding boxes and class labels for detected objects
-Processed frames stored with detection annotations

### Step 3: Video Reconstruction
```bash
ffmpeg -r 24 -i processed/frame_%04d.jpg -vcodec libx264 output_processed.mp4
```

### Results
The final output video (output_processed.mp4) clearly displays object detection in motion, with bounding boxes and labels visible across all frames. Processed frames successfully retain all detection information while maintaining video quality.

### Analysis & Insights
 YOLOv8 Performs Well When:
-Objects are clearly visible and well-lit
-Lighting conditions are sufficient
-Object size is reasonable for detection
-Minimal motion blur present



### Tools & Technologies
-Python 3.10+
-FFmpeg - Video processing and frame extraction
-Ultralytics YOLOv8 - Object detection
-OpenCV - Computer vision operations
-NumPy - Numerical computations


This project successfully demonstrates a robust pipeline for video-based object detection by treating video as a sequence of images. The method of extracting frames, applying YOLOv8 detection, and reconstructing the video provides clear visualization of object detection in motion.
