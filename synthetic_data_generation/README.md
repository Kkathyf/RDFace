# Synthetic Data Generation

This folder contains tools for generating class-specific synthetic facial images using the **DreamBooth** method built on top of a pre-trained diffusion model.

## Contents

| File | Description |
|------|-------------|
| `dreamBooth.ipynb` | Finetunes the model `SG161222/Realistic_Vision_V5.1_noVAE` using DreamBooth with 3–5 example images per class, then generates identity-preserving synthetic facial images. |

## DreamBooth + Diffusers

This notebook uses the Hugging Face [`diffusers`](https://github.com/huggingface/diffusers) library to:

- Load the pre-trained model: [`SG161222/Realistic_Vision_V5.1_noVAE`](https://huggingface.co/SG161222/Realistic_Vision_V5.1_noVAE)
- Finetune it using DreamBooth on a small number (3–5) of identity- or phenotype-specific facial images.
- Generate multiple synthetic images per class using prompt-based sampling.

> **Local Setup Tip**:  
> Clone the `diffusers` repository into this same directory before running the notebook:
>
> ```bash
> git clone https://github.com/huggingface/diffusers.git
> ```
>
> This allows for local development, customization, and ensures compatibility with DreamBooth training scripts.

> Ensure the following dependencies are installed:
> - `diffusers` (editable install if using local copy)
> - `transformers`
> - `accelerate`
> - `torch`
> - `xformers` (optional, but recommended for memory-efficient training)


## FastGAN (Not Included)

Synthetic images using FastGAN were generated externally using the official repository under GPL-3.0 license:

[https://github.com/odegeasslbc/FastGAN-pytorch](https://github.com/odegeasslbc/FastGAN-pytorch)

We used their unmodified `train.py` and `eval.py` scripts on class-specific image folders. For reproducibility, please follow their documentation.

## Output

- DreamBooth-generated images are saved in per-class directories, while FastGAN outputs are organized by checkpoint, enabling structured use in downstream tasks.
- These outputs are used in:
  - Phenotype report generation (`llm_report_generation/`)
  - Classification and few-shot evaluation (`supervised_classification/`, `few_shot_learning/`)

---

*Model used: [`SG161222/Realistic_Vision_V5.1_noVAE`](https://huggingface.co/SG161222/Realistic_Vision_V5.1_noVAE)*  
*Ensure proper image resolution and preprocessing to match input expectations. The output images resolution should be 512 $\times$ 512.*
