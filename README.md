# Advancing HCC Prognosis: A Comprehensive Framework for Improved Patient Outcomes

This repository contains a multi-stage pipeline for the analysis of histopathological images of hepatoma. The pipeline includes stain color normalization, nuclei mask segmentation, feature extraction, and prognosis prediction.

# Hepatoma Analysis Pipeline

![image](https://github.com/Haricharan0311/Hepatoma-Staging-Project/assets/49089160/6c2a176d-49e5-4100-ae73-f70bd834ccd2)

[HCC_Poster.pdf](https://github.com/user-attachments/files/16040129/HCC_G1_16_Poster_cropped.pdf)

## Table of Contents

- [Overview](#overview)
- [Stage I: Stain Colour Normalisation and Segmentation](#stage-i-stain-colour-normalisation-and-segmentation)
- [Stage II: Feature Extraction and Analysis](#stage-ii-feature-extraction-and-analysis)
- [Requirements](#requirements)


## Overview

Hepatocellular Carcinoma (HCC) is a primary cancer that originates in liver cells, specifically in hepatocytes. It is the most common type of liver cancer and represents a significant global health concern. With the advent of Machine Learning and imaging, staging has become an easy task and neural networks do a decent job. The research entails, quantifying certain biomarkers and features in the hope of making the process more "explainable". Quantifying said markers enables us to tweak the pipeline and staging systems for different body compositions and also helps us establish baseline scores for different markers helping us understand the leading causes of a particular variant of cancer.

The pipeline consists of two main stages:
1. **Stain Colour Normalisation and Nuclei Mask Segmentation**: This stage normalizes the color of histopathological images and segments the nuclei.
2. **Feature Extraction and Analysis**: This stage extracts features from the segmented nuclei masks and predicts prognosis based on these features.

## Stage I: Stain Colour Normalisation and Segmentation

The `Hepatoma_Pipeline.ipynb` notebook performs stain color normalization on the given histopathological images and segments the nuclei masks. This notebook generates a Gradio link that hosts an interface for dragging and dropping images to get the intermediate outputs.

## Stage II: Feature Extraction and Analysis

### Cell Profiler

Feed the nuclei masks generated from the given images to Cell Profiler, an open-source software, to detect the primary objects within a pixel range of 5px to 40px. 

### Cell Profiler Analyst

Pass the obtained database file to Cell Profiler Analyst, which will produce an Excel sheet containing suitable features extracted for each nucleus identified from all the images.

### Scripts

1. `Hepatoma_Generate_CSV.py`: Aggregates all the features and creates a condensed table with image names and related features.
2. `Hepatoma_Prognosis.py`: Runs the final prediction script based on the generated feature table.

## Requirements

- Python 3.x
- Gradio
- Jupyter Notebook
- Cell Profiler
- Cell Profiler Analyst


