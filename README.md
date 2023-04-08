# Factor-Model-Backtest
Research paper implementation on Factor Model, Back testing and Arbitrage

Could we use the #Macro data such as PMI, Bank profits, tax collection, IR futures, etc to forecast the infra and construction business (esp. in #emerging markets)?

To answer this I tried to implement some key ideas from the 3 papers:

1. Factor Model - Kozak et al. (2020): This paper investigates the #economic forces driving factor models and presents a decomposition method for cash flow and discount rate news components. It emphasizes the importance of interpreting factor models, helping investors improve investment strategies.

2. Backtest - Arnott et al. (2020): This paper stresses the importance of robust backtesting in the #machinelearning era, advocating for out-of-sample testing and combining machine learning with economic intuition. It presents the walk-forward methodology, a #backtesting technique that evaluates a model's performance through a step-by-step process:
#Train and test: Train the model on an in-sample data subset, test it on an out-of-sample subset, and assess its performance using relevant metrics.
#Walk forward: Incrementally expand the in-sample data with previous out-of-sample data and update the testing data, simulating real-time trading.
#Adapt and improve: Continuously assess the model's adaptability and robustness to changing market conditions, identifying potential issues and refining the model before live trading.

3. Arbitrage - Shleifer and Vishny: This paper discusses stock price anomalies, limits of #arbitrage, and noise trader #risk. It presents a model considering the interplay between arbitrageurs and noise traders, offering insights into #market inefficiencies and the role of arbitrage in financial markets.

Found some interesting results for various factors and a surprising backtest behavior. Below is the implementation, feel free to test around and extend it. Will be delving in deeper to further understand the papers and share results.

# Questions and ideas to think further 

PCA Analysis: I found that PCA is particularly beneficial when there are a large number of factors and these factors have a linear relationship among them. Otherwise, there is a risk of information loss.

Walk-forward backtesting strategy: Interestingly, the linear regression model outperformed XGBoost in this case. I am curious if this is due to overfitting and if the walk-through training and testing method is inherently more effective since it allows the model to encounter various patterns throughout market cycles.

Limits of Arbitrage: I gained insights into the anomalies that can explain differences between predicted and observed prices, beyond what the hidden Markov model could explain. I am considering if the concept could be applied to go long on factors with high exposure to stocks and short those with low exposure.
