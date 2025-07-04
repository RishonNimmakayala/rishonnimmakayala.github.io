---
layout: archive
title: "Trading Algorithms"
permalink: /tradingalgo/
author_profile: true
---




# Cross-Metal Statistical Arbitrage Engine with LSTM Model Integration  
**Rishon Reddy Nimmakayala**  
*04/2025*

---
## Overview

This project proposes the development of a quantitative framework and strategy that signals trading opportunities between cointegrated metals (Gold, Silver, Copper) through a statistical arbitrage lens. The goal is to identify historically co-moving metal pairs, measure their deviations in price behavior, and quantify the opportunity for mean-reverting relative value strategies.

---

## Motivation

COINS has increasingly emphasized spread-based trading strategies across commodity desks. Traditional arbitrage models rely on fixed parameters and assume linear relationships between commodity prices and macroeconomic indicators such as interest rates, inflation, and geopolitical factors. However, many of these relationships are non-linear, which limits the accuracy of linear models. To improve this, I propose building an LSTM-based model—leveraging its ability to capture long-term dependencies in time-series data—to provide more dynamic and responsive trade signals for the metals division.

---

## LSTM Foundations & Technicals

### Prologue: Recurrent Neural Network (RNN)

LSTM models are built on the foundation of recurrent neural networks (RNNs), which are designed for sequential data. RNNs process one input at a time while retaining hidden states, allowing them to "remember" previous inputs. This makes them well-suited for time-series data like commodity spreads. However, RNNs suffer from the vanishing/exploding gradient problem when dealing with long input sequences. LSTMs resolve this by introducing a gated memory architecture.

---

### Long-Short Term Memory: Structure

LSTMs introduce three gates:

- **Forget Gate**: Decides what information to discard from the cell state.
- **Input Gate**: Decides which values to update in the current state.
- **Output Gate**: Determines what the next hidden state should be.

These gates allow the model to selectively retain and update long-term and short-term memory. Using activation functions like sigmoid and tanh, the LSTM controls data flow and memory updates efficiently.

---

### Technical Summary

Each LSTM cell contains:

- A **cell state** for long-term memory.
- A **hidden state** for short-term memory.
- Nonlinear functions (sigmoid, tanh) to regulate memory updates.

The model begins with the forget gate, which filters previous memory. It then applies the input gate to update values based on new inputs. Finally, the output gate determines what is passed forward. This structure enables learning of temporal dependencies in spread data across metals.

---

## Metals Division Application

The LSTM model will be tested primarily on the **gold-silver spread**, chosen due to its high sensitivity to shared macroeconomic indicators like U.S. interest rates, inflation expectations, and the dollar index—yet with deviations due to industrial demand differences.

### Spread Definition

The spread will be defined as: Spread(t) = P_gold(t) - β * P_silver(t)

Where `β` is the hedge ratio determined via **cointegration testing**, aligning both metals based on historical price behavior.

### Input Variables

- Gold and silver futures prices  
- Hedge ratio (via cointegration)  
- U.S. Dollar Index (DXY)  
- Real interest rates  
- Federal Reserve announcements and meeting data  

The model will be trained on this multivariate time series to classify market states (bullish/bearish spread positions) and provide actionable signals.

---

## Goal

To create an interpretable and dynamic model that detects non-linear mean-reversion opportunities between metals, quantifies market mispricings, and supplements fundamental trade decisions with data-driven conviction.

---
