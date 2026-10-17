# Neural Network-Based Market Direction Classification

A comparative study of classical machine learning and neural networks for predicting daily NIFTY 50 market direction.

## Overview

This project investigates whether historical price-derived features can help classify the next-session direction of the NIFTY 50 index. It compares conventional machine learning models with neural network architectures using chronological evaluation.

## Models

- Majority-class baseline
- Logistic Regression
- Feed-forward Neural Network (FNN)
- Long Short-Term Memory Network (LSTM)

## Methodology

- **Dataset:** Historical daily NIFTY 50 prices
- **Features:** Lagged returns, rolling volatility, momentum, and moving-average ratios
- **Target:** Whether the next closing price is higher than the current closing price
- **Evaluation:** Chronological train/validation/test split, walk-forward evaluation, and backtesting

## Preliminary Results

| Model | Test Accuracy |
|---|---:|
| Majority baseline | 50.49% |
| Logistic Regression | 46.58% |
| FNN | 49.84% |
| LSTM | 50.65% |

The LSTM achieved 50.65% test accuracy, only slightly above the majority-class baseline. The results suggest that predicting daily market direction from these features is challenging.

The initial backtest produced a total return of 1.06% for the LSTM and 0.47% for buy-and-hold under the simulation assumptions used. These preliminary results do not establish a reliable trading edge.

## Repository Structure

- `notebooks/`: Analysis and model experiments
- `reports/`: Written project reports
- `figures/`: Visualizations (to be added)
- `results/`: Model metrics and evaluation outputs (to be added)
- `src/`: Reusable project code (planned)

## Limitations

The initial backtest requires further checks of execution timing and transaction-cost assumptions. Additional evaluation using balanced metrics, repeated walk-forward testing, and more realistic trading assumptions is needed.

## Author

**Armaan Singh**  
I² Mathematics  
IISER Thiruvananthapuram, Kerala, India

## Disclaimer

This project is for educational and research purposes only. It is not investment advice.
