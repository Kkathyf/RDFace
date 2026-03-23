# RDFace Toolkit

This repository provides a modular framework for facial image analysis in the context of rare disease diagnosis, specifically tailored for use with the **RDFace** dataset. It supports data preprocessing, classification (few-shot and supervised), synthetic image generation, and LLM-based report generation.

---

## Installation

We recommend using a virtual environment (e.g. `conda` or `venv`). Then install the dependencies with:

```bash
pip install -r requirements.txt
```
> Some models (e.g. VGGFace, CLIP, or FastGAN) require external weights or additional dependencies as noted in each module’s README.

---

## Directory Overview

1. `data_processing/`: Scripts and utilities for preparing raw pediatric facial images and analyzing synthetic ones.

2. `supervised_classification/`: Conventional deep learning pipeline for facial phenotype classification.

3. `few_shot_learning/`: Implements few-shot classification methods for identifying phenotypic patterns in settings with limited data.

4. `synthetic_data_generation/`: Generates identity- and phenotype-consistent synthetic facial images to support training in low-data settings.

5. `llm_report_generation/`: Automates generation of clinical or research-style summaries from model outputs using large language models (LLMs).

---

### VGGFace Feature Extractor

We include a modified version of the VGGFace implementation from [ProgramComputer/VGGFace-pytorch](https://github.com/ProgramComputer/VGGFace-pytorch) in folder `models_vggface/`. The modifications include a renamed architecture class and a `FeatureExtractor` wrapper to support embedding extraction for facial similarity analysis.

> **Weights not included:**  
> Please follow the original GitHub instructions to download the pretrained VGGFace weights manually:
> [https://github.com/ProgramComputer/VGGFace-pytorch](https://github.com/ProgramComputer/VGGFace-pytorch)

After downloading, place the weight file (e.g., `vgg_face.pth`) in folder `models_vggface/` and update the path in your loading script.

---
