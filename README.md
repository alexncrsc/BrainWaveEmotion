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
  
## Accuracy Results

### Gradient Boost model, 5 seconds long events + ignored labeled data
- Accuracy: 44%

### SVM model, 5 seconds long events + ignored labeled data
- Accuracy: 44%

### Random Forest model, 5 seconds long events + ignored labeled data
- Accuracy: 28%

### SVM, KNN, Gradient Boost models, 2 seconds long events
- SVM: 30%
- KNN: 36%
- Gradient Boost: 56%

### SVM, KNN, Gradient Boost models, 5 seconds long events
- SVM: 84%
- KNN: 60%
- Gradient Boost: 76%

### Random Forest model, 5 seconds long events
- Accuracy: 68%

### SVM, KNN, Gradient models, 10 seconds long events
- SVM: 41%
- KNN: 33%
- Gradient Boost: 75%


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


# Limitations

The **BrainWaveEmotion** project encounters several limitations:
- **Data Variability:** Emotional responses vary widely among individuals, impacting model generalization.
- **Hardware Constraints:** The use of a single 8-electrode device may limit spatial resolution and signal quality.
- **Subjectivity:** Emotion annotation based on stimulus music is subjective and may not fully capture nuanced emotional states.
- **Model Complexity:** Complex machine learning models may require substantial computational resources and expertise for optimization.

# Sources

The **BrainWaveEmotion** project draws upon the following primary sources:
- **MNE-Python:** Used for EEG data preprocessing and analysis.
- **OpenBCI Cyton Board:** Hardware employed for EEG data acquisition.
- **scikit-learn:** Library utilized for machine learning model implementation and evaluation.
- **Pandoc:** Tool utilized for converting Markdown to PDF format for project documentation.

## Extra info
**Files**: 
   -  annotations.csv, data labeled with full data periods.
   -  annotations2.csv, 5 seconds long events.
   -  annotations3.csv, 2 seconds long events.
   -  annotations4.csv, 10 seconds long events.
   -  data.bdf, recorded data with the Cyton EEG.
   -  Gradient_boost_5sec_ignore -  Gradient Boost model, 5 seconds long events + ignored labeled data 
   -  SVM_5sec_ignore -  SVM model,  5 seconds long events + ignored labeled data 
   -  Random_forest_5sec_ignore -   Random forest model, 5 seconds long events + ignored labeled data 
   -  SVM_KNN_Gradient_2sec -  SVM KNN Gradient boost models, 2 seconds long events 
   -  SVM_KNN_Gradient_5sec -  SVM KNN Gradient boost models, 5 seconds long events 
   -  Random_forest_5sec -  Random forest model, 5 seconds long events 
   -  SVM_KNN_Gradient -  SVM KNN Gradient models, 10 seconds long events 

## Repository Content

This repository serves as a valuable resource for researchers and developers interested in neuroinformatics, affective computing, and EEG-based emotion classification.

