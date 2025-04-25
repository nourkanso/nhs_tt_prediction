# Psychological Therapy Outcome Prediction Models

This repository contains a prediction model for predicting outcomes of psychological therapy in NHS Talking Therapies (formerly IAPT) services. The models predict seven binary outcomes related to depression, anxiety, and functional impairment following high-intensity psychological treatment.

## Key Features

- **Elastic Net Regression**: Primary modelling approach balancing interpretability and performance
- **Bootstrap Validation**: 200 iterations with optimism correction for reliable performance estimates
  
## Evaluation Metrics
The models are comprehensively evaluated using the following metrics:

### 1. Discrimination Performance
- **Area Under the Curve (AUC)**:
  - Optimism-corrected using Harrell's bootstrap method
  - Reported with 95% confidence intervals (2.5th-97.5th percentiles)
  
- **Sensitivity and specificity**:
  - Median values across 200 bootstrap iterations
  - Reported with 95% confidence intervals (2.5th-97.5th percentiles)

### 2. Calibration Performance
- **Brier Score**:
  - Median value across bootstrap iterations
  - 95% confidence intervals (2.5th-97.5th percentiles)

- **Calibration Metrics**:
  - Calibration slope 
  - Calibration intercept 
  - Flexible calibration curves (LOWESS)

### 3. Stability Analyses
- **Prediction Instability**:
  - Mean Absolute Percentage Error (MAPE) per patient
  - Overall average MAPE across all predictions

- **Visuals**:
  - Prediction instability plots
  - Calibration instability plots
  - MAPE instability plots


## Model Outcomes

The models predict seven key therapy outcomes:

1. **Depression Outcomes** (PHQ-9):
   - Reliable improvement
   - Recovery
   - Reliable recovery

2. **Anxiety Outcomes** (GAD-7):
   - Reliable improvement
   - Recovery
   - Reliable recovery

3. **Functional Impairment** (WSAS ≥10 at endpoint)

## Repository Structure

├── model/
│ ├── preprocessing.py # Data cleaning and preparation
│ ├── pipeline.py # Model pipeline construction
│ └── evaluation.py # Bootstrap validation and performance metrics
