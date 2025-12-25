This project implements a simple Vision–Language–Action (VLA) pipeline for expressive computation.

The system independently predicts emotions from:
- facial images (vision)
- user text (language)



## Emotion Space

The system operates on a constrained, interpretable emotion set:

- angry
- fear
- happy
- neutral
- sad

Vision supports all emotions; language supports a subset. Fusion logic explicitly handles this asymmetry.

---

## Architecture

1. **Vision Model**
   - CNN trained on FER-2013
   - Input: grayscale face image (48×48)
   - Output: emotion logits

2. **Text Model**
   - Transformer encoder (DistilBERT)
   - Input: raw text
   - Output: emotion logits

3. **Fusion**
   - Late fusion at decision level
   - Probabilities aligned into a shared emotion space
   - Vision-dominant weighting with text refinement

---

## Tech Stack

- PyTorch
- Hugging Face Transformers
- FER-2013 dataset
- Emotion-labeled text dataset

---

