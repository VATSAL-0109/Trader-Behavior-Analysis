# Trader Behavior Analysis: Fear vs Greed

## 📌 About This Project

In this project, I wanted to understand how market sentiment (Fear vs Greed) affects trader behavior and performance. I used historical Hyperliquid trading data and merged it with the Bitcoin Fear & Greed Index to analyze patterns in:

- Profitability under different sentiment conditions  
- How actively traders trade in Fear vs Greed  
- How much risk they take (using position size as a proxy)  
- Win rate across different sentiment regimes  
- How profits compare to losses in each sentiment  

The main question guiding this project was:  
👉 *Do traders actually perform better in Fear or Greed? And how does sentiment influence their decisions?*

---

## 📊 Data Used

### 1. Historical Trading Data (Hyperliquid)
This dataset contains individual trade records, including:
- `Timestamp IST`
- `Coin`
- `Side` (BUY/SELL)
- `Execution Price`
- `Start Position` (used as a proxy for risk-taking)
- `Closed PnL`
- Fees, Order ID, and other trade details  

Each row represents one trade.

### 2. Bitcoin Fear & Greed Index
This is a daily sentiment indicator that classifies market mood into:
- Extreme Fear  
- Fear  
- Neutral  
- Greed  
- Extreme Greed  

I used this to label each trade based on the market sentiment of that day.

---

## 🔧 What I Did (Methodology)

### Data Preprocessing
To make the data usable, I:
- Converted timestamps into proper datetime format.  
- Extracted a clean `date` column from the trading timestamps.  
- Standardized the Fear & Greed `date` column so both datasets matched.  
- Performed a **left merge** on `date` to attach sentiment to each trade.  
- Created a cleaned dataset (`merged_clean`) by removing trades that didn’t have a matching sentiment label.

### Analysis Performed
Once the data was prepared, I analyzed:
- Average profit (Closed PnL) by sentiment  
- Number of trades under each sentiment  
- Average position size (as a measure of risk-taking)  
- Win rate by sentiment  
- Average profit vs average loss in each sentiment  

---

## 📈 Key Findings

### ✅ 1. Profitability vs Sentiment (Average PnL)

| Sentiment | Avg Closed PnL |
|-----------|----------------|
| Extreme Greed | **205.82** |
| Fear | **128.29** |
| Greed | 53.99 |
| Neutral | 27.09 |
| Extreme Fear | 1.89 |

**What I observed:**  
Traders were most profitable on average during **Extreme Greed**. Performance dropped significantly in Neutral and Greed conditions, and **Extreme Fear** days were almost unprofitable.

---

### ✅ 2. Trading Activity vs Sentiment

| Sentiment | Number of Trades |
|-----------|-----------------|
| Fear | **13,869** |
| Greed | 11,292 |
| Extreme Greed | 5,621 |
| Neutral | 2,756 |
| Extreme Fear | 2,326 |

**What this suggests:**  
Traders were most active during **Fear**, likely because fear creates volatility and more trading opportunities. In **Extreme Fear**, many traders seemed to step back instead of trading.

---

### ✅ 3. Risk-Taking (Position Size) vs Sentiment

| Sentiment | Avg Start Position |
|-----------|-------------------|
| Neutral | **89,199.59** |
| Greed | 37,276.79 |
| Extreme Greed | 24,593.24 |
| Extreme Fear | 21,902.80 |
| Fear | 8,146.36 |

**My interpretation:**  
Surprisingly, traders took the **largest positions in Neutral markets**, possibly because they felt more comfortable and perceived lower risk. During **Fear**, position sizes dropped sharply, showing clear risk aversion.

---

### ✅ 4. Win Rate by Sentiment

| Sentiment | Win Rate |
|-----------|---------|
| Extreme Greed | **55.3%** |
| Neutral | 49.5% |
| Greed | 43.6% |
| Fear | 38.2% |
| Extreme Fear | 29.3% |

**Key takeaway:**  
The best win rate was in **Extreme Greed**, while traders performed worst in **Extreme Fear**, confirming that panic conditions are very difficult to trade profitably.

---

### ✅ 5. Profit vs Loss Behavior

| Sentiment | Avg Profit | Avg Loss |
|-----------|------------|----------|
| Extreme Greed | 417.56 | -463.18 |
| Fear | 373.54 | -215.94 |
| Greed | 198.20 | -413.50 |
| Neutral | 61.76 | -31.24 |
| Extreme Fear | 20.29 | -66.31 |

**What this shows:**
- **Extreme Greed**: High profits, but also very large losses → aggressive risk-taking.  
- **Fear**: Better risk-adjusted profile (big wins, relatively smaller losses).  
- **Greed**: Poor risk profile — losses were much larger than profits.  
- **Neutral**: Small wins and small losses — low risk, low reward.

---

## 🧠 Overall Conclusion

From this analysis, it’s clear that **market sentiment strongly influences trader behavior**.

- **Extreme Greed** was the most profitable and had the highest win rate.  
- Traders were **most active in Fear**, but took the **smallest positions**.  
- Traders took their **largest positions in Neutral markets**, even though profits were relatively low.

This shows that neither pure Fear nor pure Greed guarantees better trading — behavior, risk-taking, and performance are all deeply linked to sentiment.

---

## 🛠️ Tools Used

- Python  
- Pandas  
- NumPy  
- Matplotlib  
- Jupyter Notebook  

---

## ▶️ How to Run the Project

1. Clone this repository:
   ```bash
   git clone https://github.com/YOUR_USERNAME/trader-behavior-analysis.git
2. Install dependencies:
   pip install -r requirements.txt
3. Open the notebook:
   jupyter notebook analysis_clean.ipynb
4. Run all cells in order.
