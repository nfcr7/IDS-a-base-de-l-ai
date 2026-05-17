# Network Intrusion Detection using ML, Deep Learning, and Hybrid Models

This project builds and evaluates multiple machine learning and deep learning models for network intrusion detection. The goal is to classify network traffic into benign activity and different cyberattack categories using supervised learning.

The notebook includes data preprocessing, class filtering, model training, evaluation, feature engineering, and model comparison. Several rare classes with very low sample counts were removed to reduce noise and improve training stability.

## Project Overview

The project compares different model families:

- Random Forest
- XGBoost
- LightGBM
- 1D CNN
- MLP
- LSTM
- Hybrid XGBoost + CNN
- Hybrid XGBoost + Random Forest + MLP
- Feature-engineered hybrid model with an Infilteration guard

## Dataset Processing

The dataset was subsampled to 1 million rows for faster experimentation. Classes with fewer than 100 samples after preprocessing were dropped because they caused unstable training and unreliable evaluation.

Final classification was performed on 10 classes:

- Benign
- Bot
- DDOS attack-HOIC
- DDOS attack-LOIC-UDP
- DDoS attacks-LOIC-HTTP
- DoS attacks-GoldenEye
- DoS attacks-Hulk
- DoS attacks-Slowloris
- Infilteration
- SSH-Bruteforce

## Main Results

The best-performing models from the notebook were:

| Model | Accuracy |
|---|---:|
| MLP | 98.03% |
| CNN | 97.88% |
| XGB + CNN Hybrid | 97.63% |
| XGB + RF + MLP Hybrid | 96.43% |
| Tuned Random Forest | 94.80% |
| Tuned XGBoost | 91.63% |
| Tuned LightGBM | 84.86% |
| LSTM | 63.55% |

A final feature-engineered XGB + CNN hybrid model was also tested with an Infilteration guard. It achieved around 97% overall accuracy and improved focus on the difficult Infilteration class.

## Techniques Used

- Data cleaning and preprocessing
- Label encoding
- Standard scaling
- Class filtering
- Class weighting
- Random Forest tuning
- XGBoost tuning
- LightGBM tuning
- 1D CNN architecture
- MLP neural network
- LSTM neural network
- Hybrid model stacking/combination
- Feature engineering
- Confusion matrix visualization
- Classification reports
- Model comparison plots

## Libraries Used

- Python
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- TensorFlow / Keras
- XGBoost
- LightGBM

## Notes

This notebook was created as an experimental prototype for comparing classical machine learning, deep learning, and hybrid approaches for intrusion detection. Some results may vary depending on the random seed, GPU availability, dataset version, and preprocessing choices.
