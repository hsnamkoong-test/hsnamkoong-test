---
layout: distill
title: research highlight
description: My research develops AI-driven approaches to decision-making, with a particular emphasis on trustworthy and responsible learning methods. This requires an interdisciplinary approach spanning several fields including machine learning, operations research, and statistics. 
tags: distill formatting
giscus_comments: true
date: 2024-06-12
featured: true
nav: true
nav_order: 2

authors:
  - name: Hongseok Namkoong
    affiliations:
      name: Columbia University

bibliography: mybib.bib

# Optionally, you can add a table of contents to your post.
# NOTES:
#   - make sure that TOC names match the actual section names
#     for hyperlinks within the post to work correctly.
#   - we may want to automate TOC generation in the future using
#     jekyll-toc plugin (https://github.com/toshimaru/jekyll-toc).
toc:
  - name: Research philosophy and methodology
    # if a section has subsections, you can add them as follows:
    # subsections:
    #   - name: Example Child Subsection 1
    #   - name: Example Child Subsection 2
  - name: Trustworthy AI
    subsections:
#      - name: Comprehending uncertainty
      - name: Language for distribution shifts
      - name: Foundations of distributional robustness
  - name: AI-driven decisions
    subsections:
      - name: Adaptive experimentation at scale
      - name: Online decision-making with scalable ML tools
      - name: AI-based service systems
#      - name: Auto-differentiable discrete event simulation
  - name: Robust causal inference and off-policy learning
    subsections:
      - name: External validity
      - name: Unobserved confounding
      - name: Unforeseen data sparsity

# Below is an example of injecting additional post-specific styles.
# If you use this post as a template, delete this _styles block.
_styles: >
  .fake-img {
    background: #bbb;
    border: 1px solid rgba(0, 0, 0, 0.1);
    box-shadow: 0 0px 4px rgba(0, 0, 0, 0.1);
    margin-bottom: 12px;
  }
  .fake-img p {
    font-family: monospace;
    color: white;
    text-align: left;
    margin: 12px 0;
    text-align: center;
    font-size: 16px;
  }
---

## Research philosophy and methodology

I take a holistic “industrial engineering” view of AI systems, studying them from data collection to deployment & monitoring.

<div class="img l-body">
  <p>{% include figure.liquid loading="eager" path="assets/img/ai-overview.jpg" title="AI Overview" class="img-fluid rounded z-depth-1" %} </p>
  <div class="caption">
    <strong> Process view of AI (not just a single model): </strong>
        Methodological development in ML largely focuses on model training. Taking a system-level view, my research identifies bottlenecks in the process and algorithms to resolve them.     
    </div>
</div>


The standard algorithmic development paradigm for decision-making relies on theoretical performance guarantees and as a result, often ignore important operational constraints or are non-performant in practice. While theoretical insights can provide invaluable principles, their successful operationalization requires recognizing and internalizing the limitations of crude approximations and unverifiable assumptions we put in place for mathematical convenience. 

My research group identifies central intellectual bottlenecks in real-world problems, and resolve them by building computational and data-centric foundations borne out of mathematical principles. Our research methodology aims to connect two disparate yet complementary worldviews:

- computational tools and mathematical insights from statistical learning, optimization, applied probability, and casual inference
- rigorous empirical benchmarking practices arising from the AI research community’s data-centric approach.

I take inspiration from [Von Neumann’s perspective on mathematical sciences](/assets/pdf/TheMathematician.pdf), which I paraphrase below:

<blockquote style="font-size: 1em;">
    As a mathematical discipline travels far from its empirical source only indirectly inspired from ideas coming from 'reality', it is beset with grave dangers that it will develop along the line of least resistance and become more and more purely aestheticizing. This need not be bad if the discipline is under the influence of researchers with an exceptionally well-developed taste, but the only general remedy is the rejuvenating return to the source: the reinjection of directly empirical ideas. I am convinced that this is a necessary condition to conserve the freshness and the vitality of the subject, and that this will remain so in the future. 
</blockquote>

I am fortunate to be able to learn from the well-developed taste of my wonderful colleagues. Concurrent to this personal education, I (try to) inject empirical ideas to formulate research directions to increase the impact of my research.

---

## Trustworthy AI

Modern data collection systems acquire data from heterogeneous sources, and classical approaches that optimize average-case performance yield brittle AI systems. They fail to

- make good predictions on underrepresented groups
- generalize to new environments, even those similar to that seen during training
- be robust to adversarial examples and long-tailed inputs.

Yes, even the largest models trained on the entirety of the internet! 

