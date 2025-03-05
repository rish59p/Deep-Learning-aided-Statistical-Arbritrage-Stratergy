# Deep-Learning-aided-Statistical-Arbitrage-Strategy (Pairs Trading)

## Overview
This project focuses on developing a deep learning-aided statistical arbitrage strategy for pairs trading, specifically within the Automobile and Heavy Industries sectors. The strategy involves several key steps including Principal Component Analysis (PCA) for market indicators, clustering using the OPTICS algorithm, and various statistical tests to identify and exploit mean-reverting pairs.

## Project Workflow

### 1. Principal Component Analysis (PCA)
To start, we performed PCA on the stock prices to extract key market indicators. This step is crucial for reducing dimensionality and identifying the underlying factors that drive the movements in stock prices.

### 2. Clustering with OPTICS Algorithm
Next, we employed the OPTICS (Ordering Points To Identify the Clustering Structure) algorithm to cluster stocks based on the PCA results. OPTICS is particularly useful for identifying clusters in data with varying densities, which is typical in financial markets.

### 3. Statistical Exit Tests
To identify eligible pairs for trading, we conducted several statistical tests:

- **Engle-Granger Cointegration Test**: This test checks if two or more non-stationary time series in a linear combination form a stationary TS, indicating a stable, mean-reverting relationship.
  
- **Hurst Exponent**: The Hurst exponent is used to determine the nature of the time series. A value of 0.5 suggests a random walk, less than 0.5 indicates mean reversion, and greater than 0.5 implies a trending behavior.
  
- **Mean Reverting Half-Life**: We calculated the mean reverting half-life using Arithmatic Ornstein-Uhlenbeck and AR(1) models. This metric tells us the average time it takes for the spread to revert to its mean. 
  
- **Average Mean Crossover Period**: This measures how frequently the spread crosses its mean, providing insights into the dynamics of the pair.

### 4. Strategy Implementation
Using the pairs identified from the statistical tests, we implemented the pairs trading strategy. The strategy involves:
- **Long/Short Positions**: Taking long positions on the undervalued stock and short positions on the overvalued stock within a pair.
- **Mean Reversion**: Squaring off positions when the market returns to equilibrium, thereby capturing profits from the mean reversion properties of the pairs.

## Market Universe
The strategy is applied to the Automobile and Heavy Industries sectors, which are chosen due to their distinct market behaviors and the potential for finding stable, mean-reverting pairs.

## Requirements
- Python 3.x
- Pandas
- NumPy
- Scikit-learn
- Statsmodels
- OPTICS from the Scikit-learn cluster module
- Hurst
- yfinance

## Installation
1. Clone the repository:
   \`\`\`bash
   git clone https://github.com/your-repo/Deep-Learning-aided-Statistical-Arbitrage-Strategy.git
   \`\`\`
2. Install the required packages:
   \`\`\`bash
   pip install -r requirements.txt
   \`\`\`

## Usage
1. **Data Preparation**: Load and preprocess the stock price data from the Automobile and Heavy Industries sectors.
2. **PCA**: Perform PCA to extract market indicators.
3. **Clustering**: Use the OPTICS algorithm to cluster the stocks.
4. **Statistical Tests**: Run cointegration tests, calculate the Hurst exponent, mean reverting half-life, and average mean crossover periods.
5. **Trading Strategy**: Implement the pairs trading strategy based on the identified mean-reverting pairs.

## Results
The strategy identifies pairs of stocks with mean-reverting properties and executes trades to exploit these characteristics. The performance of the strategy is evaluated based on the profitability of the trades and the frequency of mean reversion.

## Conclusion
This project demonstrates the application of deep learning and statistical methods to develop a robust pairs trading strategy. By leveraging PCA, clustering, and various statistical tests, we can identify and exploit mean-reverting pairs in the Automobile and Heavy Industries sectors.

## Future Work
- **Expand Market Universe**: Apply the strategy to other sectors and markets.
- **Incorporate Machine Learning Models**: Enhance the strategy with machine learning models to predict price movements and improve trade execution.
- **Optimize Parameters**: Continuously optimize the parameters of the strategy to adapt to changing market conditions.

##References:
- Hudson & Thames - Pairs Trading Guide
- quantsti Institute

## Contributors
- [Rishabh Patil](https://github.com/rish59p)
- [Anwesha Gopireddy](https://github.com/AnweshaG-29)
