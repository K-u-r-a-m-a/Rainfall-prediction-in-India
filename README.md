# 🌧️ Hybrid Machine Learning for Rainfall Forecasting in India

### Integrating LightGBM and Bidirectional LSTM for Spatial–Temporal Rainfall Prediction
The present study has developed a successful hybrid model for rainfall prediction, incorporating LightGBM and LSTM in such a way that their complementary strengths can be employed to capture the spatial and temporal complexities in rainfall data.

<p align="center">

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![LightGBM](https://img.shields.io/badge/LightGBM-239120?style=for-the-badge)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
![Keras](https://img.shields.io/badge/Keras-D00000?style=for-the-badge&logo=keras)
![Scikit Learn](https://img.shields.io/badge/ScikitLearn-F7931E?style=for-the-badge&logo=scikitlearn)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy)

</p>

---

## 📌 Project Overview

Rainfall forecasting is crucial for agriculture, water resource management, flood prevention, and climate resilience in India.

Traditional machine learning models often struggle to simultaneously capture:

- Spatial rainfall variations across geographical regions
- Temporal rainfall patterns and seasonality

This project proposes a **Hybrid Machine Learning framework** that combines:

### LightGBM
Captures:

- Spatial relationships
- Feature interactions
- Structured rainfall patterns

### Bidirectional LSTM

Captures:

- Sequential dependencies
- Seasonal variations
- Long-term temporal trends

A dynamic weighted ensemble combines both models to leverage their strengths and improve predictive performance.

---

## 🎯 Objectives

- Forecast annual rainfall across India
- Capture both spatial and temporal patterns
- Improve predictive accuracy compared to standalone models
- Reduce prediction error
- Support agricultural and disaster management planning

---

## 📂 Dataset Information

Dataset characteristics:

| Feature | Value |
|-----------|----------|
| Coverage | India |
| Regions | 36 States/UTs |
| Years | 1901–2024 |
| Records | 4,439 |
| Data Type | Monthly + Annual Rainfall |
| Source | IMD-based rainfall dataset |

Historical statistics:

| Period | Mean Rainfall |
|----------|-------------|
| 1901–2017 | 1415.8 mm |
| 2018–2024 | 1336.3 mm |

---

## ⚙️ Data Preprocessing Pipeline

The preprocessing workflow includes:

### Data Cleaning

- Missing value handling
- Mean imputation
- Label encoding of States/UTs

### Feature Engineering

Generated lag variables:

- Lag_1
- Lag_2
- Lag_3

### Feature Scaling

- RobustScaler
- MinMaxScaler

### Feature Selection

Top 20 features selected using:

```python
SelectKBest(f_regression)
```

### Outlier Handling

```python
Z-score threshold = 3
```

---

## 🧠 Hybrid Model Architecture

```text
Input Rainfall Dataset
        ↓
Data Preprocessing
        ↓
Feature Engineering
        ↓
Feature Selection
        ↓
Train/Test Split
        ↓
5 Fold Cross Validation
        ↓
 ┌─────────────┐    ┌─────────────┐
 │ LightGBM    │    │ BiLSTM      │
 │ Model       │    │ Model       │
 └─────────────┘    └─────────────┘
        ↓                ↓
     Predictions    Predictions
            ↓
Dynamic Weighted Ensemble
            ↓
     Final Prediction
```

---

## 🔍 Model Configuration

### LightGBM

```python
learning_rate=0.03
n_estimators=1000
max_depth=3
num_leaves=31
subsample=0.8
colsample_bytree=0.8
reg_alpha=0.1
reg_lambda=0.1
```

Features:

- Early stopping
- L1/L2 regularization
- Histogram optimization

---

### Bidirectional LSTM

Architecture:

- Two stacked LSTM layers
- 128 units
- 64 units
- Dropout: 0.5
- Dense output layer
- Adam optimizer
- Learning rate scheduling
- Early stopping

---

## 📊 Results

Average metrics across 5-fold cross-validation:

| Model | RMSE | MAE | R² |
|---------|---------|---------|------|
| LightGBM | 57.18 | 40.04 | 0.9889 |
| LSTM | 37.10 | 22.5 | 0.9950 |
| Hybrid | 36.2 | 23.0 | 0.995 |

---

## 🏆 Key Achievements

✅ Hybrid model outperformed standalone approaches

✅ Captured both spatial and temporal rainfall patterns

✅ Reduced prediction error significantly

✅ Achieved:

- MAE → 23 mm
- RMSE → 36 mm
- R² → 0.995

---

## 📈 Feature Importance

Top influential features:

| Feature | Importance |
|-----------|-------------|
| JUL | 799 |
| AUG | 638 |
| JUN | 591 |
| Lag_2 | 575 |
| Lag_3 | 573 |
| SEP | 527 |
| Lag_1 | 507 |

---

## 🌍 Real World Applications

### Agriculture

- Crop planning
- Irrigation scheduling
- Yield optimization

### Disaster Management

- Flood forecasting
- Drought prediction
- Risk mitigation

### Urban Planning

- Waterlogging prevention
- Infrastructure planning

### Water Resource Management

- Reservoir management
- Water allocation strategies

---

## 🚀 Installation

Clone repository:

```bash
git clone https://github.com/K-u-r-a-m-a/Rainfall-prediction-in-India.git
```

Move into project directory:

```bash
cd Rainfall-prediction-in-India
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run notebook:

```bash
jupyter notebook
```

---

## 📦 Required Libraries

```txt
numpy
pandas
matplotlib
seaborn
scikit-learn
tensorflow
keras
lightgbm
scipy
```

---

## 🔮 Future Scope

- Real-time rainfall forecasting
- Daily rainfall prediction
- Transfer learning for low-data regions
- Integration of climate indices (ENSO, IOD)
- Explainable AI approaches
- Deployment using cloud services

---

## 📖 Citation

If you use this work in research:

```bibtex
@article{RainfallHybrid2025,
title={Hybrid Machine Learning for Rainfall Forecasting in India: Integrating LightGBM and LSTM Models},
author={Kushal Rao M and Ranveer Verma},
year={2025}
}
```

---

## ⭐ If you found this useful, consider giving the repository a star.
