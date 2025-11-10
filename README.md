# ds_glen_jacob

Market Sentiment vs Trader Behavior — Analysis 
📌 Overview

This project analyzes how trader behavior (PnL, volume, win-rate, trade size, leverage-like metrics) changes across different market sentiment conditions.
The analysis uses a combination of trade-level data and daily Fear & Greed Index sentiment values to understand patterns, risk behavior, and performance.

The notebook performs:

Data cleaning

Feature engineering

Daily aggregation

Sentiment merging

Statistical testing

Visualization

📊 Datasets Used
1. Trading Data (historical_data.csv)

Contains:

Timestamp IST

Start Position

Execution Price

Size USD

Closed PnL

Coin

Trade direction (optional)

2. Sentiment Data (fear_greed_index.csv)

Contains:

Date

Value (0–100 score)

Sentiment classification (Fear, Greed, Extreme Fear, etc.)

🔧 Key Steps in the Notebook
✅ 1. Data Cleaning

Safe datetime parsing

Handling missing/invalid values

Converting numerical columns

Aligning daily formats

✅ 2. Feature Engineering

Position value

Relative trade size (proxy for leverage)

Win/loss flag

Daily aggregates such as:

total daily PnL

win rate

daily volume

average relative size

✅ 3. Merging With Sentiment

Based on daily date

Ensures both datasets have consistent date format

✅ 4. Statistical Testing

Used Mann–Whitney U test (non-parametric and more robust than t-test):

Comparison between Fear vs Greed groups

Checks whether PnL distributions differ significantly

✅ 5. Visualization

Includes:

PnL distribution by sentiment

Volume heatmap (sentiment × date)

Win rate comparison

Relative trade size distribution

Cumulative PnL trend

Histogram of relative trade sizes

(Optional) log-scale variations

Outlier-trimmed plots

✅ Results Summary (High-Level Insights)
✔️ 1. PnL vs Sentiment

PnL distributions vary across sentiment categories

Not statistically significant difference between Fear and Greed in many cases

Market sentiment may not strongly impact trader performance

✔️ 2. Trade Size Behavior

Most trades are sized consistently

Extreme values exist due to small position sizes (ratio explodes)

After removing outliers, sentiment differences are minimal

✔️ 3. Win Rate Patterns

Win rate slightly varies by sentiment

Greed and Neutral often show small improvements

Fear-related categories show wider variance

✔️ 4. Volume and Activity

More trading activity happens during Fear and Greed days

Suggests emotional market days trigger more participation

✔️ 5. Overall Trend

The trader is reasonably consistent

Sentiment affects volume more than profitability

Risk-taking increases only slightly in Fear or Greed