Despite recent successes, lack of understanding on the failure modes of AI systems highlights the need for models that i) reliably work and ii) rigorous evaluation schemes and diagnostics that maintain their quality. 

### Language for distribution shifts

Different distribution shifts require different solutions. Understanding *why* model performance worsened is a fundamental step for informing subsequent methodological and operational interventions. Heterogeneity in data helps robustness, but the cost of data collection is often a binding constraint. We build a nuanced modeling language for quantifying data heterogeneity (or lack thereof), and use it to make optimally allocate limited resources in the AI production pipeline. To learn more, watch the following [NeurIPS tutorial](https://nips.cc/virtual/2023/tutorial/73953) and take a look at the following two papers.

<div class="img l-body">
  <div class="text-center">
        <!-- 
            <p style="font-size: 1.3em;"><a href="https://nips.cc/virtual/2023/tutorial/73953" target="_blank"><strong>NeurIPS 2023 Tutorial</strong></a></p> 
            -->
            <a href="https://nips.cc/virtual/2023/tutorial/73953" target="_blank">
                <img src="/assets/img/neurips-tutorial-2023.png" alt="Watch the tutorial" width="460" height="130" border="10" />
            </a>
  </div>
  <div class="publications">
        {% bibliography -q @*[key=CaiNaYa23]* %}
  </div>
  <div class="publications">
        {% bibliography -q @*[key=LiuWaCuNa24]* %}
  </div>
</div>

### Foundations of distributional robustness

Our vision is to build robust and reliable learning procedures that make decisions with a guaranteed level of performance over its inputs. My Ph.D. thesis built the statistical<d-cite key="DuchiGlNa21,DuchiNa21"></d-cite>, and computational<d-cite key="NamkoongDu16"></d-cite> foundations of robust machine learning. As robustness is a central topic spanning across multiple fields, my subsequent works have developed robust algorithms for deep learning <d-cite key="SinhaNaVoDu18,VolpiNaSeDuMuSa18"></d-cite>, causal inference<d-cite key="YadlowskyNaBaDuTi22,JeongNa22"></d-cite>, reinforcement learning<d-cite key="NamkoongKeYaBr20"></d-cite>, and safety evaluation of autonomous vehicles<d-cite key="OKellySiNaDuTe18"></d-cite>. These works have led to new approaches toward fairness by characterizing fundamental connections between robustness and fairness<d-cite key="HashimotoSrNaLi18,DuchiHaNa22,LiNaXi24"></d-cite>. Watch my talk (@ Google Brain, 2021) and the following two representative papers to learn more.

<div class="img l-body">
  <div class="text-center">
  {% include video.liquid path="https://www.youtube.com/embed/DRlF5sdCkKY?si=d1t8-_HYudo-K1qY" class="img-fluid rounded z-depth-1"%}
  </div>
  <div class="publications">
      {% bibliography -q @*[key=DuchiNa21]* %}
  </div>
  <div class="publications">
      {% bibliography -q @*[key=DuchiHaNa22]* %}
  </div>
</div>

---
## AI-driven decisions

Decision-making problems in OR/MS concerns the optimal allocation of scarce resources. We build scalable computational frameworks for learning operational decisions by leveraging i) auto-differentiable simulators, and ii) empirically rigorous benchmarking. Our goal is to build a algorithmic development paradigm based on computation rather than theoretical approximations. 



### Adaptive experimentation at scale

Experimentation is the foundation of scientific decision-making. Adaptive methods can significantly improve data efficiency, but 
standard algorithms are primarily designed to satisfy good upper bounds on their performance (regret bounds) and do not model important operational constraints and are challenging to implement due to infrastructural/organizational difficulties. Instead of the typical theory-driven paradigm, we leverage computational tools and empirical benchmarking for algorithm development. Our proposed framework models practical instances in online platforms and social networks involving a handful of reallocation epochs in which outcomes are measured in batches. Watch my SNAPP seminar and read the following papers to learn more.

<div class="img l-body">
<div class="text-center">
  {% include video.liquid path="https://www.youtube.com/embed/CLzRcOw9eyk?si=8v_F9ODlpHC588Ei" class="img-fluid rounded z-depth-1"%}
