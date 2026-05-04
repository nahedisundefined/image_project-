# Industrial Surface Defect Detection Project

## Project Overview
This project applies Computer Vision and Deep Learning to automate quality control for industrial components (GKN blade surfaces). The system classifies surface conditions into: **Good, Nick, or Scratch**.

##  Dataset Information
The dataset consists of 400 images of metallic surfaces.
* **Good:** 203 images
* **Scratch:** 149 images
* **Nick:** 48 images

###  Dataset Access
The dataset is hosted on Kaggle. You can access it here:
* **Kaggle Link:** [GKN Blade Surface Defect Dataset](https://www.kaggle.com/datasets/warcoder/gkn-blade-surface-defect-dataset)

**Note:** If you are running this project on Kaggle, the data is located at:
`/kaggle/input/gkn-blade-surface-defect-dataset/GKN Blade Surface Defect Dataset/Data_GKN`
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
