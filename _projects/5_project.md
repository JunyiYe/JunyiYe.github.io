---
layout: page
title: DySTAGE
description: Dynamic graph representation learning for asset pricing via spatio-temporal attention and graph encodings
img: assets/img/dystage.svg
importance: 1
category: Fintech
related_publications: true
---

Current GNN-based asset price prediction models often focus on a fixed group of assets and their static relationships within the financial network. However, this approach overlooks the reality that the composition of asset pools and their interrelationships evolves over time, necessitating the development of a flexible framework capable of adapting to this dynamism. Accordingly, we propose **DySTAGE** {% cite 10.1145/3677052.3698680 %}, a framework with a universal formulation that transforms asset pricing time series into dynamic graphs, accommodating asset addition, deletion, and changes in correlations. 

Our framework includes a graph learning model specifically designed for this purpose. In our framework, assets at various historical time steps are structured as a sequence of dynamic graphs, where connections between assets reflect their long-term correlations. DySTAGE effectively captures both topological and temporal patterns. The Topological Module deploys Asset Influence Attention to learn global interrelationships among assets, further enhanced by Asset-wise Importance Encoding, Pair-wise Spatial Encoding, and Edge-wise Correlation Encoding. Meanwhile, the Temporal Module encapsulates node representations across the temporal dimension via the attention mechanism. We validate our approach through extensive experiments using three different real-world stock pricing data, demonstrating that DySTAGE surpasses popular benchmarks in return prediction, and offers profitable investment strategies.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/dystage.svg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 1. The framework of DySTAGE. (1) Dynamic graph construction from time series (top right). (2) Dynamic graph learning model: (a) Topological Module individually processing structural information for each graph (left), (b) Temporal Module capturing historical representations across time (bottom right).

</div>