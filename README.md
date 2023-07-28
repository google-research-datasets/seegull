# SeeGULL: A Stereotype Benchmark with Broad Geo-Cultural Coverage Leveraging Generative Models

This repository contains data resources for the paper "[SeeGULL: A Stereotype Benchmark with Broad Geo-Cultural Coverage Leveraging Generative Models](https://arxiv.org/abs/2305.11840)". This dataset contains stereotype examples that may be offensive. 

## Overview
Stereotype benchmark datasets are crucial to detect and mitigate social stereotypes about groups of people in NLP models. However, existing datasets are limited in size and coverage, and are largely restricted to stereotypes prevalent in the Western society. This is especially problematic as language technologies gain hold across the globe. To address this gap, we present SeeGULL, a broad-coverage stereotype dataset, built by utilizing generative capabilities of large language models such as PaLM, and GPT-3, and leveraging a globally diverse rater pool to validate the prevalence of those stereotypes in society. SeeGULL is in English, and contains stereotypes about identity groups spanning 178 countries across 8 different geo-political regions across 6 continents, as well as state-level identities within the US and India. We also include fine-grained offensiveness scores for different stereotypes and demonstrate their global disparities. Furthermore, we include comparative annotations about the same groups by annotators living in the region vs. those that are based in North America, and demonstrate that within-region stereotypes about groups differ from those prevalent in North America.

## Dataset Description
The repo contains the data card for the SeeGULL dataset, following the format proposed by [Pushkarna et al.](https://arxiv.org/abs/2204.01075). The data card includes details of the dataset such as intended usage, field names and meanings, annotator recruitment and payments. The `dataset` folder contains the following 3 files:
- `stereotypes_global.csv`: Nationality based stereotypes
- `stereotypes_indian_states.csv`: Stereotypes about Indian States
- `stereotypes_us_states.csv`: Stereotypes about US States

For nationality based stereotypes (`stereotypes_global.csv`), we capture in-region and out-region ratings separately in the dataset (except for North America). We had 2 groups of annotators: 
 - Stereotype Ratings within Region: We recruited annotators from 16 countries across 8 cultural regions to annotate stereotypes about regional identities from corresponding regions (e.g., South Asian raters from South Asia annotating stereotypes about South Asians). 
- Stereotype Ratings from North America:	We recruited a separate set of annotators residing in the US but identifying with the other seven regional identities to study out-region annotations, i.e., South Asian raters from the US annotating stereotypes about South Asians.

Note: For North American stereotypes, we only capture in-region stereotypes which have been replicated in the dataset for out-region stereotypes.

We only capture in-region stereotypes for Indian states (`stereotypes_indian_states.csv`) and the US states (`stereotypes_us_states.csv`).

All three files contain the mean offensiveness scores. Higher the score, more offensive the stereotype. 

## Changes in SeeGULL V2

The `stereotypes_global.csv` dataset has been updated. We made the following changes:

1. Removed noisy attributes
2. Converted all attributes to lowercase
3. Lemmatization mapped attributes to a single root word/phrase
4. Removed stop words and mapped attributes to a single word/phrase
5. Removed punctuations ('-', '_') from attributes
6. Corrected typos in some identities

## Citation

```
{
@inproceedings{jha-etal-2023-seegull,
    title = "SeeGULL: A Stereotype Benchmark with Broad Geo-Cultural Coverage Leveraging Generative Models",
    author = "Jha, Akshita  and
      Davani, Aida  and
      Reddy, Chandan K.  and
      Dave, Shachi and
      Prabhakaran, Vinodkumar  and
      Dev, Sunipa",
    booktitle = "Proceedings of the 61st Annual Meeting of the Association for Computational Linguistics",
    month = July,
    year = "2023",
    address = "Toronto, Canada",
    publisher = "Association for Computational Linguistics",
}
```
