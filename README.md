# Screen Time vs Park Accessibility 📱🌳  
*Can access to parks reduce how much time people spend on their phones? We explore this question using real data and regression modeling.*

## 🧠 Project Overview  
We investigate the relationship between **smartphone screen time** and **accessibility to parks** across major U.S. cities. While people often rely on self-imposed digital limits (with questionable adherence), this project tests whether **physical spaces for activity**, like parks, offer a more effective, passive limiter.

## 🎯 Objectives  
- Determine if cities with better park access have lower screen time  
- Measure effects across total screen time and app categories (e.g., gaming, social media)  
- Build regression models to identify key predictors  
- Test real-world feasibility of reducing screen time via physical infrastructure

## 📊 Datasets Used  
- 📱 **Smartphone Usage Dataset**  
  - Screen time totals, app breakdowns (gaming, productivity, social media), and user location (U.S. cities)  
  - [Kaggle](https://www.kaggle.com/datasets/bhadramohit/smartphone-usage-and-behavioral-dataset)

- 🏞️ **2024 ParkScore Rankings**  
  - Includes categories like accessibility, median size, % of parkland in city, and amenities  
  - [Trust for Public Land](https://parkserve.tpl.org/downloads/historic/2024_ParkScoreRank.pdf)

## 🛠️ Methodology  

1. **Data Ingestion**  
   - Loaded park data into SQLite using Python  
   - Cleaned & stored fields like `avg_points`, `per cap data`, and `total data` for each city

2. **Data Join & Filtering**  
   - Merged park scores and screen time datasets using SQL JOINs on city name  
   - Filtered incomplete rows and handled outliers

3. **Exploratory Analysis**  
   - Correlation matrices  
   - Plots of park metrics vs median screen time

4. **Modeling**  
   - Trained simple linear regression models  
   - Target: screen time metrics  
   - Features: park accessibility, size, amenities, land share

## 📈 Observed Results  

- `avg_points` and park accessibility showed strong **negative correlation** with screen time  
- Regression results:
  - Models using park features as predictors explained **~55–65% of variance**
  - Cities like **Minneapolis (82.5)** and **Washington DC (84.8)** had some of the **highest park scores**
  - Cities with **lower park scores**, like **Laredo (44.7)** and **Fresno (35.4)**, generally showed **higher screen time**

- Effect was **strongest** on:
  - **Gaming** and **social media** usage  
  - **Weak or no effect** on productivity apps


## 🔍 Tools & Libraries  
- `Pandas`, `NumPy` – data cleaning and aggregation  
- `sqlite3` – storing and querying park score data  
- `Matplotlib`, `Seaborn` – visualizations  
- `scikit-learn`, `SciPy` – regression modeling and analysis

## 🧪 Future Work  
- Test more advanced models (e.g., random forest, XGBoost)  
- Incorporate more nuanced city-level data (e.g., walkability, median income)  
- Deploy a web dashboard for interactive results  
- Test causality using time-series or panel data

## ✍️ Authors  
Merna Mostafa  
Tejaswi Tripathi  
CS210 Final Project – Rutgers University
