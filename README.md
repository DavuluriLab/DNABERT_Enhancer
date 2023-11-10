# DNABERT-Enhancer: Harnessing the Power of a Comprehensive ENCODE-Guided Dataset for Enhancer Prediction

## Overview
DNABERT-Enhancer is a cutting-edge computational tool designed for the identification of enhancers – crucial regulatory elements in genomics. This repository hosts the DNABERT-Enhancer model, datasets, and related resources.

## Table of Contents
- [Introduction](#introduction)
- [Abstract](#abstract)
- [Datasets](#datasets)
- [Model](#model)
- [Usage](#usage)
- [Citation](#citation)
- [Contact](#contact)

## Introduction
Enhancers play a pivotal role in gene expression and can be linked to various diseases when they malfunction. Identifying these enhancers is a significant challenge in computational biology due to their variable characteristics and lack of distinct genomic features.

## Abstract
This project presents a comprehensive approach to enhancer prediction by combining 10 public datasets and constructing a feature matrix using ENCODE ChIP-Seq peak regions. Through a series of steps involving Random Forest classifiers and iterative refinement, we've created a high-quality dataset and developed the DNABERT-Enhancer model. This model, fine-tuned on this dataset, showcases an accuracy of 80.92% in enhancer prediction, demonstrating its effectiveness.

## Datasets
The repository includes the combined dataset of enhancer and non-enhancer sequences used for training and testing the DNABERT-Enhancer model.

### Dataset Details:
- **Enhancer Sequences:** 7,779 sequences
- **Non-Enhancer Sequences:** 8,172 sequences
- **Sequence Length:** 200 bp

## Model
DNABERT-Enhancer is built upon DNABERT, a large language model for the human genome, fine-tuned specifically for enhancer prediction.

### Model Highlights:
- **Training Accuracy:** 80.92%
- **Features:** Top ENCODE features
- **Methodology:** Random Forest classifiers and iterative refinement

## Usage
Instructions on how to use the DNABERT-Enhancer model and datasets for enhancer prediction will be provided here.

## Citation
If you use the DNABERT-Enhancer in your research, please cite our paper:

```bib
@article{your_citation_here,
    title={DNABERT-Enhancer: Harnessing the Power of a Comprehensive ENCODE-Guided Dataset for Enhancer Prediction},
    author={Your Author Names},
    journal={Your Journal Name},
    year={Your Publication Year},
    doi={Your DOI},
    url={Your Paper URL}
}

@article{ji2021dnabert,
    author = {Ji, Yanrong and Zhou, Zhihan and Liu, Han and Davuluri, Ramana V},
    title = "{DNABERT: pre-trained Bidirectional Encoder Representations from Transformers model for DNA-language in genome}",
    journal = {Bioinformatics},
    volume = {37},
    number = {15},
    pages = {2112-2120},
    year = {2021},
    month = {02},
    issn = {1367-4803},
    doi = {10.1093/bioinformatics/btab083},
    url = {https://doi.org/10.1093/bioinformatics/btab083},
    eprint = {https://academic.oup.com/bioinformatics/article-pdf/37/15/2112/50578892/btab083.pdf},
}


@misc{zhou2023dnabert2,
      title={DNABERT-2: Efficient Foundation Model and Benchmark For Multi-Species Genome}, 
      author={Zhihan Zhou and Yanrong Ji and Weijian Li and Pratik Dutta and Ramana Davuluri and Han Liu},
      year={2023},
      eprint={2306.15006},
      archivePrefix={arXiv},
      primaryClass={q-bio.GN}
}
