---
layout: post
title: "Machine-Learning Predictions of Photoluminescence in Molecules Exhibiting Thermally Activated Delayed Fluorescence with Implicit Experimental Validation"
date: 2025-03-14
categories: [Paper Summary]
tags: [ChemDataExtractor, Graph Neural Network, Materials Science, Data Mining, Materials Modelling]
description: Paper summary of the paper *Machine-Learning Predictions of Photoluminescence in Molecules Exhibiting Thermally Activated Delayed Fluorescence with Implicit Experimental Validation*
og_image: "/assets/img/tadf_pl/angew-toc.png"
---

Paper Link: [https://doi.org/10.1021/acs.jcim.6c00425](https://doi.org/10.1021/acs.jcim.6c00425)

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/tadf_pl/angew-toc.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

The application of machine learning to materials discovery is often constrained by the availability of large-scale, experimentally verified materials databases. This study presents an automatic, end-to-end framework that bridges this gap by training machine-learning predictors for materials properties on experimental data mined directly from the literature.
### Our key contributions:
- By integrating “chemistry-aware” natural language processing with automated chemical structure resolution, we present an high quality dataset of **643 experimentally measured PL wavelengths**.
- This experimentally grounded data were used to train a **light weight heterogeneous graph neural network**.
- The model achieved less than 0.12 eV error in less than 3 min on a personal laptop, effectively capturing complex structure–property relationships without manual feature engineering.