# Deep Learning Based Mobile App for Automated Plant Disease Detection

A mobile-based intelligent plant disease detection system that uses deep learning and image processing techniques to identify diseases from leaf images. The application allows users to upload or capture plant leaf images and automatically predicts the disease type, confidence score, severity level, and recommended treatments. The system supports multiple crops, including cabbage, tomato, tea, rice, and onion, using trained MobileNetV2 models integrated with a Flask backend and a mobile application interface. This project aims to provide an accessible and efficient tool for early disease diagnosis and improved crop management.

# Plant Disease Detection Mobile Application

A deep learning-based mobile application that detects plant diseases from leaf 
images using **MobileNetV2**, a lightweight convolutional neural network 
architecture optimized for on-device/mobile inference. The system covers 
**5 selected plant species**, with an individually trained classification 
model for each plant.

## Overview
Early detection of plant diseases is critical for reducing crop loss and 
improving agricultural yield. This project uses transfer learning on 
MobileNetV2 to classify leaf images into healthy/diseased categories (and 
disease sub-types) for each of the 5 selected plants, then deploys the 
trained models into a mobile application for real-time, in-field diagnosis.

## Selected Plants
| # | Plant | Model |
|---|-------|-------|
| 1 | *( Tomato)* | MobileNetV2 (transfer learning) |
| 2 | *( Potato)* | MobileNetV2 (transfer learning) |
| 3 | *( tea)* | MobileNetV2 (transfer learning) |
| 4 | *( Cabbage)* | MobileNetV2 (transfer learning) |
| 5 | *( rice)* | MobileNetV2 (transfer learning) |


## Model Architecture
- **Base model:** MobileNetV2 (pretrained on ImageNet, used as a feature extractor via transfer learning)
- **Approach:** One dedicated fine-tuned model per plant species (5 separate models total)
- **Input:** RGB leaf images, resized to MobileNetV2's expected input shape (typically 224×224)
- **Output:** Multi-class softmax layer per plant, predicting healthy vs. specific disease classes

## Dataset Split
Each plant's dataset was split as follows:
| Split | Percentage |
|-------|-----------|
| Training | 70% |
| Testing | 15% |
| Validation | 15% |

## Training Environment
- **Platform:** Google Colab (GPU runtime)
- **Framework:** TensorFlow / Keras
- Each of the 5 models was trained independently in a separate Colab notebook/session

## Features
- 📷 Real-time leaf image capture and disease prediction via mobile camera
- 🌿 Support for 5 plant species with dedicated trained models
- ⚡ Lightweight MobileNetV2 backbone — optimized for mobile/edge inference
- 📊 Per-plant accuracy and confusion matrix reporting
- 📱 On-device inference (TensorFlow Lite conversion recommended for deployment)

## Tech Stack
- **Model Training:** Python, TensorFlow/Keras, Google Colab
- **Model Architecture:** MobileNetV2 (Transfer Learning)
- **Mobile App:** *(e.g. Flutter / Android Studio )
- **Model Deployment:** TensorFlow Lite (.tflite)
