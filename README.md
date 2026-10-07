# Vehicle License Plate Recognition System

## Overview
This project implements an **Automatic License Plate Recognition (ALPR)** system that detects vehicle license plates and extracts the characters from the detected plate.
The system uses a **pretrained YOLOv8 model** for license plate detection, **OpenCV** for image processing and license plate cropping, and **OCR** for extracting the characters from the detected license plate.

## Workflow
```text
Vehicle Image / Video
        ↓
      YOLOv8
        ↓
License Plate Detection
        ↓
   Bounding Box
        ↓
      OpenCV
        ↓
License Plate Cropping
        ↓
Image Preprocessing
        ↓
       OCR
        ↓
License Plate Number
```

## Features

- License plate detection using YOLOv8
- Bounding-box based license plate localization
- License plate cropping using OpenCV
- Image preprocessing for better character recognition
- OCR-based license plate text extraction

## Technologies Used
- Python
- YOLOv8
- Ultralytics
- OpenCV
- OCR
- Google Colab
- PyTorch

## Model Training

A pretrained **YOLOv8-small (`yolov8s.pt`)** model was fine-tuned on a custom license plate dataset.

### Training Configuration

- Model: YOLOv8s
- Epochs: 70
- Image Size: 640 × 640
- Batch Size: 8
- Optimizer: AdamW
- Initial Learning Rate: 0.001
- Device: GPU
- AMP: Enabled

The dataset configuration was provided through a `data.yaml` file containing the training and validation data paths and class information.

## Installation

Install the required dependencies:

```bash
pip install ultralytics opencv-python
```
Install the OCR package/dependencies used in the project according to the OCR implementation.

## Running the Project
Open the notebook or Python script and provide the required input image/video.
The system will:
1. Detect the license plate using YOLOv8.
2. Crop the detected plate using OpenCV.
3. Preprocess the cropped plate.
4. Extract the plate characters using OCR.
5. Display the detected license plate number.

## How It Works

### 1. License Plate Detection
The input vehicle image is given to the trained YOLOv8 model. YOLO detects the license plate and returns its bounding box.

### 2. License Plate Cropping
The detected bounding-box coordinates are passed to OpenCV, which extracts the license plate region from the original image.

### 3. Image Preprocessing
The cropped license plate image is processed using OpenCV to improve its quality for text recognition.

### 4. Character Recognition
The processed license plate image is passed to OCR, which extracts the alphanumeric characters from the plate.

### 5. Final Output
The extracted characters are returned as the detected license plate number.

## Future Scope
- Improve recognition for different lighting and image-quality conditions.
- Support multiple license plates in a single image.
- Improve recognition for blurred, tilted, or partially visible plates.
- Integrate the system with a vehicle monitoring application.

## License
This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for details.

## Author
**Akankshita Puri**
B.Tech Computer Science and Engineering
