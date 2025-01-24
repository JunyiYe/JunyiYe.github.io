---
layout: page
title: Margin Trader LLM
description: Adaptive and explainable margin trading via LLMs on portfolio management
img: assets/img/margin_trader_llm.svg
importance: 2
category: Fintech
related_publications: true
---

Recent strategies for portfolio management often lack flexibility to adjust funds between long and short positions throughout trading periods. This prevents adapting portfolios to the market, which mitigates risks and seizes opportunities. To address these gaps, we propose an adaptive and explainable framework that integrates Large Language Models (LLMs) with Reinforcement Learning (RL) for dynamic long-short position adjustment in response to evolving market conditions {% cite 10.1145/3677052.3698681 %}. This approach leverages the recent advancements in LLMs for processing unstructured data and their capacity for explainable reasoning. 

The framework includes two stages: an Explainable Market Forecasting/Reasoning Pipeline, and a Position Reallocation stage. The Market Forecasting/Reasoning Pipeline allows various LLMs to learn market trends from diverse external data sources and determine optimal adjustment ratios with a clear reasoning path. The Portfolio Reallocation stage interacts with the sequential trading process from a pre-trained RL model to enhance decision-making and transparency. Our framework is flexible to accommodate various external data sources from microeconomics to macroeconomics data, diverse data types including time series and news text, along with multiple LLMs. Experiments demonstrate that our framework effectively achieves three times the return and doubles the Sharpe ratio compared to benchmarks.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/margin_trader_llm.svg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 1. The framework presents the interaction of the two-stage adjustments with the pre-trained RL trading model. Stage 1 (Market Forecasting/Reasoning Pipeline) employs LLMs to predict and analyze future stock market trends, utilizing various data sources. Stage 2 (Position Reallocation) updates the states in the RL process by adjusting the long-short ratio based on the insights gained from LLMs.
</div>