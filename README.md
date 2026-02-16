Trader Behavior Analysis: Fear vs Greed
About This Project

In this project, I analyzed how market sentiment influences trader behavior and performance. I combined historical trading data from Hyperliquid with the Bitcoin Fear & Greed Index to study how traders perform under different emotional market conditions.

The main question I wanted to answer was:

Do traders perform better in Fear or Greed? And how does sentiment influence their trading decisions?

To explore this, I looked at profitability, trading activity, risk-taking behavior, win rates, and the relationship between profits and losses across different sentiment regimes.

Data Used
1. Historical Trading Data (Hyperliquid)

This dataset contains individual trade records, including:

Timestamp (IST)

Coin

Side (BUY/SELL)

Execution Price

Start Position (used as a proxy for risk-taking)

Closed PnL

Fees, Order ID, and other trade details

Each row represents a single executed trade.

2. Bitcoin Fear & Greed Index

This is a daily sentiment indicator that classifies overall market mood into five categories:

Extreme Fear

Fear

Neutral

Greed

Extreme Greed

I used this dataset to label each trade based on the sentiment of the corresponding trading day.

Methodology
Data Preprocessing

To prepare the data for analysis, I:

Converted timestamps into proper datetime format

Extracted a clean date column from the trading timestamps

Standardized the Fear & Greed date column so both datasets aligned

Performed a left merge on date to attach sentiment labels to each trade

Removed trades that did not have a matching sentiment value to create a clean merged dataset

Analysis Performed

After preparing the data, I analyzed:

Average profit (Closed PnL) by sentiment

Number of trades under each sentiment condition

Average position size as a measure of risk-taking

Win rate by sentiment

Average profit vs average loss in each sentiment

Key Findings
1. Profitability vs Sentiment (Average PnL)

Extreme Greed showed the highest average profit per trade.
Performance dropped significantly in Neutral and Greed conditions.
Extreme Fear days were almost unprofitable on average.

This suggests that strong bullish sentiment tends to create favorable trading conditions, while panic conditions reduce profitability.

2. Trading Activity vs Sentiment

Trading activity was highest during Fear.
It decreased during Extreme Fear.

This indicates that moderate fear may create volatility and trading opportunities, but extreme panic might cause traders to step back from the market.

3. Risk-Taking (Position Size) vs Sentiment

The largest average position sizes were taken during Neutral markets.
Position sizes dropped sharply during Fear.

This was an interesting finding. Traders appeared more comfortable taking larger positions in stable conditions, while they became more risk-averse when the market showed signs of fear.

4. Win Rate by Sentiment

Win rate was highest during Extreme Greed and lowest during Extreme Fear.

This confirms that panic-driven markets are much harder to trade successfully, while strong bullish momentum improves trade success probability.

5. Profit vs Loss Behavior

Extreme Greed showed both high average profits and large average losses, indicating aggressive risk-taking.

Fear had a more balanced profile, with relatively strong profits and controlled losses.

Greed (but not extreme) showed a weaker risk profile, where losses were often larger than profits.

Neutral markets showed small wins and small losses, reflecting lower volatility and lower risk.

Overall Conclusion

This analysis shows that market sentiment significantly influences trader behavior.

Extreme Greed was the most profitable regime and had the highest win rate.
Traders were most active during Fear but took smaller positions.
The largest positions were taken during Neutral markets, even though profitability was not the highest there.

The results suggest that neither fear nor greed alone guarantees better performance. Instead, trader behavior, risk exposure, and profitability are closely tied to the overall emotional state of the market.

Tools Used

Python

Pandas

NumPy

Matplotlib

Jupyter Notebook

How to Run the Project

Clone the repository:

git clone https://github.com/YOUR_USERNAME/trader-behavior-analysis.git


Install dependencies:

pip install -r requirements.txt


Open the notebook:

jupyter notebook analysis_clean.ipynb


Run all cells in order.