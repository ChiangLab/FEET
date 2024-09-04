# FEET: A Framework for Evaluating Embedding Techniques

## Introduction

This repository introduces **FEET (Framework for Evaluating Embedding Techniques)**, a standardized protocol designed to guide the development and benchmarking of foundation models. FEET focuses on the evaluation of embeddings across three distinct use cases:
1. **Frozen Embeddings**
2. **Few-Shot Embeddings**
3. **Fully Fine-Tuned Embeddings**

The goal is to provide a comprehensive and structured evaluation of embedding techniques that ensures consistent and thorough benchmarking for foundation models. This repository contains the code and tools required to replicate our benchmarking approach.

## Use Cases
We define and evaluate foundation models based on three primary embedding scenarios:
1. **Frozen Embeddings**: Pre-trained embeddings that are not updated during the model training process.
2. **Few-Shot Embeddings**: Evaluates the model's ability to learn from a limited number of labeled examples.
3. **Fully Fine-Tuned Embeddings**: Embeddings that are updated through a full fine-tuning process on task-specific data.

Each use case is benchmarked with performance metrics to assess how well the models adapt to different levels of customization.

## Dataset
The main dataset used for evaluation is the **MIMIC-IV dataset**, specifically focusing on the prediction of antibiotic prescriptions. The dataset contains medical records and features from patients in critical care settings. To access the MIMIC-IV dataset, you must complete the necessary approval process, as it contains sensitive medical data. Preprocessing scripts are contained in `preprocessing/` to extract antibiotics cohort.

## Code and Replication

You can find the code to replicate the results in this study [here](https://anonymous.4open.science/r/embeddings_eval-846B/README.md). The repository includes:
- Scripts for data preprocessing.
- Benchmarking scripts for evaluating frozen, few-shot, and fully fine-tuned embeddings.
- FEET Table generation scripts to present the results clearly.

## Results and Benchmarking

The results of our evaluation are displayed in **FEET Tables**, where we compare different models across the embedding scenarios. The tables report AUROC and AUPRC scores across different antibiotics tasks. Furthermore, we introduce **$\delta$ FEET Tables** to highlight the relative performance improvements or drop-offs in comparison to the frozen embeddings.

### Example of FEET Table:
| Models          | Frozen  | Few-shot (2) | Fine-tuned  |
|-----------------|---------|--------------|-------------|
| BioClinicalBERT | 74.99   | 56.73        | 67.59       |
| MedBERT         | 74.22   | 55.49        | 69.35       |
| SciBERT         | 73.98   | 52.77        | 68.31       |

### Example of $\delta$ FEET Table:
| Models          | Frozen  | Few-shot (2) | Fine-tuned  |
|-----------------|---------|--------------|-------------|
| BioClinicalBERT | ------  | -21.11%      | -7.40%      |
| MedBERT         | ------  | -19.94%      | -4.87%      |
| SciBERT         | ------  | -19.80%      | -5.67%      |

## Conclusion

The FEET framework offers a principled and comprehensive way to evaluate foundation models across different embedding scenarios. By reporting on Frozen, Few-shot, and Fully Fine-tuned embeddings, we provide a deeper understanding of model performance, adaptability, and limitations.

We encourage researchers and practitioners to use FEET as a standard protocol for evaluating foundation models in their studies.
