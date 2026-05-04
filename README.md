# Industrial Surface Defect Detection 🛠️

##  Project Overview
Automated quality inspection system for industrial blade surfaces using **Computer Vision**. The goal is to detect and classify defects into three categories: **Good, Nick, and Scratch**.

##  Dataset Insights
Based on the exploratory data analysis (EDA)[cite: 1]:
*   **Total Samples:** 400 images[cite: 1].
*   **Classes:** 
    *    **Good:** 203 images[cite: 1].
    *    **Scratch:** 149 images[cite: 1].
    *    **Nick:** 48 images[cite: 1].
*   **Observation:** Significant **Class Imbalance** noted in the 'Nick' category (only ~12% of data), requiring data augmentation in future steps[cite: 1].

##  Technical Details
*   **Language:** Python[cite: 1].
*   **Core Libraries:** OpenCV, Matplotlib, and Numpy[cite: 1].
*   **Challenges:** Handling inconsistent image shapes (e.g., $1328 \times 1108$ vs $1182 \times 1339$)[cite: 1].

##  How to Run
1. Clone the repository.
2. Install dependencies:
   ```bash
   pip install opencv-python matplotlib numpy
