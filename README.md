# Pixel-and-Image-Classification-on-a-Sentinel-2-Time-Series
## Overview
This project compares two land-use / land-cover classification approaches on a multi-temporal Sentinel-2 time series:
- Pixel-based classification using traditional machine learning
- Image-based classification using convolutional neural networks (CNNs)

The study uses three Sentinel-2 Level-1C scenes acquired over the same area at different dates to analyze land-cover dynamics over time.

## Objectives
The main goals of this repository are to:
- Build a complete remote sensing classification workflow
- Compare pixel-based and image-based classification methods
- Evaluate classification performance across multiple dates
- Analyze land-cover change and model uncertainty over time

## Study Workflow

### 1. Sentinel-2 Data Preparation
Sentinel-2 imagery is downloaded using Google Earth Engine in Python for the selected area of interest.

### 2. Label Creation
Land-cover labels are created in a GIS environment for each scene, using a consistent class schema across all dates.

### 3. Pixel-Based Classification
The labeled samples are used to train supervised machine learning models on spectral band values.  
The best-performing model for each scene is selected through validation and cross-validation, then used to classify the full image.

### 4. Image-Based Classification
Using the EuroSAT RGB dataset, CNN-based models are trained and compared.  
The best CNN is then applied to Sentinel-2 image patches of size 64 × 64 pixels.

### 5. Temporal Comparison
Classification outputs from different years are compared to identify land-cover changes, potential model uncertainty, and differences between the two approaches.

## Repository Structure
- `05_eurosat_rgb/` – EuroSAT RGB dataset or related image-based classification inputs
- `Labels_New_Cairo/` – label files for the study area
- `04_pixel_bands_2016.npy` – pixel-based features for 2016
- `04_pixel_bands_2018.npy` – pixel-based features for 2018
- `04_pixel_bands_2020.npy` – pixel-based features for 2020
- `04_pixel_band_classes_2016.npy` – class labels for 2016
- `04_pixel_band_classes_2018.npy` – class labels for 2018
- `04_pixel_band_classes_2020.npy` – class labels for 2020
- `DAP05_Final_Project.ipynb` – main notebook for the project

## Data
- Sentinel-2 Level-1C imagery
- EuroSAT RGB dataset
- GIS-based land-cover labels prepared for each acquisition date
- The sentinel data can be generated if you follow the notebook,a location in Egypt was selected which focuses on New, Cairo

## Methods
### Pixel-Based Methods
Traditional supervised machine learning models trained on Sentinel-2 pixel values.

### Image-Based Methods
CNN architectures trained on image patches for scene classification.

## Outputs
The repository produces:
- trained classification models
- scene-wide prediction maps
- model evaluation metrics
- visual comparisons across dates
- land-cover change analysis

## Key Questions
This project investigates:
- How well do pixel-based and image-based methods perform on the same Sentinel-2 time series?
- Which method generalizes better across dates?
- Are detected changes real land-cover changes or model-related uncertainty?
- How do cloud cover, label quality, and spatial resolution influence results?

## How to Run
1. Prepare the Sentinel-2 and label data
2. Install the required Python libraries
3. Open `DAP05_Final_Project.ipynb`
4. Run the notebook sections in order:
   - data loading
   - preprocessing
   - training
   - validation
   - prediction
   - visualization

## Future Improvements
- A requirements file will be added
- Visual examples of classification maps will be added
- soon to include Evaluation 
- Document class definitions and label schema will be included
- Will also add reproducible setup instructions
