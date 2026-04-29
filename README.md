# Signal Density Matters: Multi-Point LLM Integration in Risk-Constrained RL for Stock Trading

## Overview

This repository contains the code for our paper investigating GRPO-CVaR, 
a critic-free reinforcement learning algorithm with CVaR tail-risk constraints 
for Nasdaq-100 stock trading, and the effect of LLM signal density on 
multi-point signal injection.

## Key Findings

- **GRPO-CVaR** combines critic-free group advantage estimation with CVaR 
  constraints, training on a single GPU in ~55 minutes
- **CVaR adds 11.47 percentage points** of return over GRPO alone
- **LLM signals at 9.7% coverage hurt performance** — the signal-free 
  variant (131.49% return) outperforms the full model (122.26%)
- Signal density is the critical bottleneck for LLM-augmented trading

## Results (2019-2023 Backtest)

| Metric | Value |
|--------|-------|
| Cumulative Return | 119.56% |
| Max Drawdown | 31.36% |
| Rachev Ratio | 0.9288 |
| Sharpe Ratio | 0.8003 |

## How to Run

1. Open ` Multi-Point LLM Integration in Risk-Constrained RL for Stock Trading.ipynb` in [Google Colab]([https://colab.research.google.com](https://colab.research.google.com/drive/1vT13_vvidc-wcxUGyLTlcFrvsxvpdnId?usp=sharing))
2. Run all cells in order (total time: ~3 hours)
3. Results will be saved in `logs/`

## Data

Training: Nasdaq-100 stocks, Jan 2013 - Dec 2018 (1,509 trading days, 84 stocks)  
Evaluation: Jan 2019 - Dec 2023 (1,258 trading days)  
Source: [FNSPID dataset](https://huggingface.co/datasets/benstaf/nasdaq_2013_2023)

## References

- [FinRL-DeepSeek](https://arxiv.org/abs/2502.07393) (Benhenda 2025)
- [DAPO for Stock Trading](https://arxiv.org/abs/2505.06408) (Zha et al. 2025)
- [DeepSeekMath / GRPO](https://arxiv.org/abs/2402.03300) (Shao et al. 2024)
- [FNSPID Dataset](https://github.com/Zdong104/FNSPID) (Dong et al. 2024)

## Author

Shafiya Kausar — AIvancity School of AI and Data, Paris
