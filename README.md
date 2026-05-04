# Industrial Surface Defect Detection Project

## Project Overview
This project applies Computer Vision and Deep Learning to automate quality control for industrial components (GKN blade surfaces). The system classifies surface conditions into: **Good, Nick, or Scratch**.

##  Dataset Information
The dataset consists of 400 images of metallic surfaces.
* **Good:** 203 images
* **Scratch:** 149 images
* **Nick:** 48 images

###  Dataset Access
You can download the dataset from the following link:
* **Download Link:** [Click Here to Access Dataset](https://www.kaggle.com/datasets/vipin20/industrial-surface-defect-detection)
* **Folder Structure:** Place the downloaded images in a folder named `/data` in the root directory.

> **Note:** A significant **Class Imbalance** was identified ('Nick' is only 12%). Data Augmentation is recommended for future improvements.

##  Technical Stack
* **OpenCV**: Image processing and resizing.
* **Matplotlib**: Data visualization.
* **Numpy**: Array manipulations.

##  Troubleshooting 
If you get a `SyntaxError` when importing `cv2` or `numpy`:
1. Ensure you do **not** have a file named `numpy.py` or `cv2.py` in your project folder or Downloads folder.
2. If such a file exists, rename it (e.g., `my_notes.py`) and delete any `__pycache__` folders.

##  How to Run
1. Clone this repository.
2. Install dependencies:
   ```bash
   pip install opencv-python matplotlib numpy
