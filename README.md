# SRLRF

**SRLRF** is a noval approach for root cause classification of C compiler optimization defects proposed by author Luohan et al in paper **《SRLRF: Fine-Grained Root Cause Analysis and Prediction for Compiler Optimization Defects》**. In this project, we open source the datasets and source code.

## Benchmark
The entire benchmark is divided equally into five folds, and the fields in each csv file are **text**,**report**,**code**,**category**,**label**.
- **text** represents the original bug rpoert
- **report** represents the bug report after removing the code
- **code** from the bug report out, or from the attachment
- **category** is a string type label (category)
- **label** is a label of type int

Please read the paper for details.

## SRLRF
### Model
- Llama-3.1-8B-Instruct: https://huggingface.co/meta-llama/Llama-3.1-8B-Instruct
- RTA: https://huggingface.co/Colorful/RTA
### Environment
Ubuntu-22.04

Core library：
Pytorch: 2.5.1,
Unsloth 2024.11.7,
Transformers = 4.46.3,
CUDA = 8.9,
CUDA Toolkit = 12.1,

### Equipment
GPU: NVIDIA GeForce RTX 4090
### Source code
Contains five main files.
- **llama3.1-finetuning.ipynb**: fine-tuning training llama3.1.
- **llama3.1-softlabel.ipynb**: evaluates the trained llama3.1 and generates soft labels
- **rta-finetuning.ipynb**: fine-tune training rta
- **rta-softlabel.ipynb**: evaluates trained rta, generates soft labels
- **stacking_ensemble.ipynb**: stacking integrated learning components, essentially training and tuning random forest models.
For detailed training process, please refer to the paper.


