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
<img width="207" height="302" alt="input_01" src="https://github.com/user-attachments/assets/db1adc64-b095-4114-a37f-3913806c4557" />


* output images:
<img width="268" height="387" alt="output_1" src="https://github.com/user-attachments/assets/e60eb67e-46db-400e-9f2e-c372236a931f" />

* output text:

<img width="439" height="395" alt="output_text_1" src="https://github.com/user-attachments/assets/c35f84cd-58a1-4ae9-b5c8-9922d2be15f7" />


---

## Limitations

* Errors increase at word level due to character mistakes
* Performance depends on image quality and text layout
* Limited by training data size and model capacity

---

## Author

Nguyen Minh Nhan
