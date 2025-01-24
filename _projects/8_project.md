---
layout: page
title: Coarse2Fine ResNet
description: A robust and high-precision generalized deep learning framework for time delay estimation
img: assets/img/coarse2fine_resnet.svg
importance: 3
category: Computer Vision
---

Time delay estimation remains an active research area with broad applications across multiple fields. While conventional Generalized Cross-Correlation based approaches focus primarily on errors following normal distribution, they struggle with large estimation errors that deviate from normal distribution due to significant signal shifts. This paper presents **Coarse2Fine-ResNet**, a robust deep learning framework that effectively handles both types of errors by leveraging 2D GCC patterns and ResNet architecture. Evaluated on multiple datasets including acoustic drone flying, speaker localization, and optical fiber sensing, our method outperforms existing GCCs and state-of-the-art deep learning models in both estimation accuracy and reduction of Large Errors.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/coarse2fine_resnet.svg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 1. The framework of the proposed Coarse2Fine-ResNet.
</div>

As illustrated in Figure 1, the Coarse2Fine-ResNet framework transforms raw 1D signals into 2D correlation patterns using GCC-PHATs with different β values (0, 1/2, 1) to capture both phase and magnitude information. The Coarse Estimator analyzes these patterns to overcome large estimation errors by identifying true peaks among ghost peaks, producing an initial delay estimate. This estimate guides the selection of a Region of Interest (ROI) for the Fine Estimator to perform precise delay calculation. This dual-stage approach effectively mitigates both large estimation errors and improves overall accuracy.