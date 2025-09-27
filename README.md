## BERT-Guardrail🔗

## Overview
This repository contains code for fine-tuning **[ModernBERT](https://huggingface.co/answerdotai/ModernBERT-base)** as a guardrail on a text classification task(logistics related queries in this case) using Hugging Face Trainers API. I haven't really found a "Huggingface" way to perform k-fold cross validation thus I implemented one my own in this notebook. The **[synthetic dataset][https://github.com/Luis-ramirez-r/modern-bert-fine-tuning]** which I forked is generated using Deepseek-v1 and moderated by Deepseek-r1 model for less biased response. The fine-tuned model performed quite well as a substitute to LLM guardrail with F1 score, 0.96 considered its lightweighted size and less expensive to finetune.

The hf format are then convert to ONNX format for fast inference and universal production portability.


## ⚙️ Setup
Clone the repo and install dependencies:

```bash
git clone https://github.com/deeplyneuralicious/bert-guardrail.git

cd bert-guardrail

uv pip install -r pyproject.toml OR uv sync
```