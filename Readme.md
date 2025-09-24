# Fractional Brownian Motion Options Pricing Model

**Advanced Mathematical Modeling for Asset Pricing Using Fractional Stochastic Processes**

A sophisticated implementation of fractional Brownian motion (fBM) for options pricing that captures long-memory effects and non-Markovian dynamics in financial markets, demonstrating the application of advanced stochastic processes beyond traditional Black-Scholes assumptions.

## Project Overview

This project develops a novel asset pricing framework that combines **jump-diffusion processes with fractional Brownian motion** to model financial derivatives. Unlike standard geometric Brownian motion which assumes independent price movements, fBM incorporates **memory effects** where past price movements influence future behavior - a phenomenon observed in both biological systems and financial markets.

The model addresses key limitations of traditional options pricing by capturing:
- **Long-range dependence** in asset returns
- **Volatility clustering** effects
- **Heavy-tailed distributions** of price movements
- **Persistent vs anti-persistent** market behavior

## Technical Implementation

### Mathematical Framework

The core model extends the standard Black-Scholes SDE:

**Standard GBM:** `dS_t = rS_t dt + σS_t dW_t`

**Fractional Extension:** `dS_t = rS_t dt + σS_t dB_t^H`

Where `B_t^H` is fractional Brownian motion with Hurst parameter `H ∈ (0,1)`:
- `H > 0.5`: Persistent (trending) behavior
- `H < 0.5`: Anti-persistent (mean-reverting) behavior  
- `H = 0.5`: Standard Brownian motion

### Key Features

- **Multiple Hurst Parameter Estimation Methods**: R/S analysis and variance-based estimation
- **Efficient fBM Simulation**: Davies-Harte algorithm with O(n log n) complexity
- **Monte Carlo Options Pricing**: Large-scale simulation engine with confidence intervals
- **Greeks Calculation**: Numerical differentiation for Delta, Gamma, Vega, Theta
- **Model Validation**: Comprehensive comparison against Black-Scholes benchmarks
- **Advanced Visualizations**: 3D surface plots, interactive dashboards, statistical analysis

### Data Sources

- **Yahoo Finance API**: Historical stock price data
- **Alpha Vantage**: Options chain data (25 requests/day free tier)
- **Real Market Data**: Apple Inc. (AAPL) used as primary test case

## Installation & Usage

### Prerequisites

