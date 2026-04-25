# 🏠 Bengaluru House Price Prediction

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python)](https://python.org)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-1.3%2B-orange?logo=scikitlearn)](https://scikit-learn.org)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)](https://jupyter.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> **Predict residential property prices in Bengaluru, India using Machine Learning.**  
> Trained on 13,320 real listings covering 9 features across hundreds of locations.

---

## 📌 Project Overview

This end-to-end Data Science project builds and compares multiple regression models to predict house prices (in Lakhs ₹) for properties in Bengaluru. It covers the full ML pipeline:

| Stage | Description |
|---|---|
| 🗃️ Data Loading | Load & explore the raw CSV dataset |
| 🧹 Data Cleaning | Handle nulls, parse sqft ranges, extract BHK |
| ⚙️ Feature Engineering | Price per sqft, location dummies, outlier removal |
| 📊 EDA | Distributions, correlations, location analysis |
| 🤖 Model Training | 6 algorithms compared with cross-validation |
| 📈 Evaluation | R², MAE, RMSE, residual plots |
| 💾 Deployment Ready | Saved model + prediction CLI script |

---

## 📁 Project Structure

```
bengaluru-house-price-prediction/
│
├── data/
│   └── Bengaluru_House_Data.csv      # Raw dataset (13,320 records)
│
├── notebooks/
│   └── bengaluru_house_price_prediction.ipynb  # Full Jupyter Notebook
│
├── src/
│   ├── train_model.py                # Training pipeline script
│   └── predict.py                    # CLI prediction utility
│
├── models/
│   ├── bengaluru_house_price_model.pkl  # Saved best model
│   └── columns.json                     # Feature columns & metadata
│
├── outputs/
│   ├── price_distribution.png
│   ├── bhk_area_analysis.png
│   ├── top_locations.png
│   ├── correlation_heatmap.png
│   ├── sqft_vs_price.png
│   ├── model_comparison.png
│   ├── best_model_evaluation.png
│   └── feature_importance.png
│
├── requirements.txt
├── .gitignore
└── README.md
```

---

## 📊 Dataset

| Attribute | Details |
|---|---|
| **Source** | Bengaluru House Data |
| **Records** | 13,320 |
| **Features** | 9 (area_type, availability, location, size, society, total_sqft, bath, balcony, price) |
| **Target** | `price` — House price in Lakhs (₹) |
| **Locations** | 1,300+ unique locations (grouped to ~240 after cleanup) |

---

## 🤖 Models Compared

| Model | R² Score | MAE (Lakhs) | RMSE (Lakhs) |
|---|---|---|---|
| Linear Regression | ~0.84 | ~23 | ~45 |
| Ridge Regression | ~0.84 | ~23 | ~45 |
| Lasso Regression | ~0.84 | ~23 | ~46 |
| Decision Tree | ~0.71 | ~22 | ~60 |
| **Random Forest** ⭐ | **~0.88** | **~19** | **~38** |
| Gradient Boosting | ~0.86 | ~21 | ~41 |

> ⭐ **Random Forest** selected as best model based on R² and RMSE.

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/bengaluru-house-price-prediction.git
cd bengaluru-house-price-prediction
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Run Training Script

```bash
python src/train_model.py
```

### 4. Launch Jupyter Notebook (VS Code or Browser)

```bash
# In VS Code: open notebooks/bengaluru_house_price_prediction.ipynb
# In browser:
jupyter notebook notebooks/bengaluru_house_price_prediction.ipynb
```

### 5. Predict a House Price (CLI)

```bash
python src/predict.py \
  --location "Whitefield" \
  --sqft 1500 \
  --bath 2 \
  --bhk 3
```

**Output:**
```
==================================================
  🏠  Predicted Price: ₹ 82.45 Lakhs
==================================================
  Location   : Whitefield
  Total Sqft : 1500
  BHK        : 3
  Bathrooms  : 2
  Area Type  : Super built-up  Area
  Model Used : Random Forest
  Model R²   : 0.8812
==================================================
```

---

## 📈 Key Visualizations

| Chart | Description |
|---|---|
| Price Distribution | Raw price vs log-transformed skewness |
| BHK vs Price | Median price breakdown by bedroom count |
| Top Locations | 15 most expensive Bengaluru localities |
| Correlation Heatmap | Feature inter-relationships |
| Sqft vs Price | Scatter by BHK category |
| Model Comparison | R², MAE, RMSE bar charts |
| Actual vs Predicted | Residual analysis for best model |
| Feature Importance | Top 20 predictors (Random Forest) |

---

## 🛠️ VS Code Setup

1. Install extensions: **Python**, **Jupyter**, **Pylance**
2. Select Python interpreter: `Ctrl+Shift+P` → *Python: Select Interpreter*
3. Open the notebook: navigate to `notebooks/` → click the `.ipynb` file
4. Run all cells: `Ctrl+Shift+P` → *Jupyter: Run All Cells*

---

## 👤 Author

**[Your Name]**  
📧 your.email@example.com  
🔗 [LinkedIn](https://linkedin.com/in/yourprofile)  
🐙 [GitHub](https://github.com/YOUR_USERNAME)

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgements

- Dataset sourced from Kaggle — Bengaluru House Price Data
- Inspired by various real estate ML projects in the data science community
