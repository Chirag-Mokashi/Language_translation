# Language Translation with Seq2Seq Transformer

A neural machine translation system built with a Sequence-to-Sequence Transformer model, evaluated using the BLEU metric.

## Overview

This project implements and trains a Transformer-based encoder-decoder model for language translation. The model is trained end-to-end and evaluated with BLEU score, achieving **36.62** on the test set — falling in the "good translation" range.

## Model Architecture

**Sequence-to-Sequence Transformer**

| Component | Detail |
|-----------|--------|
| Architecture | Encoder-Decoder Transformer |
| Attention | Multi-head self-attention + cross-attention |
| Tokenisation | Subword tokeniser |
| Framework | PyTorch / TensorFlow |

## Results

| Metric | Score |
|--------|-------|
| BLEU Score | **36.62** |

### BLEU Score Interpretation

| Range | Quality |
|-------|---------|
| 0–19 | Low quality |
| 20–29 | Acceptable |
| **30–39** | **Good** ← this model |
| 40–49 | Very good |
| 50+ | Excellent |

A BLEU score of 36.62 indicates the model produces translations that align well with reference translations, though there is room for improvement — particularly in long-range dependencies and rare vocabulary.

## Setup

```bash
git clone https://github.com/Chirag-Mokashi/Language_translation
cd Language_translation
pip install -r requirements.txt
```

## Training

```bash
python train.py
```

Hyperparameters (epochs, learning rate, batch size, model dimensions) are configurable in the training script.

## Evaluation

```bash
python evaluate.py
```

Outputs BLEU score on the test set along with sample translations.

## Inference

```python
from model import translate

result = translate("The weather is nice today.")
print(result)
```

## Tech Stack

- Python, PyTorch / TensorFlow
- Transformer (Seq2Seq with attention)
- NLTK / sacrebleu (BLEU evaluation)