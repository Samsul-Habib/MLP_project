# 🎬 Cinema Audience Forecasting  
Forecasting daily theatre audience counts using machine learning.

This repository contains a complete workflow for predicting cinema audience volume using historical booking logs, POS transactions, theatre metadata, and calendar features. It is built around a single, fully documented **Jupyter notebook** for end-to-end reproducibility.

---

---

## 🎯 Objective
Predict the **daily audience count** for each theatre in the test period based on:

- Online booking data (BookNow)  
- In-theatre POS data (CinePOS)  
- Metadata describing each theatre  
- Calendar and temporal patterns  

The notebook generates predictions formatted according to the `sample_submission.csv` specification.

---

## 📦 Dataset Overview
The original dataset (download from Kaggle) typically includes:

- `booknow_visits.csv` — target variable (audience counts)  
- `booknow_booking_daily.csv` / `booknow_booking.csv` — online booking logs  
- `cinePOS_booking.csv` — point-of-sale bookings  
- `booknow_theaters.csv`, `cinePOS_theaters.csv` — theatre metadata  
- `movie_theater_id_relation.csv` — mapping between online and offline ID  
- `date_info.csv` — calendar metadata
- `sample_submission.csv` — required output format  

Place all dataset files inside a local folder named `data/` before running the notebook.

---

## 🧠 Notebook Workflow

### 1. Setup & Reproducibility
- Importing dependencies  
- Setting global random seeds  
- Defining data paths and utility functions  

### 2. Data Loading & Cleaning
- Parsing dates, IDs, and column types  
- Merging BookNow and CinePOS datasets  
- Validating completeness and detecting missing data  
- Aligning theatre identifiers across data sources  

### 3. Exploratory Data Analysis (EDA)
- Daily audience trends  
- Seasonality and weekly patterns  
- Booking → visits relationships  
- Theatre-level behaviour and distribution analysis  

### 4. Feature Engineering
- **Temporal features:**  
  - day-of-week, month, year, is_weekend  
  - rolling averages (7/14/28 days), lag features  
- **Theatre metadata:**  
  - theater area code, theater type  

### 5. Modeling
- Gradient boosting models (LightGBM / XGBoost)  
- Train–validation time-based splits  
- Hyperparameter tuning using optuna 
- Global model across all theatres or theatre-aware variants  

### 6. Validation
- Time-series cross-validation  
- Feature importance and model diagnostics  

### 7. Submission Generation
- Final prediction pipeline  
- Producing `submission.csv` in the required format  

---

## ▶️ How to Run Locally

### 1. Create a Python virtual environment
```bash
python -m venv my_env
my_env\Scripts\activate
```
### 2. Install dependencies
```bash
pip install -r requirements.txt
```
### 3.Or install common dependencies directly
```bash
pip install numpy pandas matplotlib scikit-learn lightgbm xgboost seaborn plotly
```
### 4. Run the notebook
  * open VS code and start the kernel
  * now run the notebook.
---
### Visit the URL for complete project description
[Link text] (https://www.kaggle.com/competitions/Cinema_Audience_Forecasting_challenge)

