# Genomic Language Model for Predicting Enhancers and Their Allele-Specific Activity in the Human Genome

## Overview
DNABERT-Enhancer is a machine learning method based on the genome foundational large language model DNABERT. The fine-tuned model successfully identify enhancer regions in the human genome by focusing on the high-attention regions in the enhancer sequences. Moreover, DNABERT-Enhancer is applied to identify and predict candidate non-coding genomic variants in the enhancer regions which can cause a significant shift in enhancer function as well as disrupt the  TFBSs within. This repository hosts the DNABERT-Enhancer model, datasets, and related resources.

## Table of Contents
- [Introduction](#introduction)
- [Abstract](#abstract)
- [Datasets](#datasets)
  - [Data Statistics](#data-statistics)
  - [Data Structure](#data-structure)
  - [Sample Dataset](#sample-dataset)
- [Model and Usage](#model)
  - [Data Processing](#data-processing)
  - [Usage](#usage)
    - [Download Fine-tuned Model](#download-fine-tuned-model)
    - [Getting Prediction from the Model](#getting-prediction-from-the-model)
    - [Storing the Results in W&B](#storing-the-results-in-wb)
- [Usage](#usage)
- [Citation](#citation)
- [Contact](#contact)

## Introduction
Enhancers coordinate the gene expression in a tissue-specific manner. Computational identification of these non-coding regulatory regions is challenging because of its intricate characteristics like varying lengths, ambiguous boundaries, functioning independent of their orientation and variable distances from associated promoters. Moreover, absence of well-defined genetic or epigenetic signatures that can accurately discriminate enhancers within genomic regions adds another layer of complexity. Enhancer malfunction due to genetic alteration mechanisms cause aberrant gene expression leading to genetic diseases like congenital disorders, cancers, and common complex diseases, collectively termed as enhanceropathies. Identifying disease-associated enhancers and recognizing GWAS-identified risk variants within them opens window for drug target discovery and enhancer-targeting therapies implying the clinical significance. Traditional machine learning methods often struggle to grasp the true context and the nuanced nature of enhancer DNA sequences, leading to uncertain real-world efficacy for enhancer prediction.

## Abstract
Predicting and deciphering the regulatory logic of enhancers is a challenging problem, due to the intricate sequence features and lack of consistent genetic or epigenetic signatures that can accurately discriminate enhancers from other genomic regions. Recent machine-learning based methods have spotlighted the importance of extracting nucleotide composition of enhancers, but models based solely on them fail to learn the sequence context and perform suboptimally. Motivated by advances in genomic language models, we developed a novel enhancer prediction method, called DNABERT-Enhancer, by applying DNABERT pre-trained language model on the human genome. We trained two different models, one on 17,540 enhancers and the other on 36,927 enhancers curated from the ENCODE registry of candidate cis-Regulatory Elements (cCREs). The best fine-tuned model achieved performance of 88.05% accuracy with Matthews correlation coefficient (MCC) of 76% on independent set aside data. Further, we present the analysis of the predicted enhancers for all chromosomes of the human genome by comparing with the enhancer regions reported in publicly available databases. Finally, we applied DNABERT-Enhancer along with other DNABERT fine-tuned models to predict candidate SNPs with allele-specific enhancer and TF binding activity. The genome-wide enhancer annotations and candidate loss-of-function genetic variants predicted by DNABERT-Enhancer provide valuable resources for genome interpretation in functional and clinical genomics studies.

## Datasets
For building the **DNABERT-Enhancer** model, we created enhancer and non-enhancer data, length of 200 bp, using 10 different databases and eliminated potential mislabeled sequences by applying a Random Forest classifier iteratively. 

### Data statistics
In the whole process of preparing unbiased and reliable data (_Fine-tune data_) for DNABERT finetuning task, we prepared 3 datasets namely _dataset 1(DS1)_, _dataset 2(DS2)_ and dataset _3(DS3)_ where DS2 and DS3 are subsets of DS1, created by selecting the true predictions (True positives and True negatives) by the Random Forest models. The statistics of the four datasets are given in below table. ![statistics](Figures/Data_statistics.png)

### Data structure
Each dataset is a feature matrix which represents the intersect between the enhancer/non-enhancer regions with 4000 ENCODE ChIP-seq features, where the values represent the number of overlapped peaks. The rows are the enhancer/non-enhancer elements and columns are the ENCODE ChIP-seq peaks or features. Matrix structure is as shown in the below figure.![image](Figures/Sample_matrix.png)

### Sample dataset
<!--The repository includes the combined dataset of enhancer and non-enhancer sequences used for training and testing the DNABERT-Enhancer model. -->
A sample dataset of 500 enhancers and 500 non-enhancers (1000 entries) from the _Fine-tune data_ is provided in the 'Sample_dataset' folder. The ‘Sample_Fine-tune_data_entries.csv’ has the sampled enhancer and non-enhancer coordinates with sequence and class name. The ‘Sample_DNABERT_input.tsv’ has the hexamers and the label of the corresponding sampled entries. Please refer to below figures for the format of the files.
![image](Figures/Dataset_format.png)
![image](Figures/DNABERT_input.png)

**Note**: The entire dataset will be available upon request.

## Model
DNABERT-Enhancer is built upon [DNABERT](https://github.com/jerryji1993/DNABERT), a large language model for the human genome, fine-tuned specifically for enhancer prediction.

### Data Processing
Explain the data processing steps involved in preparing the dataset for the model.

### Usage
Instructions on how to effectively use the DNABERT-Enhancer model.


#### Download Fine-tuned Model
Instructions on how to download the DNABERT-Enhancer model from Hugging Face.

#### Getting Prediction from the Model
Guidelines on how to use the DNABERT-Enhancer model to make predictions.

#### Storing the Results in W&B
Steps to log and track model predictions using Weights and biases.

### Model Highlights:
- **Test Accuracy:** 80.92%
- **Features:** Top ENCODE features
- **Methodology:** Random Forest classifiers and iterative refinement

## Usage
Instructions on how to use the DNABERT-Enhancer model and datasets for enhancer prediction will be provided here.

## Citation
If you use the DNABERT-Enhancer in your research, please cite our paper:

```bib

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
