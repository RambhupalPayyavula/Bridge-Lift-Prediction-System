# 🌉 Chelsea Street Bridge Lift Prediction (ML for Traffic Optimization)

This project develops a machine learning system to **predict bridge lift timings** for the Chelsea Street Bridge in Boston, enabling proactive traffic management and reducing congestion for commuters.

Developed in collaboration with **AECOM** and **MassDOT**, this project applies **data engineering, feature engineering, and machine learning** to solve a real-world infrastructure problem.

# Bridge-Lift-Prediction-System
Predicts bridge lift timings using ML on bridge logs, weather, and tidal data to enable proactive traffic management and reduce congestion. Built with Random Forest (R²=0.90) and XGBoost (F1=0.96) in a real-world AECOM × MassDOT use case.

---

## 📊 Problem Statement

The Chelsea Street Bridge is a bascule bridge that lifts frequently to allow vessel passage.

This causes:
- Traffic congestion  
- Delays during peak commute hours  
- Disruptions near Seaport District & Logan Airport  

👉 Goal: Predict bridge lift timings to enable **advance traffic alerts and congestion mitigation**

---

## 🗂️ Datasets

### 🔹 Bridge Logs (AECOM)
- ~5,857 records, 15 variables  
- Includes lift start/end times and durations  

### 🔹 Weather Data (NOAA)
- ~4,063 records  
- Captures environmental conditions  

### 🔹 Tidal Data (NOAA)
- ~36,867 records  
- Represents tidal levels influencing vessel movement  

---

## ⚙️ Tech Stack

**Language:** Python  
**Data Processing:** pandas, numpy  
**Visualization:** matplotlib, seaborn  
**Machine Learning:** scikit-learn, XGBoost  

---

## 🧼 Data Engineering & Feature Engineering

- Extracted target variable: `Start_hour`  
- Created derived features:
  - Notice Time Difference  
  - Lift Duration  
- Integrated multi-source datasets (bridge + weather + tidal)  
- Handled missing values and encoded categorical variables  
- Filtered data for analysis period (2019–2022)  

---

## 📈 Exploratory Insights

- **Peak Vessel Traffic:** 7 AM – 1 PM (highest at 8 AM)  
- **High Traffic Days:** Thursday and Friday (>830 passages)  
- **Dominant Vessel Type:** Tug/Barge (>1400 occurrences)  
- **Operational Efficiency:**  
  - 96.3% of vessels pass within 1-hour notice window  

---

## 🧠 Machine Learning Models

### 🔹 Regression (Predicting Lift Timing)

| Model | Performance |
|------|-----------|
| Random Forest (Best) | R² = 0.90, RMSE = 1.79 |
| Linear Regression | Baseline |
| Decision Tree | Moderate |

👉 **Top Features:**
- ETA_Hour  
- Notice Time Difference  
- Vessel Count  

---

### 🔹 Classification (Time-of-Day Prediction)

Target Classes:
- Morning (5 AM – 12 PM)  
- Afternoon (12 PM – 5 PM)  
- Evening (5 PM – 8 PM)  
- Night (8 PM – 5 AM)  

| Model | Performance |
|------|-----------|
| XGBoost (Best) | F1 Score = 0.96 |
| Random Forest | Strong |
| KNN | Moderate |
| Naive Bayes | Baseline |

👉 **Top Features:**
- ETA_Hour  
- Email_Ltime_Diff  
- Email_ETA_Diff  
- Act_Time_Diff  
- Vessel(s)  

---

## 🏆 Key Impact

- Enabled predictive insights for **traffic congestion management**  
- Improved decision-making for **transportation planning systems**  
- Demonstrated real-world application of ML in **infrastructure optimization**  

---

## 📂 Repository Structure

```bash
Bridge-Lift-Prediction/
├── data/                         # Raw and processed datasets
├── notebooks/                   # EDA and modeling
├── src/                         # Feature engineering and model scripts
├── models/                      # Saved models (optional)
├── README.md
