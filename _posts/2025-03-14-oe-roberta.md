---
layout: post
title: "OE-RoBERTa: Cost-Efficient Pretraining of Language Models for Optoelectronics Applications"
date: 2025-03-14
categories: [Paper Summary]
tags: [ChemDataExtractor, Language Models, Materials Science, Data Mining]
description: Paper summary of the paper *Cost-Efficient Pretraining of Language Models for Optoelectronics Applications*
og_image: "/assets/img/oe-roberta/DAPT_schematics.png"
---

Paper Link: [https://doi.org/10.1021/acs.jcim.4c02029](https://doi.org/10.1021/acs.jcim.4c02029)

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/oe-roberta/oebert-toc.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


## TL;DR

Models at [https://huggingface.co/collections/CambridgeMolecularEngineering/](https://huggingface.co/collections/CambridgeMolecularEngineering/).
- **Development of OE-RoBERTa, OE-BERT, and OE-ALBERT:** Transformer-based language models optimized for optoelectronics research, fine-tuned for text classification, question answering, and text embedding.
- **Cost-Efficient Domain Adaptive Pretraining (DAPT):** A method reducing computational expenses by over 80% while maintaining performance.
- **Interesting Findings:** For optoelectronics QA, OE-RoBERTa is much better than BERT under the same amount of DAPT. Possible reasons includes,
  - RoBERTa is cased and the byte-pair encoding tokenizer has a much larger vocabulary.
  - RoBERTa has undergone longer general English pre-training, which may be transferrable to scientific literature.

## Introduction

The field of optoelectronics is rapidly expanding, producing vast amounts of research literature that can be challenging to process and analyze efficiently. Language models have demonstrated their potential in various scientific disciplines, including materials science and chemistry, making them invaluable for text mining, data extraction, and knowledge discovery. In this study, we introduce OE-RoBERTa, along with OE-BERT and OE-ALBERT, as domain-specific language models for optoelectronics. These models outperform their general English counterparts while significantly reducing computational costs compared to conventional pre-training through domain-adaptive pretraining (DAPT).

## Key Contributions

- **Development of OE-RoBERTa, OE-BERT, and OE-ALBERT:** Transformer-based language models optimized for optoelectronics research.
- **Cost-Efficient Domain Adaptive Pretraining (DAPT):** A method reducing computational expenses by over 80% while maintaining performance.
- **Performance Evaluation:** Models tested on abstract classification, question-answering (QA), and text retrieval tasks.

## Why Optoelectronics Needs Specialized Language Models
<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/oe-roberta/intro-illustration.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
   Figure 1: Applications of BERT-like models in optoelectronics research
</div>

General language models struggle with domain-specific terminology, complex sentence structures, and highly technical knowledge found in optoelectronics research. The introduction of OE-RoBERTa addresses these limitations, enabling efficient literature mining, factual question answering, and document classification in optoelectronics.


The optoelectronics-adapted models were developed using a three-step process:
1. **Domain Adaptive Pretraining (DAPT):** Pretraining on a 5.7GB optoelectronics-specific corpus.
2. **Fine-Tuning on Downstream Tasks:** Abstract classification, QA, and text embedding.
3. **Evaluation and Benchmarking:** Comparison against general-purpose models and OpticalBERT.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/oe-roberta/DAPT_schematics.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
   Figure 2: Model training pipeline for our "optoelectronics-aware" language models.
</div>

## Performance Highlights

### Question Answering

The models were tested on the SQuAD v1.1 dataset and a domain-specific dataset, TADF-numeric. OE-RoBERTa achieved higher accuracy than larger general-purpose models like RoBERTa-large, demonstrating its effectiveness in optoelectronics-related QA tasks. We saved seven checkpoints during the DAPT of OE-RoBERTa and OE-BERT, and see how their QA performance evolves with DAPT. Interestingly, their learning curves are almost parallel, but RoBERTa started with a much better score, which implies that "RoBERTa + DAPT" may be much more energy efficient and environment friendly than training from BERT or from scratch.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/oe-roberta/em_f1_progress.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
   QA performance's evolution against the amount of DAPT.
</div>

## Models and Datasets

For access to the models and datasets, visit the Hugging Face repository: [https://huggingface.co/collections/CambridgeMolecularEngineering/](https://huggingface.co/collections/CambridgeMolecularEngineering/).

