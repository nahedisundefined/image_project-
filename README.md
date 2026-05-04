# Industrial Surface Defect Detection (GKN Blade)

##  Project Overview
This project focuses on automating quality control in industrial manufacturing. Using **Computer Vision**, the system detects and classifies defects on metallic GKN blade surfaces. This automation reduces human error and speeds up the inspection process.

##  Dataset Information
The dataset contains 400 high-resolution images categorized into three types of surface conditions:
*   **Good:** 203 images (Reference/Pass)
*   **Scratch:** 149 images (Defect/Fail)
*   **Nick:** 48 images (Defect/Fail)

###  Dataset Access
The dataset is hosted on Kaggle. You can find it here:
*   **Kaggle Link:** [GKN Blade Surface Defect Dataset](https://www.kaggle.com/datasets/warcoder/gkn-blade-surface-defect-dataset)
*   **Internal Path (Kaggle):** `/kaggle/input/gkn-blade-surface-defect-dataset/GKN Blade Surface Defect Dataset/Data_GKN`

##  Engineering Challenges & Solutions

### 1. Image Standardization
The source images have inconsistent resolutions (e.g., 1328x1108 and 1182x1339). 
*   **Solution:** All images are pre-processed and resized to **224x224 pixels** using OpenCV to ensure compatibility with deep learning architectures.

### 2. Class Imbalance
The 'Nick' defect represents only **12%** of the dataset, which can lead to model bias.
*   **Solution:** Future iterations will implement **Data Augmentation** (Rotation, Flipping, and Zooming) to synthesize more samples for the underrepresented classes.

##  Technical Stack
*   **Python 3.x**
*   **OpenCV**: For image processing and normalization.
*   **NumPy**: For high-performance array operations.
*   **Matplotlib**: For data visualization and defect analysis.

##  How to Run
1.  **Clone the repository.**
2.  **Install dependencies:**
    ```bash
    pip install opencv-python numpy matplotlib
    ```
3.  **Run the Notebook:**
    Open `Surface_Defect_Detection.ipynb` and ensure the dataset path is correctly set to the directory containing the 'Good', 'Nick', and 'Scratch' folders.

## ⚠️ Note on Imports
Make sure your working directory does **not** contain files named `numpy.py` or `cv2.py`, as this will cause import conflicts with the official libraries.
