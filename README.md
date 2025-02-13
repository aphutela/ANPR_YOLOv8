
# Automatic Number Plate Recognition System

This project implements an Automatic Number Plate Recognition (ANPR) system using YOLOv8 for detection and EasyOCR for recognition. It achieves an accuracy of 88% in detecting and recognizing number plates from images and videos.

Demo Video: https://youtu.be/B7-GQrrR4vQ

## Table of Contents
1. Project Overview

2. Dataset

3. Usage

4. Features

5. Results

6. Acknowledgments

## Project Overview
This ANPR system detects and extracts the text from vehicle number plates in images and videos:

Detection: Uses the YOLOv8 model to detect number plate regions.
Recognition: Uses EasyOCR to extract text from detected number plate regions.
The system is designed for high efficiency and handles both static images and real-time video processing.
## Dataset
Annotated 600 images of vehicles manually using Label Studio for training the YOLOv8 model.

Labels include bounding boxes around the number plates.


## Usage
Training the YOLOv8 Model
To train the YOLOv8 model on the annotated dataset:

!yolo task=detect mode=train model=yolov8s.pt data=number-plate.yaml epochs=60 plots=True

Number Plate Detection and Recognition
For Images:
Place the image file in the specified directory.

Run the detection script:

file_path = "/content/drive/MyDrive/Innovation_ANPR/datasets/images/test/example_image.jpeg"
number_plate_list = detect_number_plates(image, model, display=True)

Recognize text using EasyOCR:

number_plate_list = recognize_number_plates(file_path, reader, number_plate_list, write_to_csv=True)
For Videos:
Place the video file in the specified directory.
Run the detection and recognition script:

file_path = "/path/to/video/file.mp4"
# The script processes the video frame by frame.
## Features
1. YOLOv8 for Detection:

Detects number plates with 88% accuracy.

Handles occlusion and varying lighting conditions effectively.

2. EasyOCR for Recognition:

Extracts text from number plate regions.

3. Supports Images and Videos:

Processes static images and real-time video streams.

4. CSV Logging:

Outputs detected number plates and their text into a CSV file.

5.Visualization:

Bounding boxes drawn around detected number plates.
Displays extracted text on the image/video.
## Results
Detection Accuracy: 88%

Model Performance:

True Positives (TP): 0.45

True Negatives (TN): 0.43

False Positives (FP): 0.05

False Negatives (FN): 0.07

Example outputs:

Image: Detected number plate regions with bounding boxes and extracted text.

Video: Annotated frames with detected number plates and text.

## Acknowledgements
YOLOv8 for object detection.

EasyOCR for text recognition.

Label Studio for dataset annotation.
