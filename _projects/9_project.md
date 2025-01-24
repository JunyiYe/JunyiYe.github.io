---
layout: page
title: SafeLight
description: A reinforcement learning method toward collision-free traffic signal control
img: assets/img/safelight.svg
importance: 1
category: Transportation
related_publications: true
---

Traffic signal control is safety-critical for our daily life. Roughly one-quarter of road accidents in the U.S. happen at intersections due to problematic signal timing, urging the development of safety-oriented intersection control. However, existing studies on adaptive traffic signal control using reinforcement learning technologies have focused mainly on minimizing traffic delay but neglecting the potential exposure to unsafe conditions. We, for the first time, incorporate road safety standards as enforcement to ensure the safety of existing reinforcement learning methods, aiming toward operating intersections with zero collisions. We have proposed a safety-enhanced residual reinforcement learning method (**SafeLight**) {% cite Du_Ye_Gu_Li_Wei_Wang_2023 %} and employed multiple optimization techniques, such as multi-objective loss function and reward shaping for better knowledge integration. Extensive experiments are conducted using both synthetic and real-world benchmark datasets. Results show that our method can significantly reduce collisions while increasing traffic mobility.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/safelight.svg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 1. Reinforcement Learning (RL) framework with four possible ways of integrating safety modules in action, state, reward function, and loss function. Note that the RL model could be in any form.
</div>
