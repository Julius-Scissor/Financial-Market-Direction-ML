# Neural Network-Based Market Direction Classification

**A comparative study of classical machine learning and neural networks for daily NIFTY 50 market-direction prediction.**

## Overview

Can historical price-derived features help predict whether the NIFTY 50 index will close higher on the next trading session?

This project investigates that question by comparing a simple majority-class baseline, Logistic Regression, a feed-forward neural network (FNN), and a Long Short-Term Memory network (LSTM). Models are evaluated using chronological data splits to respect the time-series structure of financial data.

## Research Setup

- **Market:** NIFTY 50 index
- **Prediction task:** Binary next-session direction classification
- **Target:** 1 if the next close exceeds the current close, otherwise 0
- **Features:** Lagged returns, rolling volatility, momentum, and moving-average ratios
- **Evaluation:** Chronological train/validation/test split, walk-forward evaluation, and an initial trading simulation

## Models

1. Majority-class baseline
2. Logistic Regression
3. Feed-forward Neural Network (FNN)
4. Long Short-Term Memory Network (LSTM)

## Preliminary Test Results

| Model | Accuracy |
|---|---:|
| Majority-class baseline | 50.49% |
| Logistic Regression | 46.58% |
| FNN | 49.84% |
| LSTM | 50.65% |

The LSTM achieved 50.65% test accuracy, a small improvement over the 50.49% majority-class baseline. These results indicate that daily market-direction prediction remains challenging with the selected features and models.

### Initial Backtesting Results

The original simulation reported a total return of **+1.06% for the LSTM** and **+0.47% for buy-and-hold** under its specified assumptions.

These figures are preliminary, not evidence of a reliable trading edge. Execution timing and transaction-cost treatment require further validation before drawing conclusions about practical profitability.

## Methodology

The workflow includes:

1. Historical price data preparation and exploratory analysis.
2. Feature engineering using lagged returns, volatility, momentum, and moving-average ratios.
3. Chronological training, validation, and test splits.
4. Model training and comparison against a simple baseline.
5. Walk-forward evaluation and an initial backtesting analysis.

## Repository Structure

- `notebooks/`: Main analysis and model experiments.
- `reports/`: Written project reports.
- `results/`: Results documentation and, as the project develops, machine-readable evaluation outputs.

## Reproducibility

Open the notebook in Google Colab or Jupyter Notebook. Install the dependencies listed in `requirements.txt`, then follow the notebook cells in order.

The exact data source, package versions, and any required data-download steps should be documented alongside the notebook to support reproducibility.

## Limitations and Future Work

- Evaluate balanced accuracy, macro F1, and Matthews correlation coefficient.
- Verify that feature construction and validation avoid information leakage.
- Use a feasible trade-execution convention after a prediction is generated.
- Apply transaction costs consistently to strategy and benchmark returns.
- Expand walk-forward testing to assess the stability of any predictive signal.

## Author

**Armaan Singh**  
I² Mathematics  
IISER Thiruvananthapuram, Kerala, India

## Disclaimer

This project is for educational and research purposes only. It is not investment advice.
