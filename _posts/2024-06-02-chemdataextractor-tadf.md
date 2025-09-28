---
layout: post
title: Thermally activated delayed fluorescent (TADF) molecules and properties extracted from scientific literature with ChemDataExtractor
date: 2024-06-02
categories: [Paper Summary]
tags: [ChemDataExtractor]
description: Thermally activated delayed fluorescent (TADF) molecules and properties extracted from scientific literature with ChemDataExtractor
og_image: "/assets/img/cde_tadf/pie_bar.png"
---

Paper Link: [https://www.nature.com/articles/s41597-023-02897-3](https://www.nature.com/articles/s41597-023-02897-3)

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/cde_tadf/pie_bar.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
   The composition of the database of TADF materials in a pie and a bar chart.
</div>

## Introduction

The interest in thermally activated delayed fluorescence (TADF) is ever growing due to its potential to improve the efficiency of organic light-emitting diodes (OLEDs). TADF materials can convert non-emissive triplet states into emissive singlet states, allowing for a theoretical internal quantum efficiency (IQE) of 100%. The discovery of new TADF materials could potentially be accelerated by data-driven design-to-device pipelines and machine learning capabilities. However, there is currently no consistently structured database for existing TADF molecules. To fill this gap, the chemistry-aware natural-language-processing toolkit ChemDataExtractor was used to extract data from 2,733 scientific articles, resulting in a database of 25,482 data records with 82% overall precision and a subsidiary database of 5,349 property records represented by simplified molecular-input line-entry system (SMILES) strings.

## Key Improvements

### Abbreviation gives SMILES

As abbreviations are widely used in organic molecule names, IUPAC names can be extracted along with abbreviations giving structural information of the compound. By exploiting this, the database contains ~5k records with SMILES strings extracted.

### Query design saves your computing hours

While simply searching the word TADF from publishers is simple, it return significantly many false positive papers which will waste computing resources during extraction. Defining a more precise query using the API provided by publishers saves you 90% computing hours. In this case, a database on the same order of magnitude was extracted from less than 3k papers as previous work with hundreds of thousand papers.

### Compound Blocking

It is very common that several chemical names appear closely in text. In this work, commonly mentioned compounds (e.g. water, toluene) were blocked automatically to avoid wrong association between properties and compounds. This step boosted the association precision up to above 80%. The blocklist was constructed by text-mining TADF papers automatically for high occurrence chemical names.

## Results

Here is a detail view of the database structure.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/cde_tadf/histograms_abcd.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
   Histograms of the value distributions of the four extracted TADF properties.
</div>

## Conclusion

This research presents a well-structured database for molecular TADF materials and can facilitate data-science driven developments in the field of TADF. New text-mining techniques were developed and implemented, which might be transferrable to other data-mining pipeline in material science.

## Additional Resources

- The data extraction source code can be found at the [GitHub Page](https://github.com/Dingyun-Huang/chemdataextractorTADF).
