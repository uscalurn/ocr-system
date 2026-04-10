# ocr-system
This project implements an end-to-end Optical Character Recognition (OCR) system.

The pipeline consists of:
- Text detection using a segmentation-based approach to localize text regions
- Bounding box extraction from predicted masks
- Text recognition using a CNN + Transformer architecture

The system processes input images and outputs extracted text through a full pipeline:
Image → Detection → Cropping → Recognition → Text

This project focuses on building core deep learning components, including model design, preprocessing, training, and inference.
