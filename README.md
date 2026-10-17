[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Julius-Scissor/Financial-Market-Direction-ML/blob/main/notebooks/01_market_direction_analysis.ipynb)
# Neural Network-Based Market Direction Classification

A quantitative research project investigating whether historical NIFTY 50 price-derived features can predict short-horizon market direction. The project compares a majority-class baseline, Logistic Regression, a feed-forward neural network (FNN), and a Long Short-Term Memory network (LSTM).

## Research Objective

The objective is to evaluate whether classical machine learning and neural network models can identify useful directional signals from historical market features, and whether those signals translate into improved simulated trading performance after transaction costs.

This is an educational research project, not a production trading system.

## Models

- Majority-class baseline
- Logistic Regression
- Feed-forward Neural Network (FNN)
- Long Short-Term Memory network (LSTM)

## Features and Target

The models use 12 price-derived features:

- Lagged returns over five sessions
- Rolling volatility over 5, 10, and 20 sessions
- Moving-average ratios over 5 and 20 sessions
- Momentum over 5 and 10 sessions

The target-aligned experiment predicts whether the return from the next session's open to the following session's open is positive.

$$\[
r_t = \frac{O_{t+2}}{O_{t+1}} - 1
\]$$

The binary target is 1 when this return is positive and 0 otherwise.

## Evaluation Methodology

The experiment uses chronological training, validation, and test splits. The target-aligned experiment includes a two-row purge at the training and validation boundaries to reduce forward-label overlap.

Feature scaling is fitted on training data only. Validation data is used for model selection and early stopping, while the final test period is reserved for reporting.

The simulated trading strategy is long-or-cash:

- Signals are generated using information available through the current close.
- Positions are entered at the following session's open.
- The holding period runs from one session's open to the next session's open.
- The reported backtest assumes a one-way transaction cost of 0.1%.
- Results are compared with a buy-and-hold benchmark over the same test window.

## Final Purged Test Results

Test period: 4 April 2024 to 24 September 2026.

| Model | Accuracy | Balanced Accuracy | MCC | Total Strategy Return |
|---|---:|---:|---:|---:|
| Majority baseline | 50.33% | 50.00% | 0.0000 | +2.37% |
| Logistic Regression | 50.16% | 49.89% | -0.0041 | -0.27% |
| FNN | 49.02% | 48.73% | -0.0555 | -11.79% |
| LSTM | 47.88% | 47.62% | -0.0762 | -8.99% |
| Buy and Hold | N/A | N/A | N/A | +2.37% |

The majority baseline matches buy-and-hold because it predicts the positive class for every observation and remains invested. The learned models did not outperform this baseline in the final test evaluation.

These results do not establish a reliable predictive or trading edge.

## Repository Structure

- `notebooks/`: Notebook-based analysis and experiments
- `reports/`: Research reports
- `results/`: Classification metrics, predictions, backtest results, cost sensitivity analyses, and audit exports
- `requirements.txt`: Python dependencies
- `.gitignore`: Files excluded from version control

## Limitations and Future Work

- Predictive performance is close to the majority-class baseline.
- The neural networks show weak out-of-sample directional performance.
- Transaction costs and opening-price execution are simplified assumptions; actual fills, slippage, liquidity, and market impact may differ.
- Further work should include repeated walk-forward evaluation, probability calibration, statistical uncertainty estimates, and realistic execution assumptions.
- The results are specific to this dataset, feature set, split, and modeling configuration.

## Reproducibility

The analysis notebook and exported CSV files are available in this repository. The notebook can be opened in Google Colab to inspect the workflow and reproduce the experiments, subject to the availability of the source data and dependencies.

## Author

**Armaan Singh**  
I² Mathematics  
IISER Thiruvananthapuram, Kerala, India

## Disclaimer

This project is for educational and research purposes only. It is not investment advice and should not be used as the sole basis for trading decisions.
