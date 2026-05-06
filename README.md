# When LLM Signals Hurt: A Coverage-Density Analysis of LLM-Augmented RL for Stock Trading

This repository hosts the paper *"When LLM Signals Hurt: A Coverage-Density Analysis of LLM-Augmented Reinforcement Learning for Stock Trading,"* which reports negative results on LLM-augmented reinforcement learning for stock trading evaluated on Nasdaq-100 (2019–2023).

📄 **Paper PDF:** FinAI Paper

## Headline findings

1. **Signal density curve.** LLM signal injection at sparse coverage (≤20%) performs *worse* than no signals at all. The FNSPID dataset's 9.7% non-neutral coverage sits inside this harmful regime.

2. **Baseline gap.** The LLM-augmented RL agent (158.11% cumulative return as a 3-seed ensemble) underperforms three standard non-RL baselines: momentum top-10 (250.45%), equal-weight buy-and-hold (235.00%), and equal-weight monthly rebalanced (214.06%).

3. **Rebalancing-frequency control.** Deploying the same trained agents under matched monthly execution drops returns by 47pp, ruling out daily-rebalancing transaction costs as the explanation for the baseline gap.

4. **CVaR null result.** Removing the CVaR tail-risk constraint produces an effect within seed-to-seed noise; the sign of the effect flipped across two independent runs of the same code.

5. **Per-regime decomposition.** The agent does outperform all non-RL baselines in the 2023 recovery period (52.6% vs. 20–39%), suggesting regime-specific advantages obscured by single-window evaluation.

## Methodological recommendations

The paper argues that researchers in LLM-augmented RL trading should adopt four practices as standard:

- Compare against non-RL baselines (momentum top-k, equal-weight monthly rebalanced)
- Report signal coverage density as a first-class experimental variable
- Control for rebalancing frequency between agent and baselines
- Decompose returns by market regime rather than aggregating into a single window

## Status

- **Submitted to:** NeurIPS 2026
- **HAL:** *pending validation — link will be added once live*
- **arXiv:** *pending endorsement — link will be added once live*

## Code availability

Code and trained models are not currently included in this repository. They will be released after the June 2026 conference presentation. For NeurIPS reviewer access during the review period, an anonymous code repository is referenced in §1 of the paper.

## Citation

If you reference this work, please cite:

```bibtex
@misc{kausar2026signaldensity,
  title={When LLM Signals Hurt: A Coverage-Density Analysis of LLM-Augmented Reinforcement Learning for Stock Trading},
  author={Kausar, Shafiya and [Co-authors]},
  year={2026},
  howpublished={Submitted to NeurIPS 2026},
  url={https://github.com/YOUR_USERNAME/signal-density-llm-trading}
}
```

## License

The paper PDF is licensed under [Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International (CC BY-NC-ND 4.0)](LICENSE). You may share the paper with attribution, but you may not modify it or use it for commercial purposes without permission.

## Contact

For questions or collaboration: shafiya.kausar@aivancity.education
