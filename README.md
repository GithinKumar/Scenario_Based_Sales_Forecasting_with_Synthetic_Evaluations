# ML-EGA-model
ML models for synthetic data generation and EGA scenario-based analysis
# ML Models: Data Synthesizer & EGA

## 🔍 Overview
This repository contains two machine learning models:
1. **Data Synthesizer**: Generates synthetic data for 2 future years using 4 years of historical data.
2. **EGA Model**: (Left side) Trained on the 4-year dataset and user-defined market scenarios. The model is evaluated on the synthetic 2-year dataset (right side), and then retrained using prediction errors and scenario-based simulations to improve robustness and adaptability. 

## 📁 Structure
- `/notebooks`: Colab notebooks for both models
- `/data`: Datasets used and generated
- `README.md`: This file