</div>
  <div class="publications">
      {% bibliography -q @*[key=CheNa23]* %}
  </div>

  Starting with my one-year stint at Meta's adaptive
  experimentation team, I've been pondering on how
  bandit algorithms are largely designed by
  theoreticians to achieve good regret bounds and are
  rarely used in practice due to the difficulty of
  implementation and poor empirical performance. In
  this work, we focus on underpowered, short-horizon,
  and large-batch problems that typically arise in
  practice. 
  
  We use large batch normal approximations
  to derive an MDP formulation for deriving the
  optimal adaptive design. Our optimization formulation allows the
  use of standard computational tools in ML for designing adaptive
  algorithms.
  Our approach significantly improves statistical power over standard 
  methods, even when compared to Bayesian bandit algorithms 
  (e.g., Thompson sampling) that require full distributional knowledge 
  of individual rewards. Overall, we expand the scope of 
  adaptive experimentation to settings that are difficult 
  for standard methods, involving limited adaptivity, 
  low signal-to-noise ratio, and unknown reward distributions.

    <p>{% include figure.liquid loading="eager" path="/assets/img/arm-diagram.png" title="AES" class="img-fluid rounded z-depth-1" %} </p>
  <div class="caption">
    To model short-horizon problems, we must design algorithms that optimize instance-specific constants, 
    instead of relying on regret bounds that only hold in the large horizon limit.
    We develop a computation-driven adaptive experimentation framework that can flexibly handle batching. Our main observation is that normal approximations, which are universal in statistical inference, can also guide the design of adaptive algorithms. Instead of the typical theory-driven paradigm, we use PyTorch and empirical benchmarking for algorithm development.     
    </div>

</div>

### Online decision-making with scalable ML tools

Real-world decision-making requires grappling with a perpetual lack of data as environments
change. Intelligent agents must comprehend uncertainty and actively gather information to resolve
it. Leveraging scalable computational tools in ML---neural networks, SGD based on auto-differentiation, 
validation losses---to balance exploration and exploitation is a longstanding challenge. 

Consider cold-start problem on recommender systems, where an online platform must learn high-quality items
among a large catalogue. The standard ML approach uses item features to predict engagement---the de facto 
industry standard. Instead, we propose a *sequence modeling approach* where we predict
the *sequence of engagements* observed for the item using an autoregressive model (e.g., transformer). 

- We learn active exploration algorithms like Thompson sampling on vast historical data 
- We directly relate autoregressive loss to online decision-making performance: 
training good autoregressive sequence models allows you to solve complex online decision-making problems! 

<div class="img l-body">
    <p>{% include figure.liquid loading="eager" path="/assets/img/imputation.png" title="imputation" class="img-fluid rounded z-depth-1" %} </p>
  <div class="caption">
    <strong> Main insight</strong>: Recommending items based on autoregressively imputed observations implements 
    Thompson sampling, a prominent instantiation of the optimism under uncertainty principle. 
  </div>
  <div class="publications">
      {% bibliography -q @*[key=ZhangCaNaRu24]* %}
  </div>
</div>


### AI-based service systems

Recent advances in AI present significant opportunities to rethink the design of service 
systems with AI at the forefront.
Endogeneity presents a key intellectual challenge to managing congestion. 
Prediction is never the goal, but the link between 
predictive performance and downstream decision-making performance is not straightforward: 
prioritizing a job based on predictions impacts the delay of other jobs!

<div class="img l-body">
    <p>{% include figure.liquid loading="eager" path="/assets/img/queue-ml.png" title="queue-ml" class="img-fluid rounded z-depth-1" %} </p>
  <div class="caption">
    Example of a service system based on state-of-the-art AI models: large-scale content moderation systems in online platforms.
    AI models help human reviewers prioritize toward violating contents most likely to go viral.
  </div>
</div>

We crystallize how classical tools from queueing theory provide managerial 
insights into the design and operation of AI-based service systems:
- simple policies with heavy traffic optimality guarantees
- novel model selection procedure for prediction models with 
downstream queueing performance as a central concern
- AI-based triage by trading off predictive performance, hiring costs, and congestion costs

<div class="img l-body">
  <div class="publications">
      {% bibliography -q @*[key=LeeNaZe24]* %}
  </div>
</div>


<!-- 
### Auto-differentiable discrete event simulation

Typical operational decision-making problems (e.g., queueing, inventory management) are often distinguished by two characteristics: i) the dynamics of the system are relatively simple and ii) action space is combinatorially large. Despite their flexibility, black-box reinforcement learning methods are unreliable and require prohibitive amounts of data. We develop auto-differentiable simulators that can directly optimize policies at scale and showcase the promise of this algorithmic development paradigm on the benchmark problems we develop.

E. Che, J. Dong, and H. Namkoong. Auto-differentiable discrete event simulation for queuing network control. Working paper, 2024.
-->

