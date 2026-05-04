# Industrial Surface Defect Detection Project

## Project Overview
This project applies Computer Vision and Deep Learning to automate quality control for industrial components, specifically GKN blade surfaces. The system is designed to analyze images and classify the surface condition into one of three categories: Good, Nick, or Scratch. This helps in identifying structural flaws without the need for manual human inspection.

## Dataset Information
The dataset consists of 400 images of metallic surfaces categorized into three classes:
* Good: 203 images (Clean surfaces).
* Scratch: 149 images (Linear surface marks).
* Nick: 48 images (Small chips or gouges).

Note: The images are stored in the `/data` folder, organized by category. You can also access the dataset through the project documentation links.

Important Observation:
A significant Class Imbalance was identified, as the 'Nick' category represents only about 12% of the total data. Future work will require Data Augmentation techniques to balance the classes and improve model accuracy for this specific defect.

## Technical Stack
The project is built using Python and the following core libraries:
* OpenCV: Used for image loading and processing tasks.
* Matplotlib: Used for visualizing data distributions and displaying image samples.
* Numpy: Used for handling image arrays and mathematical operations.

## Engineering Challenges
* Image Consistency: The source images have varying resolutions (e.g., 1328x1108 and 1182x1339). All images must be resized to a uniform shape before being fed into a neural network.
* Data Distribution: Managing the low sample count for specific defects to prevent the model from becoming biased toward the 'Good' class.

## How to Run
1. Clone this repository to your local machine.
2. Ensure the dataset is placed in the `/data` directory.
3. Install the necessary dependencies:
   pip install opencv-python matplotlib numpy
4. Open and run the Jupyter Notebook `Surface_Defect_Detection.ipynb` to view the analysis and visualization steps.
