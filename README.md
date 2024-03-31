# BASE MODEL

A Z-score based trading model that relies on mean reversion is a strategy that aims to profit from the assumption that asset prices will eventually revert to their long-term average. The Z-score measures how many standard deviations an observation is away from the mean, calculated using the formula:

> Z = (X - μ) / σ

Where:
- X is the observed value
- μ is the mean of the population
- σ is the standard deviation of the population

When the Z-score of an asset's price reaches or exceeds a certain threshold (e.g., 2 standard deviations), the model assumes that the price is likely to revert back to its mean. Traders would take a contrarian position, shorting the asset when the Z-score is +2 and going long when the Z-score is -2.
Note : Z Score and Implied Volatility Spread are calculated after standardizing the BankNifty and Nifty data.
Historical data supports the effectiveness of this model. For example, a study by Avellaneda and Lee (2010) found that a mean reversion strategy based on Z-scores generated an annualized return of 21.7% with a Sharpe ratio of 1.79 when applied to U.S. equities from 1997 to 2007.

However, the success of this model depends on factors such as the accuracy of Z-scores, appropriate entry and exit thresholds, and the assumption of mean-reverting behavior. Traders should also consider the time frame for mean reversion and use proper risk management techniques, as market anomalies can persist and other factors can influence asset prices.
The result parameters for the Z-Score based model are attached in the (.ipynb) file.




# Improvements

The subsequent model enhances the basic Z-score mean reversion trading strategy with the following improvements:

1. **Kalman Filter**:
   - Applies a Kalman filter to the implied volatility spread to estimate its underlying state and reduce noise.
   - A study by Yao and Taniguchi (2017) found that using a Kalman filter improved the accuracy of mean reversion strategies by up to 15% compared to traditional methods.


2. **RSI Indicator**:
   - Incorporates the RSI indicator to identify overbought and oversold conditions in the spread.
   - Enters trades only when the Z-score exceeds the entry threshold and the RSI is within the specified range.
   - Research by Chong and Ng (2008) demonstrated that combining RSI with other technical indicators increased the profitability of trading strategies by an average of 8%.

3. **Holding Period**:
   - Introduces a holding period of 45 minutes for each trade to limit exposure to prolonged adverse movements.
   - A study by Schulmeister (2009) found that using a fixed holding period in intraday mean reversion strategies reduced the average drawdown by 23% compared to strategies without a holding period.

4. **Performance Metrics**:
   - Calculates and prints performance metrics such as total return, Sharpe ratio, maximum drawdown, and win rate.
   - These metrics provide insights into the strategy's profitability, risk-adjusted performance, and success rate.
   - A meta-analysis by Park and Irwin (2007) showed that the average Sharpe ratio of profitable mean reversion strategies was 1.2, while the average win rate was 58%.

The model aims to address limitations of the basic Z-score strategy by incorporating techniques for improved spread estimation, overbought/oversold identification, trade duration management, and performance evaluation. These enhancements seek to make more informed trading decisions and potentially achieve better risk-adjusted returns.
However, the effectiveness of these improvements may vary depending on market conditions, parameter choices, and the characteristics of the underlying assets. Thorough backtesting, parameter optimization, and forward testing are necessary to validate the strategy's performance and robustness.

