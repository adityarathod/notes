# OLPS Survey Paper Notes
## 1. Introduction
- **Portfolio selection** aims to optimize the allocation of wealth across a set of assets
- A fundamental research problem in computational finance and is something financial engineers really case about
- Two major schools:
  - Mean-Variance Theory: origins in modern finance theory
    - Focuses on single-period portfolio selection to determine the best tradeoff between expected return and risk
  - Capital Growth Theory (CGT): origins in information theory
    - Focuses on multi-period portfolio selection, aiming to maximize portfolio's growth rate
- **Online portfolio selection** sequentially selects a portfolio over a set of assets while aiming to maximize cumulative wealth
  - "Online" in the sense that market information arrives sequentially and decisions must be made immediately

## 2. Problem Setting
A financial market has $m$ assets, and we trade over $n$ different trading periods.

We represent prices changes in the market by a $m$-dimensional _price relative vector_ $\mathbf{x}_t \in \mathbb{R}^{m}$, where $t=1,2,...,n$, representing the the ratio of $t$ th closing price to $t-1$ th closing price. Each element $\mathbf{x}_{t,i}$ is that ratio for the $i$ th asset