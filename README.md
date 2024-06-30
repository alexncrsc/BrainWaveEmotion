# BrainWaveEmotion

**BrainWaveEmotion** is a comprehensive machine learning project designed to classify emotional states using EEG (electroencephalogram) data collected with a Cyton device from OpenBCI. This setup includes 8 electrodes for capturing brainwave signals.

## Project Overview

The project involves the following steps:

1. **Data Acquisition**: 
   - EEG data is recorded from an 8-electrode Cyton device while the subject (myself) listens to stimulus music to induce happy and sad emotional states.

2. **Data Preprocessing**: 
   - Raw EEG data is loaded and processed using MNE to remove accelerometer channels (Accel X, Y, Z) and annotate emotional states.

3. **Annotation Handling**: 
   - Annotations are loaded from a CSV file, converted to appropriate units, and filtered to exclude 'ignore' states but also to include it.

4. **Event Generation**: 
   - Events are generated based on the annotated emotional states ('happy', 'sad', 'ignore') with corresponding onset times.

5. **Epoch Creation**: 
   - Epochs of 2, 5, and 10 seconds are created from the raw data to capture temporal patterns in the EEG signals.

6. **Feature Extraction**: 
   - Power spectral densities (PSDs) are computed for different frequency bands (delta, theta, alpha, sigma, beta) to use as features.

7. **Model Training and Evaluation**: 
   - Various machine learning models, including K-Nearest Neighbors (KNN), Support Vector Machine (SVM), Random Forest, and Gradient Boosting, are trained and evaluated. 
   - The code uses StandardScaler for feature normalization and performs model training with different epoch lengths.

8. **Handling Pauses**: 
   - Pauses between stimuli are considered to ensure accurate emotion labeling.

## Key Libraries and Tools

The project leverages the following Python libraries: 
- MNE
- NumPy
- pandas
- scikit-learn
- Matplotlib

## Key Scripts and Functions

- Loading and preprocessing EEG data
- Handling and filtering annotations
- Generating and plotting events
- Creating epochs for different durations
- Extracting power spectral density features
- Training and evaluating various machine learning models
- Plotting confusion matrices to visualize model performance

## Extra info
**Files**: 
   -  annotations.csv, data labeled with full data periods.
   -  annotations2.csv, 5 seconds long events.
   -  annotations3.csv, 2 seconds long events.
   -  annotations4.csv, 10 seconds long events.
   -  data.bdf, recorded data with the Cyton EEG.
   -  EEG_final_version.ipynb, the jupyter notebook that contains all the code.

## Repository Content

This repository serves as a valuable resource for researchers and developers interested in neuroinformatics, affective computing, and EEG-based emotion classification.

