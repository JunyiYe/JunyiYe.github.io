---
layout: page
title: TextFlow2
description: a framework that converts flowchart images into text to improve explainability and control in flowchart understanding tasks
img: assets/img/textflow.png
importance: 3
category: "large language model"
related_publications: true
---

Flowcharts are typically presented as images, driving the trend of using vision-language models (VLMs) for end-to-end flowchart understanding. However, two key challenges arise: (i) **Limited controllability**—users have minimal influence over the downstream task, as they can only modify input images, while the training of VLMs is often out of reach for most researchers. (ii) **Lack of explainability**—it is difficult to trace VLM errors to specific causes, such as failures in visual encoding or reasoning.

We propose TextFlow {% cite ye2024beyond %}, addressing aforementioned issues with two stages: (i) **Vision Textualizer**—which generates textual representations from flowchart images; and (ii) **Textual Reasoner**—which performs question-answering based on the text representations. TextFlow offers three key advantages: (i) **users can select the type of text representations** (e.g., Graphviz, Mermaid, PlantUML), or further convert them into executable graph object to call tools, enhancing performance and controllability; (ii) **it improves explainability** by helping to attribute errors more clearly to visual or textual processing components; and (iii) **it promotes the modularization of the solution**, such as allowing advanced LLMs to be used in the reasoner stage when VLMs underperform in end-to-end fashion. Experiments on the FlowVQA and FlowLearn benchmarks demonstrate TextFlow's state-of-the-art performance as well as its robustness.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/textflow.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Our dual-stage TEXTFLOW (bottom) vs. prior work (top).
</div>

As illustrated in the above figure, the approach TextFlow consists of two main stages: (1) Vision Textualizer: A VLM converts the visual components of the flowchart into a high-quality text representation. (2) Textual Reasoner: An LLM or VLM based Texutal Reasoner can use tools
and interpret the text representations to answer questions related to the flowchart’s logic and structure. By decoupling these tasks, TextFlow enables specialized models to focus on their respective strengths: Vision Textualizer process the visual elements, while Textual Reasoner handle reasoning tasks, thus improving accuracy and flexibility.

{% endraw %}