
# 🗽 New York Taxi Spending Analysis

## 🔍 Project Overview
This is a **supervised regression** project focused on analyzing and predicting **taxi fare spending across New York City**, based on historical ride data.

### 📌 Problem Statement  
Predict the **average money spent on taxi rides per region**, for each **day and hour** in New York City.

### 🎯 Objectives
- Build and evaluate machine learning models to predict spending.
- Explore how time, location, and weather impact taxi fare amounts.
- Enhance model performance using engineered features.

---

## 📊 Dataset Information

### 📁 Data Source
- **TLC Trip Record Data (Yellow Cabs)**  
  [Download Dataset (Parquet)](https://d37ci6vzurychx.cloudfront.net/trip-data/yellow_tripdata_2019-01.parquet)

### 📄 Sample Columns
| VendorID | Pickup Time | Dropoff Time | Passenger Count | Trip Distance | Pickup ID | Dropoff ID | Fare Amount | Tip Amount | Total Amount |
|----------|-------------|---------------|------------------|----------------|------------|-------------|---------------|--------------|----------------|
| 1        | 2019-01-01 00:46:40 | 2019-01-01 00:53:20 | 1 | 1.5 | 151 | 239 | 7.00 | 1.65 | 9.95 |

### 🧹 Data Cleaning & Preparation
- Removed rows with **zero or negative `total_amount`**.
- Removed **outliers** based on statistical thresholds.

### 🔧 Feature Engineering
1. **Time-based features**: day of week, hour, weekend/holiday indicator.  
2. **Location-based features**: merged `LocationID` with NYC **borough data**.  
3. **Weather features**: merged with historical weather data (via public API).

### ⚠️ Data Limitations
- Missing values in `congestion_surcharge`.
- Assumes accurate mapping from `LocationID` to boroughs.

---

## 🛠️ Technical Stack

| Tool | Description |
|------|-------------|
| Python | Primary language |
| Jupyter Notebook | Development environment |
| pandas, numpy | Data manipulation |
| scikit-learn | Machine learning models |
| matplotlib, seaborn | Data visualization |

---

## 🧪 Methodology

### 🔍 Exploratory Data Analysis (EDA)
- Distribution of fares and trip distances.
- Correlation of weather and congestion with spending.
- Patterns by borough, hour, and day of week.

### 🧠 Models Used
- **Benchmark**: Decision Tree (original features only)
- **Trained models**:  
  - Decision Tree  
  - Random Forest  
  - Gradient Boosting  
  - Tuned Random Forest (via GridSearchCV)

### 📈 Evaluation Metrics

| Model | MAE | RMSE | R² Score |
|-------|-----|------|----------|
| Benchmark (Decision Tree) | 9.778 | 14.739 | 0.225 |
| Decision Tree (All Features) | 9.876 | 14.963 | 0.211 |
| Random Forest | 7.663 | 13.600 | 0.348 |
| Gradient Boosting | 9.525 | 14.184 | 0.291 |
| Tuned Random Forest | **7.446** | **12.792** | **0.423** |

---

## 📊 Results & Insights

### ✅ Key Findings
- **Weather** and **borough location** significantly affect average fare amount.
- **Tuned Random Forest** achieved the best performance (MAE: 7.34, R²: 0.435).
- Feature engineering improved model accuracy substantially.

### 📈 Visualizations
- Trip volume heatmaps by hour and region.
- Bar charts for average fare per borough and weekday.
- Scatter plots comparing predicted vs. actual fares.

### 💼 Business Implications
- Helps taxi operators optimize pricing and fleet management.
- Supports city planners in understanding demand patterns.

---

## 🔮 Future Improvements
- Integrate real-time traffic/congestion data.
- Extend analysis to include multiple months or years.
- Deploy model as an API for real-time fare predictions.

---

## 📂 Project Structure (Suggested)
