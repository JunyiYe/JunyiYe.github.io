---
layout: page
title: FaultyMath
description: Benchmarking LLMs’ logical integrity on faulty mathematical problems
img: assets/img/faulty_math_problem.svg
importance: 4
category: Generative AI
related_publications: true
---

Consider the math problem: "Lily received 3 cookies from her best friend yesterday and ate 5 for breakfast. Today, her friend gave her 3 more cookies. How many cookies does Lily have now?" Many LLMs solve this by calculating "1" using the equation "3 - 5 + 3." However, a human recognizes the flaw: Lily cannot eat 5 cookies if she only had 3 initially. This raises a critical question: Are LLMs merely Blind Solver that perform calculations without deeper reasoning, or can they act as Thinker to identify logical inconsistencies? 

To investigate, we introduce **FaultyMath** {% cite rahman2024blind %}, a benchmark of diverse faulty math problems spanning multiple categories (e.g., algebra, geometry), difficulty levels, and origins of faultiness (e.g., common sense violations, ambiguity, contradictions). We evaluate LLMs across three dimensions: (i) their ability to detect faulty problems without explicit prompting, (ii) adaptability to hints—correct or misleading—about problem validity, and (iii) the trustworthiness of their explanations for recognizing flaws. Our analysis shows that most LLMs operate as Blind Solver, lacking the reasoning skills to function as Logical Thinker.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/faulty_math_problem.svg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 1. FaultyMath curation process. Three stages: (i) GPT-4 converts valid math problems
into faulty ones; (ii) GPT-4 self-verifies; (iii) human verification.

</div>