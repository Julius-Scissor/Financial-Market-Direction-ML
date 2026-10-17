# Results and Evaluation

This directory documents the evaluation results for the Neural Network-Based Market Direction Classification project.

## Test-set classification accuracy

| Model | Accuracy |
|---|---:|
| Majority-class baseline | 50.49% |
| Logistic Regression | 46.58% |
| Feed-forward Neural Network (FNN) | 49.84% |
| Long Short-Term Memory Network (LSTM) | 50.65% |

## Preliminary backtesting

The initial backtest produced the following total returns under the project's simulation assumptions:

| Strategy | Total return |
|---|---:|
| FNN | -10.42% |
| Logistic Regression | -31.51% |
| LSTM | +1.06% |
| Buy and Hold | +0.47% |

## Interpretation

The LSTM achieved only a small improvement over the majority-class accuracy baseline. Its preliminary backtest return was also modest, and these results do not establish a reliable trading edge.

The classification results require further evaluation using balanced metrics, and the backtest requires additional checks of execution timing and transaction costs.

These are preliminary research results, not investment advice.
