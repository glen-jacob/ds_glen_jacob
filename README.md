# Market Sentiment vs Trader Behavior — Analysis 

## 📌 Overview
This project analyzes how trader behavior (PnL, volume, win-rate, trade size, and relative leverage-like metrics) changes across different market sentiment conditions using the Fear & Greed Index.

The notebook includes:
- Data cleaning  
- Feature engineering  
- Daily aggregation  
- Sentiment merging  
- Statistical testing  
- Visualization and insights  

---

## 📁 Project Structure
ds_glen_jacaob/
│
├── notebook_1.ipynb # Main analysis notebook
├── historical_data.csv # Trading dataset
├── fear_greed_index.csv # Market sentiment dataset
├── outputs
└── README.md


---

## 📊 Datasets Used

### 1. Trading Data (`historical_data.csv`)
Includes:
- Timestamp IST
- Start Position
- Execution Price
- Size USD
- Closed PnL
- Coin / Symbol

### 2. Sentiment Data (`fear_greed_index.csv`)
Includes:
- Date  
- Sentiment score (0–100)  
- Sentiment classification (Fear, Neutral, Greed, etc.)

---

## 🔧 Key Steps in the Notebook

### ✅ Data Cleaning
- Safe datetime parsing  
- Handling missing and invalid records  
- Standardizing numeric types  

### ✅ Feature Engineering
- Position value in USD  
- Relative trade size (proxy for leverage)  
- Daily aggregated metrics:
  - Total daily PnL  
  - Win rate  
  - Daily volume  
  - Relative size  

### ✅ Merging With Sentiment
- Merged on the `date` column  
- Ensures consistent format on both datasets  

### ✅ Statistical Testing
Used **Mann–Whitney U test**, because PnL distributions are non-normal.

### ✅ Visualizations
- Daily PnL distributions  
- Volume heatmap (Sentiment × Date)  
- Win-rate comparison  
- Relative trade size (before and after outlier removal)  
- Cumulative PnL over time  
- Histogram of relative trade size  

---

## ✅ Results Summary (Insights)

### ✔️ PnL Trends
- PnL distributions vary but not significantly across sentiments  
- Fear/Greed groups show no strong statistical difference  

### ✔️ Trade Sizing Behavior
- Most trades cluster near relative size = 0  
- A few extreme outliers caused by very small position values  
- After filtering outliers, sentiment differences become clearer  

### ✔️ Win Rate
- Win rate stays mostly stable  
- Slight variation in Fear and Greed conditions  

### ✔️ Activity Levels
- Fear and Greed days show more trading volume  
- Indicates emotional or high-volatility periods attract more activity  

---

## How to Run the Project

### Google Colab
1. Upload the notebook:  
   `ds_assignment.ipynb`
2. Upload both datasets:
   - `historical_data.csv`
   - `fear_greed_index.csv`
3. Run all cells:  
   **Runtime → Run all**

### Local Jupyter Notebook
Install dependencies:

```bash
pip install pandas numpy matplotlib seaborn scipy

