# A Lightweight Alignment-Free Framework for Robust Hepatitis C Virus Genotyping Using Cluster-Aware Evaluation

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

**Authors:**  
Ahmed M. Fahmy, Muhammed S. Hammad, Walid I. Al-atabany, Mai S. Mabrouk

---

## Overview

The study presents a lightweight and interpretable machine-learning framework for **Hepatitis C Virus (HCV) genotype/subtype classification** using alignment-free nucleotide-sequence representations.

The framework systematically investigates:

- Four sequence encoding methods:
  - k-mer encoding
  - Frequency Chaos Game Representation (FCGR)
  - One-hot encoding
  - Label encoding
- Different k-mer granularities (`k = 3, 4, 5`)
- Supplementary genomic descriptors:
  - GC content
  - GC skew
- Class-imbalance handling using:
  - SMOTE
  - Random undersampling
- Multiple machine-learning classifiers:
  - XGBoost
  - Random Forest
  - K-Nearest Neighbors (KNN)
  - Multi-Layer Perceptron (MLP)
- CD-HIT-EST cluster-aware train/test splitting to reduce sequence-identity leakage
- Feature-importance analysis
- Per-genotype performance analysis
- Statistical evaluation of SMOTE and GC-based feature integration
- Comparison with an alignment-based NCBI genotyping approach

A major focus of the study is providing a stricter assessment of model generalization. Instead of relying on a conventional random train/test split, nucleotide sequences are first clustered using **CD-HIT-EST at 90% sequence identity**, and entire clusters are assigned to either the training or testing partition.

---

## Background

Hepatitis C Virus is characterized by substantial genetic diversity, making accurate genotype and subtype identification important for viral surveillance and genomic analysis.

Traditional HCV genotyping approaches often rely on laboratory assays or sequence-alignment methods. Computational machine-learning approaches provide an alternative way to characterize genomic sequences, but their evaluation can be affected by several challenges, including:

- High sequence similarity between training and testing samples
- Severe class imbalance
- Variable sequence lengths
- Partial genomic sequences
- High-dimensional nucleotide representations
- Potential information leakage caused by random data splitting

This study addresses these issues using **alignment-free sequence representations**, imbalance-handling techniques, and a **similarity-aware evaluation protocol**.

---

## Key Contributions

The main contributions of this work are:

1. **Cluster-aware HCV genotype evaluation**

   CD-HIT-EST clustering at **90% nucleotide-sequence identity** is used before train/test splitting so that sequences from the same similarity cluster are not distributed across both partitions.

2. **Systematic comparison of four sequence representations**

   - k-mer
   - FCGR
   - One-hot
   - Label encoding

3. **Investigation of class-imbalance strategies**

   The study evaluates both:
   - SMOTE
   - Random undersampling

4. **Evaluation of supplementary genomic descriptors**

   GC content and GC skew are evaluated as biologically interpretable compositional features.

5. **Multiple classifier families**

   The same representations are evaluated using:
   - XGBoost
   - Random Forest
   - KNN
   - MLP

6. **Statistical evaluation**

   A two-way repeated-measures ANOVA is used to investigate the effects of:
   - SMOTE
   - GC-based feature integration
   - Their interaction

7. **Model interpretability**

   Feature-importance analysis identifies influential:
   - 5-mer sequence motifs
   - GC content
   - GC skew

8. **Per-genotype analysis**

   Performance is analyzed separately across the ten HCV genotype/subtype classes.

9. **Comparison with an alignment-based genotyping approach**

   The proposed machine-learning framework is also discussed in comparison with the NCBI BLAST-based genotyping tool.

---

## Dataset

HCV nucleotide sequences were obtained from the:

**Los Alamos Hepatitis C Virus Sequence Database**

https://hcv.lanl.gov/

Ten genotype/subtype classes were included:

| Class |
|---|
| 1a |
| 1b |
| 2a |
| 2b |
| 2c |
| 3a |
| 3b |
| 4 |
| 5 |
| 6 |
