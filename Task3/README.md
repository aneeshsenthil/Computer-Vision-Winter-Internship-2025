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
The input video was converted into individual image frames, enabling frame-by-frame processing for object detection.

### Step 2: Object Detection
Each extracted frame was passed through the YOLOv8 model.  
Bounding boxes and class labels were added to highlight detected objects, and the processed frames were saved for reconstruction.

### Step 3: Video Reconstruction
The processed frames were combined back into a video.  
This produced a final output video that shows object detection results continuously across all frames.


### Results
The final output video (output_processed.mp4) clearly displays object detection in motion, with bounding boxes and labels visible across all frames. Processed frames successfully retain all detection information while maintaining video quality.


### Tools & Technologies
- Python 3.10+
- FFmpeg - Video processing and frame extraction
- Ultralytics YOLOv8 - Object detection
- OpenCV - Computer vision operations
- NumPy - Numerical computations


This project successfully demonstrates a robust pipeline for video-based object detection by treating video as a sequence of images. The method of extracting frames, applying YOLOv8 detection, and reconstructing the video provides clear visualization of object detection in motion.
