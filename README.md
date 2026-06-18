# Multi-Seed Re-Examination of LLM-Augmented RL for Stock Trading

Code and results for ongoing research on multi-seed evaluation of an LLM-augmented reinforcement learning agent for Nasdaq-100 stock trading.

> **Note:** The accompanying paper is currently in preparation. Citation details will be added once the paper is publicly available.

## Overview

This repository contains code, multi-seed experiment results, and trained-model evaluation outputs for an LLM-augmented reinforcement learning trading agent (GN-PPO-CVaR) on the Nasdaq-100 (2019–2023).

The research extends prior single-seed work with:
- 3-seed evaluation of the signal coverage sweep
- 8-seed CVaR ablation
- Per-regime decomposition across 5 sub-windows
- Daily-vs-monthly rebalancing comparison

## Data

The experiments use the publicly available dataset:
[benstaf/nasdaq_2013_2023](https://huggingface.co/datasets/benstaf/nasdaq_2013_2023)

No data files are included in this repo. The notebook downloads the data automatically on first run via `datasets.load_dataset(...)`.

## Setup

Python 3.11. Install dependencies:

​```bash
pip install -r requirements.txt
​```

Hardware: an NVIDIA GPU with ≥8 GB VRAM is recommended. The experiments were run on an RTX A2000 8GB Laptop GPU.

## Reproducing the results

​```bash
jupyter notebook notebooks/FinAI_Final_v5.ipynb
​```

Run cells sequentially. Expected total runtime:
- Cells 1–9 (setup, smoke test): ~15 minutes
- Cell 10 (3-seed training): ~70 minutes
- Cells 11–18 (backtests, baselines, ablation): ~6 hours
- Cell 19 (multi-seed coverage sweep): ~15 hours
- Cells 21–30 (monthly, regime, summary): ~10 minutes

Pre-computed result files are in `results/` for verification without re-running.

## Results

Headline findings:

| Condition | Mean Return (%) | Std (%) | n seeds |
|---|---|---|---|
| Full agent, full coverage | 166.34 | 21.66 | 3 |
| No CVaR | 129.51 | 21.58 | 8 |
| No signals | 121.27 | 25.53 | 3 |
| Monthly variant ensemble | 104.61 | — | 3 |

See `results/coverage_sweep_multiseed.json` and `results/ablation_v3_matched_extended.json` for full data.

## License

MIT — see LICENSE file.

## Acknowledgments

This work was conducted under academic guidance at aivancity school for Technology, Business and Society, Cachan, France.
