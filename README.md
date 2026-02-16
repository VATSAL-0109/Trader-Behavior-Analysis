Trader Behavior Analysis
Impact of Market Sentiment on Trading Performance
1. Introduction

This project analyzes how market sentiment influences trader behavior and trading performance.

I combined historical trading data from Hyperliquid with the Bitcoin Fear & Greed Index to examine how traders behave under different emotional market conditions.

The central question behind this project was:

Do traders perform better in Fear or in Greed?
And more importantly, how does sentiment influence their risk-taking and outcomes?

2. Data Sources
2.1 Historical Trading Data (Hyperliquid)

The trading dataset contains individual trade-level records, including:

Timestamp (IST)

Coin traded

Side (BUY / SELL)

Execution price

Start position (used as a proxy for risk-taking)

Closed PnL

Fees, Order ID, and related trade details

Each row represents one executed trade.

2.2 Bitcoin Fear & Greed Index

The Fear & Greed Index is a daily sentiment indicator that classifies overall market mood into five categories:

Extreme Fear

Fear

Neutral

Greed

Extreme Greed

Each trade was labeled with the corresponding sentiment of that trading day.

3. Data Preparation

Before performing the analysis, I cleaned and aligned the datasets using the following steps:

Converted trading timestamps into proper datetime format

Extracted a clean date column from trading timestamps

Standardized the Fear & Greed date format

Performed a left merge on date to attach sentiment labels to each trade

Removed records without matching sentiment labels to create a clean merged dataset

This ensured consistency and accuracy across both datasets.

4. Analysis Performed

After preparing the merged dataset, I analyzed the following:

4.1 Profitability by Sentiment

Average Closed PnL under each sentiment condition

4.2 Trading Activity

Number of trades executed in each sentiment regime

4.3 Risk-Taking Behavior

Average start position used as a proxy for risk exposure

4.4 Win Rate

Percentage of profitable trades under each sentiment

4.5 Profit vs Loss Characteristics

Average profit of winning trades

Average loss of losing trades

5. Key Findings
5.1 Profitability and Sentiment

Extreme Greed showed the highest average profit per trade.

Profitability dropped significantly during Neutral and Greed conditions.

Extreme Fear days were nearly unprofitable on average.

This indicates that strong bullish sentiment creates more favorable trading conditions compared to panic-driven markets.

5.2 Trading Activity

Trading activity was highest during Fear.

It declined during Extreme Fear.

This suggests that moderate fear increases volatility and opportunity, while extreme panic discourages participation.

5.3 Risk-Taking Patterns

The largest average position sizes were taken during Neutral markets.

Position sizes dropped sharply during Fear.

This shows that traders tend to increase exposure when conditions feel stable and reduce risk when uncertainty rises.

5.4 Win Rate Trends

The highest win rate occurred during Extreme Greed.

The lowest win rate occurred during Extreme Fear.

Panic conditions appear to be significantly more difficult to trade profitably.

5.5 Profit vs Loss Behavior

Extreme Greed showed high average profits but also large losses, indicating aggressive behavior.

Fear had relatively strong profits with more controlled losses.

Greed showed weaker risk efficiency, with losses often larger than profits.

Neutral markets had smaller gains and smaller losses, reflecting lower volatility.

6. Overall Conclusion

The analysis clearly shows that market sentiment has a measurable impact on trader behavior.

Extreme Greed was the most profitable regime and had the highest win rate.

Traders were most active during Fear but reduced their position sizes.

The largest positions were taken during Neutral markets despite moderate profitability.

The results demonstrate that trading behavior, risk exposure, and performance are strongly influenced by overall market sentiment.

7. Tools and Technologies

Python

Pandas

NumPy

Matplotlib

Jupyter Notebook

8. How to Run the Project
Step 1: Clone the repository
git clone https://github.com/YOUR_USERNAME/trader-behavior-analysis.git

Step 2: Install dependencies
pip install -r requirements.txt

Step 3: Open the notebook
jupyter notebook analysis_clean.ipynb


Run all cells in order to reproduce the analysis.