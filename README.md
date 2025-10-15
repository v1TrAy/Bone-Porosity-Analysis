# Bone Porosity Analysis Project

This repository contains the implementation of an image processing project aimed at analyzing bone porosity using OpenCV techniques such as contour detection and thresholding.

## Project Overview

The objective is to extract and quantify the porosity percentage in bone tissue images. The approach involves converting images to grayscale, applying Gaussian smoothing to reduce noise, and using various thresholding methods to segment porous areas.

## Methodology

- Image conversion to grayscale using `cv2.cvtColor()`.
- Gaussian blur (7x7 filter) for smoothing.
- Thresholding techniques applied:
  - Otsu's method (`cv2.THRESH_BINARY + cv2.THRESH_OTSU`) for adaptive binarization.
  - Triangle method (`cv2.THRESH_BINARY + cv2.THRESH_TRIANGLE`).
  - Adaptive mean thresholding (`cv2.ADAPTIVE_THRESH_MEAN_C`).
- Morphological operations such as dilation and erosion to refine contours.
- Contour detection with `cv2.findContours()` to identify porous regions.
- Calculation of porosity percentage:
  
  \[
  \text{porosity\_percentage} = \left(\frac{\text{pore\_area}}{\text{total\_area}}\right) \times 100
  \]

- Histogram equalization was tested for image quality enhancement but showed minimal effect.

## Results

- Different thresholding methods yielded varying porosity results:
  - Otsu: 77.71%
  - Mean_C: 70.91%
  - Triangle: 3.80%
  - Otsu with histogram equalization: 77.13%
- Otsu's method provided the best porosity extraction results.
- Watershed segmentation was attempted for more refined segmentation but did not give satisfactory results.

## Files in the Repository

- `Bone-Porosity-Analysis.ipynb`: Jupyter notebook with the complete code for preprocessing, thresholding, contour calculation, and porosity analysis.
- `Bone-Porosity-Analysis-Report.pdf`: Project report summarizing objectives, methodology, and results.

## Installation

1. Clone the repository:

git clone https://github.com/yourusername/bone-porosity-analysis.git
cd bone-porosity-analysis

2. Install required packages:

pip install opencv-python numpy matplotlib


## Usage

- Run the notebook to preprocess images, apply thresholding, calculate contours, and analyze porosity percentages.
- Explore different thresholding methods and observe their different effects on porosity extraction.
