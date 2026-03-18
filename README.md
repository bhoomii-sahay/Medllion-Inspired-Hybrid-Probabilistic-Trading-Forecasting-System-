# Medllion-Inspired-Hybrid-Probabilistic-Trading-Forecasting-System-
Modular 3-day forecasting system using GMM-based regime detection, block bootstrap (5000+ paths), and ensemble models (rules + Random Forest). Features advanced time-series indicators and fractional Kelly sizing with tail-risk metrics. Deployed as a Telegram bot delivering real-time BUY/SELL/HOLD signals.

💼 Medallion-Style Quant Trading System
A Regime-Aware, Multi-Agent ML Trading Engine with Probabilistic Risk Modeling

🧠 Project Summary

This project builds a systematic trading engine that combines:

Statistical feature engineering

Regime detection (unsupervised learning)

Supervised ML (Random Forest)

Monte Carlo simulation (block bootstrap)

Risk-aware portfolio sizing (Kelly criterion)

Unlike toy trading bots, this system focuses on decision quality under uncertainty, not just prediction accuracy.

🏗️ ## System Architecture

Data → Features → Regime Detection → ML Model
        ↓                ↓              ↓
   Monte Carlo Simulation → Risk Metrics → Decision Engine → Trade Signal

 ⚡ Design Choice: Live Data System

This system uses live market data via yfinance instead of static datasets, enabling:

Real-time adaptability

Continuous signal generation

No dependency on pre-collected datasets

For evaluation, historical windows are dynamically constructed during runtime.
⚙️ Key Components
📊 Feature Engineering

Trend signals (SMA crossover)

Volatility clustering

Bollinger Band width

Volume anomalies (z-score)

Higher moments (skew, kurtosis)

👉 Captures non-linear market structure, not just price.

🧬 Regime Detection (Unsupervised Learning)

Gaussian Mixture Model (GMM)

Identifies latent states:

High volatility (risk-off)

Low volatility (compression)

Neutral

👉 Critical for context-aware trading

🤖 Machine Learning Model

Random Forest Classifier

Predicts next-period direction

Outputs:

Feature importance

Probabilities (not just labels)

👉 Focus on robust, interpretable ML

🎲 Monte Carlo Engine

Stationary Block Bootstrap

Preserves autocorrelation in returns

Generates:

Expected return

Downside probability

Tail risk (Expected Shortfall)

🧠 Multi-Agent Decision System

Agent	Role
Expectation Agent	Risk-adjusted edge
Structure Agent	Market conditions filter
ML Agent	Predictive signal

Final decision = ensemble voting system

📉 Risk Management

Half-Kelly position sizing

Volatility-adjusted exposure

Tail-risk awareness

📊 Example Output

Regime: neutral (97.8%)
Final Decision: HOLD
Position Size: 2%

3-Day Projection:
Expected: +0.12%
Downside: -3.87%
Upside: +3.37%
