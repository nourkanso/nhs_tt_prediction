# Psychological Treatment Outcome Prediction Models

This repository contains a prediction model for predicting outcomes of psychological therapy in NHS Talking Therapies (formerly IAPT) services. The models predict seven binary outcomes related to depression, anxiety, and functional impairment following high-intensity psychological treatment.

## Key features

- **Elastic net regression**: Primary modelling approach. 
- **Bootstrap internal validation**: 200 iterations with optimism-correction. 
  
## Evaluation metrics
The models are comprehensively evaluated using the following metrics:

### 1. Discrimination performance
- **Area Under the Curve (AUC)**:
  - Optimism-corrected using Harrell's bootstrap method
  - Reported with 95% confidence intervals (2.5th-97.5th percentiles)
  
- **Sensitivity and specificity**:
  - Median values across 200 bootstrap iterations
  - Reported with 95% confidence intervals (2.5th-97.5th percentiles)

### 2. Calibration performance
- **Brier Score**:
  - Median value across bootstrap iterations
  - 95% confidence intervals (2.5th-97.5th percentiles)

- **Calibration metrics**:
  - Calibration slope 
  - Calibration intercept 
  - Calibration curves (using Locally Weighted Scatterplot Smoothing (LOWESS))

### 3. Stability analyses
- **Visuals**:
  - Prediction instability plots
  - Calibration instability plots
  - Mean absolute percentage error (MAPE) instability plots (per patient)

## Model outcomes

The models predict seven key outcomes:

1. **Depression outcomes** (PHQ-9):
   - **Reliable improvement**: a clinically significant reduction (≥6) in PHQ-9 score, beyond measurement error.
   - **Recovery** (cases only): a final PHQ-9 score below the clinical threshold for depression (≤10).
   - **Reliable recovery** (cases only): combination of reliable improvement and recovery.

2. **Anxiety outcomes** (GAD-7):
   - **Reliable improvement**: a clinically significant reduction (≥4) in GAD-7 score, beyond measurement error.
   - **Recovery** (cases only): a final GAD-7 score below the clinical threshold for anxiety (≤8).
   - **Reliable recovery** (cases only): combination of reliable improvement and recovery.

3. **Functional impairment** (WSAS):
   - **WSAS ≥10 at endpoint**: indicates significant functional impairment at the end of treatment, regardless of baseline score.

