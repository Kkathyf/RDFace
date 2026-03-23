# LLM Report Generation (Qwen 2.5-VL)

This folder contains Jupyter notebooks for generating and evaluating phenotype reports from facial image data using the **Qwen 2.5-VL** large multimodal language model. Reports are used to qualitatively assess the realism and diversity of both real and synthetic facial images.

## Contents

| Notebook | Description |
|----------|-------------|
| `gen_raw_report.ipynb` | Generates phenotype descriptions from real facial images using Qwen 2.5-VL. |
| `gen_dreambooth_report.ipynb` | Generates phenotype descriptions for DreamBooth-generated synthetic images. |
| `gen_fastgan_report.ipynb` | Generates phenotype descriptions for FastGAN-generated synthetic images. |
| `evaluate_report.ipynb` | Compares generated reports across methods and optionally evaluates coherence, phenotype consistency, or similarity to real descriptions. |

## Model Info

- **Model Used**: [Qwen 2.5-VL](https://huggingface.co/Qwen/Qwen-VL)
- **Modalities**: Vision + Language
- **Purpose**: Generate free-text phenotype reports directly from input facial images or embeddings.

## Workflow

1. **Data Input**: Load preprocessed facial images or metadata.
2. **LLM Generation**: Use Qwen 2.5-VL to produce phenotype summaries (e.g., facial features, dysmorphology, age/gender estimates).
3. **Comparison**: Evaluate and compare the quality of reports between real and synthetic images.

## Example Use Cases

- Assess whether synthetic images preserve disease-relevant facial traits.
- Analyze phenotype consistency across augmentation methods.
- Generate narrative descriptions for clinical reviewers or dataset documentation.

## Requirements

- Python 3.8+
- `transformers`, `torch`, `pandas`, `numpy`, `matplotlib`
- Access to a Qwen 2.5-VL inference API or model checkpoint
- Preprocessed input data (facial crops or embeddings)

## Notes

- Reports may be saved as `.txt`, `.json`, or inline DataFrame columns.
- `evaluate_report.ipynb` may use embedding-based similarity, GPT/LLM re-ranking, or human-annotated scores.

---

*For more information on Qwen-VL, visit the [official repository](https://github.com/QwenLM/Qwen-VL).*
