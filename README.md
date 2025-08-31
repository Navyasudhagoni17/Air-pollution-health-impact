# 🌍 Air Pollution Health Impact Analysis  

This project analyzes the relationship between **air pollution (PM2.5 exposure)** and **health outcomes (mortality due to air pollution)** using real-world datasets. The goal is to explore correlations, run regression models, and build a simple **risk assessment model** that predicts the likelihood of high mortality based on air quality.  

---

## 📊 Dataset  
The dataset is sourced directly from the **World Bank Open Data API**:  
- **PM2.5 Exposure (µg/m³)** → `EN.ATM.PM25.MC.M3`  
- **Mortality Rate due to Air Pollution (per 100,000 people)** → `SH.STA.AIRP.P5`  

The two datasets are merged on `country` and `year` to create a structured dataset like:  

| country       | iso3c | year | pm25 | mort_rate |
|---------------|-------|------|------|-----------|
| India         | IND   | 2010 | 58.2 | 87.4      |
| China         | CHN   | 2015 | 47.8 | 64.5      |
| United States | USA   | 2015 | 8.4  | 12.3      |

The merged dataset is saved as:  
merged_wdi_pm25_mortality.csv

markdown
Copy code

---

## ⚙️ Process  
1. **Data Collection** → Fetch air pollution & mortality data via World Bank API.  
2. **Preprocessing** → Clean, merge, and filter missing values.  
3. **Exploratory Analysis** → Correlation analysis between PM2.5 and mortality.  
4. **Regression Model** → Ordinary Least Squares (OLS) regression with `statsmodels`.  
5. **Risk Assessment Model** → Logistic Regression with `scikit-learn` to classify "high-risk" countries/years.  
6. **Visualization** → Scatter plots to show trends and predicted risk levels.  

---

## 🛠️ Technologies Used  
- **Python**  
- **Pandas** for data handling  
- **Matplotlib** for visualization  
- **Statsmodels** for regression analysis  
- **Scikit-learn** for machine learning (logistic regression)  

---

## 📈 Outputs  
- **Correlation coefficient** between PM2.5 exposure and mortality.  
- **Regression summary** (coefficients, R², p-values).  
- **Risk Model**: Accuracy and ROC-AUC score.  
- **Visualizations**:  
  - Scatter plot: PM2.5 vs Mortality  
  - Predicted risk probability vs PM2.5  

*(Example visualization placeholder — replace with your own)*  
![Scatter Plot Example](images/scatter_example.png)  

---

## 🚀 How to Run  
### Option 1: Google Colab  
- Open [Google Colab](https://colab.research.google.com/)  
- Copy the notebook code into a new notebook  
- Run all cells (dataset downloads automatically via API)  

### Option 2: Local (VS Code / Jupyter)  
```bash
git clone https://github.com/your-username/air-pollution-health-analysis.git
cd air-pollution-health-analysis
pip install -r requirements.txt
python air_pollution_analysis.py
