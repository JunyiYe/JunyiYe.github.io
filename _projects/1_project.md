---
layout: page
title: TextFlow1
description: a framework that converts flowchart images into text to improve explainability and control in flowchart understanding tasks
img: assets/img/textflow.png
importance: 1
category: large language model
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


<!-- ---
layout: page
title: TextFlow - Beyond End-to-End VLMs
description: A dual-stage framework for superior flowchart understanding
img: assets/img/textflow.jpg
importance: 1
category: Large language model
related_publications: true
---

## Overview

TextFlow presents a novel approach to flowchart understanding that overcomes key limitations of end-to-end Vision Language Models (VLMs). By decomposing the process into two stages - Vision Textualizer and Textual Reasoner - TextFlow achieves superior performance while offering enhanced controllability and explainability.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/textflow.jpg" title="TextFlow Architecture" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    TextFlow's dual-stage architecture: Vision Textualizer converts flowcharts to structured text representations, while Textual Reasoner performs reasoning tasks on these representations.
</div>

## Key Innovations

TextFlow introduces several key innovations in flowchart understanding:

1. **Dual-Stage Framework**: By separating visual understanding from reasoning, TextFlow enables specialized models to focus on their respective strengths.

2. **Multiple Text Representations**: Support for various text formats (GRAPHVIZ, MERMAID, PLANTUML) allows flexibility in how flowcharts are represented and processed.

3. **Enhanced Controllability**: Users can select text representation types and convert them into executable graph objects for improved performance.

4. **Better Explainability**: The two-stage approach helps attribute errors more clearly to either visual or textual processing components.

5. **Modular Design**: Allows for the use of advanced LLMs in the reasoning stage when VLMs underperform in end-to-end processing.

## Results

<div class="row">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/textflow-results.jpg" title="Performance Comparison" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/textflow-analysis.jpg" title="Error Analysis" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left: Performance comparison across different models and approaches. Right: Error analysis showing the distribution of error sources.
</div>

Our experiments on the FlowVQA and FlowLearn benchmarks demonstrate TextFlow's superior performance:

- Achieved new state-of-the-art results (82.74 vs. 76.61 on FlowVQA)
- GRAPHVIZ emerged as the most effective text representation
- Demonstrated robustness across different:
  - Task categories
  - Flowchart sources
  - Orientations and sizes

## Key Findings

1. **Representation Effectiveness**: GRAPHVIZ proved to be the most effective text representation for flowcharts overall, while PLANTUML, though performing the worst, still surpassed end-to-end VQA baselines for Claude-3.5-Sonnet and GPT-4o.

2. **Robustness Analysis**: TextFlow showed strong robustness across:
   - Different VLM/LLM choices in both stages
   - Various flowchart orientations
   - Different flowchart sizes

3. **Error Analysis**: The majority of errors were attributed to the Vision Textualizer stage, particularly in handling complex node structures and decision nodes.

## Code and Resources

All code is publicly available on [GitHub](https://github.com/JunyiYe/TextFlow). The repository includes:

- Implementation of both Vision Textualizer and Textual Reasoner
- Support for multiple text representation formats and tool use
- Evaluation scripts and benchmarks
- Detailed documentation and examples

## Citation

If you use TextFlow in your research, please cite:

```bibtex
@article{ye2024beyond,
  title={Beyond End-to-End VLMs: Leveraging Intermediate Text Representations for Superior Flowchart Understanding},
  author={Ye, Junyi and Dash, Ankan and Yin, Wenpeng and Wang, Guiling},
  journal={arXiv preprint arXiv:2412.16420},
  year={2024}
}
``` -->