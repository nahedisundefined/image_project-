#  Industrial Surface Defect Detection (GKN Blade)

##  Project Overview
This project focuses on automating quality control in industrial manufacturing. Using **Computer Vision** and classical **Image Processing** techniques, the system detects and classifies defects on metallic GKN blade surfaces. This automated pipeline ensures high precision, reduces human error, and provides a low-latency alternative to deep learning models for real-time inspection.

##  Dataset Information
The dataset contains **400 high-resolution images** categorized into three types of surface conditions. 
- **Dataset Source:** [GKN Blade Surface Defect Dataset (Kaggle)](https://www.kaggle.com/datasets/warcoder/gkn-blade-surface-defect-dataset)

| Category | Count | Description |
| :--- | :--- | :--- |
| **Good** | 203 | Baseline/Reference (Pass) |
| **Scratch** | 149 | Surface abrasions (Fail) |
| **Nick** | 48 | Edge deformations/Chips (Fail) |

---

##  Engineering Challenges & Solutions

### 1. Data Integrity & Stability
**Challenge:** Real-world datasets often contain corrupted files that can crash automated code.
**Solution:** Implemented a **Validation Protocol** that verifies every image using `cv2.imread`. If a file is unreadable, the system logs a warning and skips it, ensuring 100% pipeline stability.

### 2. Metal Reflection & Low Contrast
**Challenge:** Metallic surfaces reflect light, making shallow scratches nearly invisible.
**Solution:** Applied **CLAHE** (Contrast Limited Adaptive Histogram Equalization) to amplify local contrast, followed by **Median Filtering** to remove sensor noise without blurring defect edges.

### 3. Image Standardization
**Challenge:** Inconsistent source resolutions (e.g., 1328x1108).
**Solution:** All images are normalized to **512x512 pixels** using `INTER_AREA` interpolation to maintain detail for feature extraction.

---

##  Core Implementation (The Pipeline)

Below is the optimized Python snippet representing the core logic of the inspection system:

```python
import cv2
import numpy as np

def process_blade_inspection(image_path):
    # 1. Load with Integrity Check
    img = cv2.imread(image_path)
    if img is None:
        return "Corrupted File"

    # 2. Preprocessing & Standardization
    resized = cv2.resize(img, (512, 512), interpolation=cv2.INTER_AREA)
    gray = cv2.cvtColor(resized, cv2.COLOR_BGR2GRAY)

    # 3. Advanced Enhancement (CLAHE)
    clahe = cv2.createCLAHE(clipLimit=2.0, tileGridSize=(8,8))
    enhanced = clahe.apply(gray)
    denoised = cv2.medianBlur(enhanced, 5)

    # 4. Defect Detection (Morphological & Canny)
    kernel = cv2.getStructuringElement(cv2.MORPH_RECT, (15, 15))
    tophat = cv2.morphologyEx(denoised, cv2.MORPH_TOPHAT, kernel)
    edges = cv2.Canny(tophat, 50, 150)

    return edges
