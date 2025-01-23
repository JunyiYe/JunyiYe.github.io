---
layout: page
title: project 1
description: with background image
img: assets/img/12.jpg
importance: 1
category: work
# related_publications: true
---

Every project has a beautiful feature showcase page.
It's easy to include images in a flexible 3-column grid format.
Make your photos 1/3, 2/3, or full width.

To give your project a background in the portfolio page, just add the img tag to the front matter like so:

    ---
    layout: page
    title: project
    description: a project with a background image
    img: /assets/img/12.jpg
    ---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/1.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/3.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Caption photos easily. On the left, a road goes through a tunnel. Middle, leaves artistically fall in a hipster photoshoot. Right, in another hipster photoshoot, a lumberjack grasps a handful of pine needles.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>

You can also put regular text between your rows of images, even citations {% cite einstein1950meaning %}.
Say you wanted to write a bit about your project before you posted the rest of the images.
You describe how you toiled, sweated, _bled_ for your project, and then... you reveal its glory in the next row of images.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>

The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

{% raw %}

```html
<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
```

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