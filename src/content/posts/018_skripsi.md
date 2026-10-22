---
title: 'Aerial UAV Pothole Object Detection with Deep CNN'
pubDate: '2020-03-23'
category: 'product'
techStack: ['Python', 'TensorFlow', 'OpenCV', 'Google Colab', 'Computer Vision']
---

- [x] Peer-Reviewed Journal Publication (JDSSE Vol. 1, No. 1)
- [x] Model Benchmark Evaluated Across Frame Rates (1 FPS to 30 FPS)
- [x] Academic Research & Undergraduate Thesis

::link{url="https://doi.org/10.20527/jdsse.v1i01.3"}

## Overview

Road surface distress and unmonitored potholes represent severe traffic hazards, contributing to vehicular damage and fatal road accidents. Conventional ground-level road inspection methods are labor-intensive, hazardous for surveying crews, and constrained by vehicular occlusion.

This research engineered an automated aerial inspection pipeline using Unmanned Aerial Vehicles (UAVs) to capture high-definition road footage, coupled with deep Convolutional Neural Networks (CNNs) to detect and localize potholes autonomously. The study evaluated optimal video sampling frame rates to maximize mean Average Precision (mAP) while preserving computational efficiency.

## Architecture and Technical Implementation

### 1. Transfer Learning with SSD ResNet-50 FPN

The computer vision pipeline was implemented using the TensorFlow Object Detection API:

- **Model Architecture**: Deployed Single Shot MultiBox Detector (SSD) architecture paired with a ResNet-50 Feature Pyramid Network (FPN) backbone pre-trained on the MS COCO dataset (`ssd_resnet_50_fpn_coco`).
- **Feature Pyramid Network (FPN)**: Extracts multi-scale feature hierarchies to detect both small asphalt cracks and large roadway depressions across varying UAV flight altitudes.
- **Hardware Acceleration**: Training and evaluation cycles were executed on GPU-accelerated environments using Python and Google Colab.

### 2. Dataset Acquisition & Video Frame Rate Optimization

- **UAV Aerial Video Dataset**: Captured real-world asphalt surface footage from low-altitude drone survey flights over urban road networks in South Kalimantan.
- **Frame Rate Benchmark**: Systematically analyzed the effect of video frame sampling rates on object detection accuracy:
  - **Peak Performance**: 30 FPS achieved the highest detection accuracy with **49.43% mAP**.
  - **Efficiency Baseline**: 1 FPS maintained robust performance at **48.36% mAP**, dramatically reducing inference latency and dataset storage footprint.
  - **Model Average**: Achieved an overall baseline performance of **48.90% mAP** across diverse road lighting conditions and shadows.

## Publication & Repository

- **Journal Article**: _Detection of Potholes using Convolutional Neural Network with Unmanned Aerial Vehicle (UAV)_, Journal of Data Science and Software Engineering (JDSSE), DOI: [10.20527/jdsse.v1i01.3](https://doi.org/10.20527/jdsse.v1i01.3).

::github{repo="miftahulmuhaemen/Pothole-Object-Detection-TF-API-"}
