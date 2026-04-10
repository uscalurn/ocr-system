# ocr-system
This project implements an end-to-end Optical Character Recognition (OCR) system.

The pipeline consists of:
- Text detection using a segmentation-based approach to localize text regions
- Bounding box extraction from predicted masks
- Text recognition using a CNN + Transformer architecture

The system processes input images and outputs extracted text through a full pipeline:
Image → Detection → Cropping → Recognition → Text

This project focuses on building core deep learning components, including model design, preprocessing, training, and inference.
# End-to-End OCR System (Detection + Transformer Recognition)

## Overview

This project implements a complete Optical Character Recognition (OCR) pipeline using deep learning.

The system consists of two main stages:

* **Text Detection**: locate text regions in images using segmentation
* **Text Recognition**: convert cropped text regions into character sequences

Pipeline:
**Image → Detection → Cropping → Recognition → Text**

---

## Method

### 1. Text Detection

* Model: ResNet18-based segmentation
* Output: pixel-wise text mask
* Post-processing:

  * Thresholding
  * Morphological operations
  * Connected components → bounding boxes

### 2. Text Recognition

* CNN encoder for feature extraction
* Transformer decoder for sequence prediction
* Token-based character generation

---

## Dataset

The model is trained on the **TextOCR dataset** from Kaggle.

* Task: scene text extraction from images
* Contains annotated text regions and corresponding labels
* Suitable for both detection and recognition tasks

---

## Results

Evaluation on validation set:

* **CER (Character Error Rate):** 33.68%
* **WER (Word Error Rate):** 45.31%
* **Character-level accuracy:** ~66.32%

The model demonstrates **moderate performance**, with reasonable character recognition but accumulated errors at the word level.

---

## Models

Pretrained models are available in the **Releases** section:

* `best.pth` → Text Detection model
* `best_recognition.pth` → Text Recognition model

Download and place them in the project directory before running inference.

---

## How to Run

1. Install dependencies:

```
pip install -r requirements.txt
```

2. Open the notebook:

```
ocr_pipeline.ipynb
```

3. Run all cells to:

* Load models
* Perform detection
* Run OCR inference

---

## Demo
* input images:
![input_1](https://github.com/user-attachments/assets/d1d3998a-4604-4d9d-9aac-5ceacadc2112)

* output images:
<img width="268" height="387" alt="output_1" src="https://github.com/user-attachments/assets/e60eb67e-46db-400e-9f2e-c372236a931f" />


---

## Limitations

* Errors increase at word level due to character mistakes
* Performance depends on image quality and text layout
* Limited by training data size and model capacity

---

## Author

Nguyen Minh Nhan
