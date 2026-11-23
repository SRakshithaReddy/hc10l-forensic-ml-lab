# hc10l-forensic-ml-lab

# Foundational Python Scripting for Forensic Dataset Preprocessing

Modular Python notebook and preprocessing pipeline for cleaning, auditing, and scaling raw numerical forensic and security datasets (`HC-10L: Machine Learning for Forensic and Security Lab`).

## Overview

Raw forensic telemetry, host/network metrics, and security logs frequently suffer from **missing readings**, **heavy skew**, and **anomalous spikes**. This notebook demonstrates a structured, leak-free preprocessing workflow designed to prepare numerical feature vectors for downstream machine learning models while keeping code modular and well-documented.

### What the Notebook Covers
1. **Dataset Generation & Numerical Audit:** Creates a sample numerical forensic dataset (`timing_jitter_ms`, `entropy_score`, `signal_amplitude`, `syscall_rate`, and `is_anomalous`) with injected missing values and spikes, then summarizes missingness rates, mean vs. median spread, and min/max ranges.
2. **Leak-Free Train/Test Splitting:** Splits data into training and test sets **before** fitting imputers or scalers so test distribution statistics do not leak into training.
3. **Missing Value Imputation:** Uses `SimpleImputer` (defaulting to `median` imputation to avoid distortion from skewed or spiked forensic metrics) with non-mutating DataFrame copies.
4. **Feature Scaling:** Supports configurable scaling (`RobustScaler`, `StandardScaler`, and `MinMaxScaler`), defaulting to `RobustScaler` (median and IQR) for resilience against outliers.

## Repository Structure

```text
.
├── forensic_dataset_preprocessing.ipynb   # Commented notebook with executed outputs & process summary
└── README.md                              # Project overview and usage instructions
