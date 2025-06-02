# object-detection-garbage-
Object detection for a robot controlling application

# Real-Time Object Detection with MobileNet-SSD

This project demonstrates real-time object detection using the MobileNet Single Shot Detector (SSD) model deployed via OpenCV’s `dnn` module. It includes Python scripts optimized for general desktop use and Raspberry Pi environments.

Project Structure

```
├── MobileNetSSD_deploy.caffemodel        # Pre-trained Caffe model (weights)
├── MobileNetSSD_deploy.prototxt.txt      # Model architecture definition
├── real_time_object_detection.py         # Script for real-time detection (general use)
├── pi_object_detection.py                # Optimized script for Raspberry Pi (multiprocessing)
```

---
Requirements

- Python 3.x
- OpenCV (with `dnn` module)
- `imutils` package
- `numpy`

Install dependencies with:

```bash
pip install opencv-python imutils numpy
```

---

Usage

### General Desktop (Webcam)

```bash
python real_time_object_detection.py --prototxt MobileNetSSD_deploy.prototxt.txt --model MobileNetSSD_deploy.caffemodel
```

### Raspberry Pi (with optional PiCamera support)

```bash
python pi_object_detection.py --prototxt MobileNetSSD_deploy.prototxt.txt --model MobileNetSSD_deploy.caffemodel
```

> Tip: Uncomment `usePiCamera=True` in the script if using a PiCamera.

---

Features

- Real-time object detection via webcam or PiCamera
- Uses pre-trained MobileNetSSD Caffe model
- 21 object classes supported (e.g., person, car, dog, bottle)
- Adjustable confidence threshold (`--confidence`)
- Optionally uses multiprocessing on Raspberry Pi to offload detection from the main thread

---

Model Info

- **Model**: MobileNetSSD (Single Shot MultiBox Detector)
- **Framework**: Caffe
- **Input Size**: 300x300 pixels
- **Classes**: `["background", "aeroplane", "bicycle", "bird", "boat", "bottle", "bus", "car", "cat", "chair", "cow", "diningtable", "dog", "horse", "motorbike", "person", "pottedplant", "sheep", "sofa", "train", "tvmonitor"]`

---

Exit

Press the **`q`** key in the display window to quit the application.

---
