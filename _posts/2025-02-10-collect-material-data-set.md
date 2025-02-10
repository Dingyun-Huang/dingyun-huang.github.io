---
layout: post
title: Thoughts on Text-mining Material Datasets for Modelling and Generation
date: 2025-02-10
categories: [Thoughts]
tags: [ChemDataExtractor, Machine Learning, Materials Science, Data Mining, AI]
og_image: "/assets/img/thoughts_text_mining/headline.jpg"
description: Thoughts on Text-mining Material Datasets for Modelling and Generation
---

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/thoughts_text_mining/headline.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
   Generated with DALL•E.
</div>

## Problem Definition

Material property modeling involves training machine learning (ML) models to predict material properties based on structural information. This approach has applications in various domains, from predicting mechanical strength to estimating electronic or optical behavior. However, effective ML models require well-structured and reliable datasets, making data mining a crucial step in the workflow.

## Key Considerations When Mining Data

### 1. Clearly Define the Objective

Before collecting data, it is essential to clarify what property is being modeled. The objective will determine what kind of data is required. For example:

- **Chemical-level properties vs. Device-level properties**: Some properties of the same dimension and similar names involve very different underlying phyics. For instance, an OLED’s electroluminescence wavelength versus its light-emitting molecule's dilute solution photoluminescence wavelength.

The distinction between these levels affects how data should be sourced and interpreted.

### 2. Are the Features Sufficient?

A fundamental question in ML modeling is whether the chosen features fully determine the target property. If not, missing factors could compromise model performance. It helps to think constructively: _What are the most influential factors affecting the property?_ Some commonly overlooked factors include:

- **Solvents**: Some material properties depend on the solvent environment, which might not be captured in the dataset.
- **States of matter**: A material’s phase (solid, liquid, gas, film) can significantly affect its properties.
- **Temperature and pressure**: External conditions influence many material behaviors but are often omitted in large-scale datasets.

### 3. Data Availability and Scalability

Not all necessary information is available in a large-scale, in text, or in collectable format. Some challenges include:

- **Chirality and stereochemistry**: Large molecular structures often require 3D information, which cannot be inferred from common 2D chemical structure representations.
- **Crystalline materials**: Extracting structural information from diagrams or text descriptions can be difficult, limiting automation.

If critical data points are missing, consider alternative sources, hybrid approaches, or additional experimental validation.

### 4. Trustworthiness of Data Sources

The reliability of mined data is crucial. Some experimental results in literature may be cherry-picked or irreproducible, leading to inconsistencies. Key factors in assessing dataset trustworthiness include:

- **Reproducibility**: Prioritize materials or properties where results are consistent across multiple studies.
- **Domain expertise**: Understanding the field helps in selecting credible literature and filtering out unreliable data.

## Conclusion

Careful data mining is essential for developing accurate ML models in material science. Defining the objective, ensuring the completeness of features, evaluating data availability, and assessing source reliability all contribute to building a robust dataset. Integrating domain knowledge with computational techniques can significantly improve model performance and scientific discovery.
