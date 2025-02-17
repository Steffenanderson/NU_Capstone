# Reinforcement Learning-Based Systematic Trading Model

## Overview
This project implements a **reinforcement learning-based systematic trading model** optimized for SPY. The model applies machine learning techniques to predict market movements and automate trade execution. It leverages **Proximal Policy Optimization (PPO)** combined with **Random Forest feature selection** to maximize risk-adjusted returns while controlling drawdowns.

## Key Features
- **High Performance:** Achieved a **97.06% return** over **267 trading days**, with a **Sharpe Ratio of 4.03** and a **max drawdown of 9.0%**.
- **Feature Engineering:** Utilizes a diverse set of indicators, including:
  - **Overlap Studies** (Bollinger Bands, Moving Averages, Parabolic SAR)
  - **Momentum Indicators** (RSI, MACD, Stochastic Oscillator)
  - **Volume & Volatility Indicators** (OBV, ATR, Standard Deviation)
  - **Statistical Analysis** (Linear Regression, Beta, Correlation)
- **Automated Execution:** Implements a live execution framework via **Alpaca API**, handling trade execution and risk management autonomously.
- **Reinforcement Learning (RL):** Utilizes **PPO** within a custom **Gym trading environment** to optimize buy/sell decisions based on market conditions.
- **Feature Selection Optimization:** Implements **Recursive Feature Elimination (RFE)** and **Variance Inflation Factor (VIF)** for reducing multicollinearity and enhancing model performance.

## Model Architecture
1. **Data Preprocessing & Feature Engineering:**
   - Fetches **historical market data** via the **Alpaca Market Data API**.
   - Generates technical indicators for trend analysis, momentum evaluation, and risk assessment.
   - Normalizes and selects relevant features using **Random Forest** and **VIF-based filtering**.

2. **Reinforcement Learning Training Pipeline:**
   - Constructs a custom **Gym trading environment**.
   - Trains **PPO agent** using historical data for policy optimization.
   - Evaluates model performance on a separate test dataset.

3. **Live Trading Execution:**
   - Integrates with **Alpaca API** for order execution.
   - Implements real-time **risk management strategies**.
   - Monitors portfolio performance and adjusts trading actions dynamically.

## Performance Metrics
| Metric             | Value        |
|-------------------|-------------|
| Return (%)        | 97.06%       |
| Sharpe Ratio      | 4.03         |
| Max Drawdown (%) | 9.0%         |
| Avg Holding Period | 17 days     |
| Benchmark        | Outperformed SPY |

## Installation & Setup
### Prerequisites
Ensure you have **Python 3.8+** and install the required dependencies:
```bash
pip install -r requirements.txt
```
### API Configuration
Obtain Alpaca API credentials and set up environment variables:
```bash
export ALPACA_API_KEY='your_api_key'
export ALPACA_API_SECRET='your_api_secret'
export ALPACA_BASE_URL='https://paper-api.alpaca.markets'
```

## Usage
### 1. Train the Reinforcement Learning Model
```bash
python train.py
```
### 2. Evaluate Model Performance
```bash
python evaluate.py
```
### 3. Run Live Trading
```bash
python live_trading.py
```

## Results Visualization
To analyze the model's trading performance, execute:
```bash
python visualize_results.py
```
This generates key **performance charts**, including **cumulative returns, drawdowns, and trade entry/exit points**.

## Future Improvements
- **Fine-tune Hyperparameters** for improved generalization.
- **Explore Alternative RL Algorithms** (e.g., SAC, DDPG) for enhanced decision-making.
- **Enhance Risk Management** through dynamic stop-loss and position sizing strategies.
- **Expand to Multi-Asset Trading** for improved portfolio diversification.

## Author
**Steffen Anderson** – Data Scientist

## License
This project is licensed under the MIT License.

## Acknowledgments
- **OpenAI Gym** for reinforcement learning environment support.
- **Alpaca API** for seamless market data access and trade execution.
- **TA-Lib** for technical indicators computation.

---
This README provides an **informative and structured** overview of your project, ensuring clarity for other developers and quant researchers interested in systematic trading strategies.

