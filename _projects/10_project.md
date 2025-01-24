---
layout: page
title: Time-Series Mixer
description: Prediction with time-series mixer for the S&P500 index
img: assets/img/ts_mixer.svg
importance: 3
category: Fintech
related_publications: true
---

As an essential US economic indicator, the S&P500 Index is used to assess the current state of market performance and gauge the economy’s future course. However, stock market index prediction is challenging due to its nonlinearity and inherently volatile character. Recurrent Neural Networks (RNN) and their variants are de facto standards for sequence modeling. Recently, Convolutional Neural Networks (CNN) and attention-based networks, such as dilated casual convolutions and Transformers, have also become popular in time series forecasting. In this paper, we report on the design of a **Time-Series Mixer (TS-Mixer)** {% cite ye10148151 %} architecture based on MLP-Mixer, an all-MLP architecture for time series forecasting. 

To the best of our knowledge, this is the first implementation of MLP-Mixer-based architecture for sequence modeling. Modern deep learning models are increasingly built to handle univariate time series data. They generally pay attention to analyzing temporal dependencies while ignoring the relationship among features. The proposed architecture is specifically created for multivariate time series forecasting to capture temporal feature interactions while simultaneously learning feature correlations. To accomplish this, the proposed Time-Feature Mixer contains two types of MLP layers: feature mixer and temporal mixer. The feature mixer is applied independently to each data point to capture the correlation among features. In contrast, the temporal mixer extracts temporal dependency (trend, seasonal, cyclical, or random characteristics) of each feature across the whole input sequence. Compared to prevalent neural networks in sequence modeling, TS-Mixer exhibits competitive performance regarding S&P500 Index prediction.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/ts_mixer.svg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 1. The Architecture of TS-Mixer. The macro-structure of TS-Mixer (top-left). The illustration of MLP1 and MLP2 blocks (bottom-left). Three types of Mixer block design (right). (1) Mixer block (the same Mixer block in MLP-Mixer); (2) MixerReverse block; (3) MixerParallel block.
</div>
