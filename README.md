# importance-sampling-option-pricing

The content of this notebook is based on Chapter 4 of the book "Monte Carlo Methods in Financial Engineering" by Paul Glasserman. <br>

## Overview

This project implements a Monte Carlo simulation for pricing a up-and-in European call option under the Geometric Brownian Motion (GBM) model.

To improve the efficiency and accuracy of standard Monte Carlo estimation, the project applies **importance sampling** as a variance reduction technique.

The goal is to compare the performance (variance and convergence speed) between standard Monte Carlo and importance sampling.

---

## Model Assumption

The underlying stock price follows a Geometric Brownian Motion (GBM):

$$\frac{dS(t)}{S(t)} = r dt + \sigma dW(t)$$

where:
- $S(t)$: stock price at time t  
- $r$: risk-free interest rate  
- $\sigma$: volatility  
- $W(t)$: Wiener process

---

## Option Type

- Up-and-in European Call Option
- Payoff: $max(S(T) - K, 0) 1_{\{max_{1 \le i \le m} S(t_i) > b\}}$
  Here, $b$ is a barrier

---

## Method

### Standard Monte Carlo
- Simulate the path of stock prices $S(t)$ using GBM
- Compute discounted payoff
- Take average over all paths

### Importance Sampling
- Use Girsanov thorem to tilt a Wiener process
- Simulate the path of stock prices $S(t)$ using GBM
- Compute discounted payoff
- Take the average of all paths using a likelihood ratio

---

## Features

- GBM-based stock price simulation
- Up-and-in European call option pricing
- Standard Monte Carlo estimator
- Importance sampling implementation
- Girsanov theorem
- Confidence interval comparison between methods

---

## Tech Stack

- Python
- NumPy

---

## Results

Stratified sampling shows:
- Lower variance (i.e., narrower confidence interval) compared to standard Monte Carlo

---

## References

1. Glasserman, P. (2003) *Monte Carlo Methods in Financial Engineering*. Springer, New York.

---
