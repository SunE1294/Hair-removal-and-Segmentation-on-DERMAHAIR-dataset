# Dermoscopic Hair Removal & Lesion Segmentation

This repository contains code and resources for **hair removal and lesion segmentation** on dermoscopic images using classical image processing techniques. The project focuses on preprocessing dermoscopic images to remove hairs and accurately segment skin lesions, which is crucial for AI-assisted skin cancer analysis.

---

## Dataset

We use the **[DERMAHAIR – Skin Cancer Hair Removal Dataset](https://www.kaggle.com/datasets/riotulab/skin-cancer-hair-removal)**:

- **Total Images:** 700 paired images (with hair / hair-free)  
- **Lesion Classes:** `mel` (Melanoma), `nv` (Nevus), `bcc` (Basal Cell Carcinoma), `akiec` (Actinic Keratoses), `bkl` (Benign Keratosis), `df` (Dermatofibroma), `vasc` (Vascular Lesion)  
- **Structure:**  
  - `Data_Skin_with_Hair` – Images with hair  
  - `Data_Skin_without_Hair` – Corresponding hair-free ground truth images  

---

## Features

### 1. Hair Removal
- **Technique:** DullRazor  
- **Process:**  
  - Convert image to grayscale  
  - Apply **Blackhat morphology** to detect hairs  
  - Remove hairs using **inpainting (Telea method)**  
- **Metrics:** Hair density, MSE, PSNR calculated for evaluation  
- **Output:** Cleaned, hair-free images saved for segmentation  

### 2. Lesion Segmentation
- **Technique:** Region-based approach  
- **Process:**  
  - Otsu Thresholding  
  - Morphological operations (open/close)  
  - Extract largest contour to isolate lesion  
- **Metrics:** Dice Score & IoU calculated to measure accuracy  
- **Result:** Average Dice Score: 82.95%  

---

## Requirements

- Python 3.x  
- OpenCV (`cv2`)  
- NumPy (`numpy`)  
- Matplotlib (`matplotlib`)  

Install dependencies via pip:

```bash
pip install opencv-python numpy matplotlib
