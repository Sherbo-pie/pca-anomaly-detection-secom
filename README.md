# PCA-Based Anomaly Detection on the SECOM Dataset

## Overview

This project explores anomaly detection in semiconductor manufacturing data using **Principal Component Analysis (PCA)**. Instead of using PCA solely for dimensionality reduction, it is trained on normal operating data and used to identify anomalies through **reconstruction error**, measured using **Squared Prediction Error (SPE)**.

## Dataset

- **Dataset:** SECOM Semiconductor Manufacturing Dataset
- **Samples:** 1,567
- **Features:** 591 sensor measurements
- High-dimensional and highly imbalanced industrial dataset

## Methodology

- Removed features with excessive missing values
- Applied mean imputation to remaining missing values
- Trained PCA exclusively on normal samples
- Reduced dimensionality from **591 features to 156 principal components**
- Retained **95% of the dataset variance**
- Used **Squared Prediction Error (SPE)** as the anomaly score
- Set anomaly threshold using the training distribution of reconstruction errors

## Models Compared

The PCA-SPE framework was benchmarked against:

- Isolation Forest
- One-Class SVM

## Results

| Method | Key Observation |
|----------|----------|
| PCA-SPE | Highest anomaly recall (0.423) |
| Isolation Forest | Lower recall |
| One-Class SVM | Lower recall |

PCA-SPE provided the best anomaly detection recall while also offering interpretable insights into the sensors contributing to anomalous behaviour.

## Key Takeaways

- Demonstrates PCA as an anomaly detection technique rather than only a dimensionality reduction method.
- Highlights the precision–recall trade-off in anomaly detection systems.
- Provides sensor-level interpretability through feature contribution analysis.
- Shows the effectiveness of reconstruction-error-based anomaly detection on industrial sensor data.

## Tools & Libraries

- Python
- NumPy
- Pandas
- scikit-learn
- Matplotlib

## Report

A detailed report containing preprocessing steps, mathematical background, experiments, and analysis is included in this repository.
