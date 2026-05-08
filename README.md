## 💻 Core Implementation (Pipeline Snippet)

Below is the optimized Python script used to process the GKN images. This snippet demonstrates the **Data Integrity Check**, **CLAHE Enhancement**, and **Defect Detection**:

```python
import cv2
import numpy as np
import os

def process_gkn_blade(image_path):
    # 1. Data Integrity: Load and verify image
    img = cv2.imread(image_path)
    if img is None:
        return None  # Skip corrupted files
    
    # 2. Preprocessing: Resize for consistency
    resized = cv2.resize(img, (512, 512), interpolation=cv2.INTER_AREA)
    gray = cv2.cvtColor(resized, cv2.COLOR_BGR2GRAY)
    
    # 3. Restoration & Enhancement: CLAHE & Median Blur
    # This step amplifies local contrast on metallic surfaces
    clahe = cv2.createCLAHE(clipLimit=2.0, tileGridSize=(8,8))
    enhanced = clahe.apply(gray)
    denoised = cv2.medianBlur(enhanced, 5)
    
    # 4. Feature Detection: Morphological Top-Hat & Canny
    # Highlights intensity peaks (defects) relative to surface
    kernel = cv2.getStructuringElement(cv2.MORPH_RECT, (15, 15))
    tophat = cv2.morphologyEx(denoised, cv2.MORPH_TOPHAT, kernel)
    edges = cv2.Canny(tophat, 50, 150)
    
    return edges

# Example Usage:
# result = process_gkn_blade('path/to/blade_image.png')
