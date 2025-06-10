# HCV Genotyping: Advances in Encoding Techniques and Feature Integration

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

**Authors:**  
Ahmed M. Fahmy, Muhammed S. Hammad, Walid I. Al-atabany, Mai S. Mabrouk

---

## Overview

This repository contains all source code, data processing pipelines, and supplementary scripts for the study:

**Optimizing HCV Genotyping: Advances in Encoding Techniques and Feature Integration**

Our work explores advanced encoding techniques and the integration of supplementary genomic features to boost machine learning performance in Hepatitis C Virus (HCV) genotyping. We systematically benchmark multiple sequence encodings (FCGR, k-mer, One-hot, Label), combine them with biologically relevant features (GC content, GC skew), and apply class balancing using SMOTE across various ML models (XGBoost, Random Forest, MLP, KNN).

---

## Table of Contents

- [Background](#background)
- [Pipeline Overview](#pipeline-overview)
- [Installation](#installation)
- [Usage](#usage)
- [Results](#results)
- [Data Availability](#data-availability)
- [Citing](#citing)
- [Acknowledgements](#acknowledgements)
- [License](#license)

---

## Background

Hepatitis C Virus (HCV) genotyping is essential for guiding clinical therapies and epidemiological surveillance. Traditional lab methods face limitations due to high genetic variability, contamination, and class imbalance in datasets.

This repository provides a reproducible pipeline to:
- Encode genomic sequences using advanced representations (k-mer, FCGR, etc.).
- Integrate supplementary sequence features (GC content, GC skew).
- Apply oversampling (SMOTE) to handle class imbalance.
- Evaluate multiple ML classifiers for HCV genotype prediction.

---

## Pipeline Overview

1. **Data Acquisition**  
   - Download sequences from [Los Alamos HCV Sequence Database](https://hcv.lanl.gov/content/sequence/HCV/ToolsOutline.html).

2. **Preprocessing**  
   - Split into complete/partial sequences and apply quality control.

3. **Encoding Methods**  
   - k-mer encoding (k=5 recommended)
   - Frequency Chaos Game Representation (FCGR)
   - One-hot encoding
   - Label encoding

4. **Feature Engineering**  
   - Extract GC content and GC skew for each sequence.

5. **Class Balancing**  
   - Use [SMOTE](https://imbalanced-learn.org/stable/references/generated/imblearn.over_sampling.SMOTE.html) to balance classes.

6. **Model Training**  
   - Evaluate XGBoost, Random Forest, MLP, KNN (and optionally CNN) with 5-fold stratified CV.

7. **Evaluation**  
   - Report accuracy, precision, recall, F1-score for all genotypes.
   - Analyze feature importance.

---

## Installation

1. **Clone the repo:**
   ```bash
   git clone https://github.com/AM5820/HCV-genotyping.git
   cd HCV-genotyping