---
## Robust off-policy learning

Off-policy methods can learn sequential decision policies using the rich reservoir of previously collected (non-experimental / observational) data. Although engineered approaches to off-policy learning have seen much progress—based on deep learning and simulation optimization—they often produce unreliable policies due to their heuristic nature. For these methods to bear fruit and transform applications where experimentation is costly, it is important to avoid deploying policies whose safety cannot be verified. 

Engineering progress is predicated on rigorous empirical evaluation. While prediction models can be easily evaluated on previously collected data, assessing decision-making performance requires counterfactual reasoning. Traditional modeling assumptions that allow adjusting prediction models to learn counterfactuals rarely hold in practice. The growth in the nominal volume of data is no panacea: observed data typically only covers a portion of the state-action space, posing challenges in counterfactual learning. Concomitant to unseen data sparsity, shifts in the data distribution are common. Observed decisions depend on unrecorded confounders, and learning good policies requires causal reasoning. Marginalized demographic groups are severely underrepresented; for example, among 10000+ cancer clinical trials the National Cancer Institute funds, fewer than 5% of participants were non-white. 

Our existing statistical language falls woefully short as it relies on unverifiable (and often false) assumptions, and we lack diagnostics that can identify failure modes. We develop data analysis tools that can 
- guarantee robust scientific findings and perhaps more importantly
- fail in expected ways by highlighting the fundamental epistemic uncertainty in the data.


<div class="img l-body">
<div class="text-center">
    {% include video.liquid path="https://www.youtube.com/embed/FqdH75RazNQ?si=yr19pw3ygvcDQtHu" class="img-fluid rounded z-depth-1"%}
</div>
</div>

### External validity

While large-scale randomized studies offer a “gold standard” for internal validity, their external validity can be called into question over spatiotemporal changes in the population, particularly when the treatment effect is heterogeneous across the population. The ACCORD and SPRINT trials offer a prominent example: they studied the effect of treatments to lower blood pressure on cardiovascular disease, but reached opposite conclusions despite exceptionally large sample sizes (5-10K). The mechanism behind the difference could not be explained by experts even ex-post. 

We develop new methods to assess and improve the external validity of RCTs. In particular, we develop sensitivity analysis frameworks that allows researchers to assess the extent to which existing experiments inform the treatment effect in a new target site and quantify an expected range of the policy effect for each new site. 

<div class="img l-body">
<div class="publications">
    {% bibliography -q @*[key=JeongNa22]* %}
</div>
</div>

### Unobserved confounding

Off-policy methods can learn decision policies using the rich reservoir of previously collected (observational) data. A universal assumption that enable counterfactual reasoning requires observed decisions do not depend on any unrecorded confounders that simultaneously affect future states/rewards. This condition is frequently violated in medicine, e-commerce, and public policy, e.g., emergency department patients often do not have an existing record in the hospital’s electronic health system, leaving essential patient-specific information unobserved in subsequent counterfactual analysis. In the presence of unobserved confounding, even with large samples, it is impossible to precisely estimate the performance of the evaluation policy. To guard against spurious counterfactual evaluations, we propose a worst-case approach where we first posit a realistic notion of bounded unobserved confounding that limits the influence of unrecorded variables on observed decisions and develop corresponding worst-case bounds on the reward.


<div class="img l-body">
  <div class="publications">
      {% bibliography -q @*[key=YadlowskyNaBaDuTi22]* %}
  </div>
  <div class="d-flex justify-content-center">
      <div class="text-center">
          {% include figure.liquid loading="eager" path="/assets/img/confounding.png" title="confounding" class="img-fluid rounded z-depth-1" %}
      </div>
  </div>
</div>

### Unforeseen data sparsity

A central challenge in observational analysis is that the effective sample size is difficult to gauge. Even when a nominally large dataset is collected, the effective sample size may be prohibitively small when there is little overlap between trajectories seen under the data-generating and proposed policies. Data sparsity becomes more pronounced in modern problems that involve high-dimensional covariates representations; causal identification becomes difficult on parts of the covariate space with limited effective sample size. Existing observational methods are only valid in the large sample limit and silently fail in practical instances, where the effective sample size is limited. 

We propose a new inferential framework that provides always-valid uncertainty quantification. Unlike asymptotic methods, we quantify instance-specific uncertainty that accurately scales with the level of overlap Our proposed counterfactual evaluation paradigm i) provides always-valid uncertainty estimates, spurring engineering progress through rigorous empirical evaluations, and ii) guides the optimal design of experiments based on previously collected (observational) data.

