# Crop and Weed Detection using Faster R-CNN (ResNet50-FPN)

A deep learning-based object detection project for identifying and classifying cultivated crops and weeds in agricultural images using Faster R-CNN.

## Overview

This project focuses on developing an automated system for detecting and classifying crops and weeds in agricultural environments using computer vision techniques.

By leveraging a Faster R-CNN model with a ResNet50-FPN backbone, the system aims to support precision agriculture by improving weed management efficiency and reducing reliance on manual labor and excessive herbicide use.

## Problem Background

In precision agriculture, weed control is a critical challenge:

* Weeds compete with crops for nutrients, water, and sunlight
* Can reduce crop yield by up to **30%**
* Traditional methods (manual or herbicide spraying) are inefficient and environmentally harmful

This project proposes a **selective and intelligent detection approach** using deep learning.

## Methodology

### Dataset

* Source: Kaggle - *Crop and Weed Detection with Bounding Boxes*
* Total data: **1300 images (512x512)**
* Classes:

  * Crop (tanaman budidaya)
  * Weed (gulma)
* Annotation format: YOLO (converted for training)

### Data Preprocessing

* Image resizing
* Normalization (ImageNet mean & std)
* Conversion to tensor
* Bounding box adjustment

### Data Augmentation

* Horizontal flip
* Random rotation
* Resize
* Random brightness & contrast

## Model Architecture

* **Model:** Faster R-CNN
* **Backbone:** ResNet50-FPN (pretrained on COCO)
* **Components:**

  * Region Proposal Network (RPN)
  * Object classification & bounding box regression

The model is customized for **2 classes: crop and weed**.

## Training Setup

* Optimizer: SGD (Stochastic Gradient Descent)
* Learning rate scheduler applied
* Training epochs: **15**
* Loss components:

  * Classification loss
  * Bounding box regression loss
  * Objectness loss

## Evaluation Metrics

* **mAP (mean Average Precision):** 0.8779
* **F1-Score:** 0.6929
* **IoU Threshold:** 0.5

These results indicate strong performance in both detection and classification tasks.

## Results

* Model successfully detects and localizes crops and weeds
* Consistent loss reduction during training
* Good generalization on test data

However:

* Some challenges remain with overlapping objects
* Performance affected by lighting conditions and object size

## Objectives

* Automate crop and weed detection
* Improve efficiency in agricultural management
* Reduce environmental impact of herbicide overuse

## Reference

* Dataset: [Crop and Weed Detection Dataset](https://www.kaggle.com/datasets/ravirajsinh45/crop-and-weed-detection-data-with-bounding-boxes)
