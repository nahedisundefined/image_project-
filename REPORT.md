# Surface Defect Detection Project Report
**Course:** Digital Image Processing (CS.383)

## 1. Project Overview
This project implements an automated inspection pipeline for turbine blades. It focuses on identifying surface defects using classical computer vision.

## 2. Methodology
- **Enhancement:** Applied CLAHE for metallic surfaces.
- **Filtering:** Used Median blur to reduce noise.
- **Segmentation:** Employed Top-Hat transforms and Canny edge detection.

## 3. Performance
- **Speed:** 0.44s per image.
- **Efficiency:** 100% stability on the GKN dataset.
