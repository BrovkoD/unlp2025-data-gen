# 🌍 UNLP 2025 — Cross-Lingual Data Generation

This repository contains a Jupyter notebook for generating and filtering synthetic multilingual datasets via automated **back-and-forth translation**. It supports **UNLP 2025** experiments where dataset diversity is essential for robust **manipulation detection** and **classification**.

---

## 📄 Notebook

### [`cross_translation.ipynb`](cross_translation.ipynb)

The notebook enables multilingual data generation via:

- `GoogleTranslator` or `DeeplTranslator` from [`deep-translator`](https://pypi.org/project/deep-translator/)

---

## 🛠 Dependencies

Install required packages:

```bash
pip install pandas numpy deep_translator
```

## 🚀 Usage

You can run the notebook directly in Google Colab

## 💡 Applications

- Synthetic data augmentation for NLP pipelines
- Multilingual training data for low-resource languages
- Robustness testing of translation services

## 🔭 Future Work

Planned features include semantic filtering using back-translation quality scores with SequenceMatcher:

```python
from difflib import SequenceMatcher
from deep_translator import GoogleTranslator

def is_good_translation(original, translated, threshold=0.75):
    back_translated = GoogleTranslator(source='auto', target='en').translate(translated)
    similarity = SequenceMatcher(None, original, back_translated).ratio()
    return similarity >= threshold
```

This will help filter noisy or inaccurate translations to ensure high-quality augmented datasets.

## 📁 Files

```
unlp2025-data-gen/
├── cross_translation.ipynb   # Core notebook for multilingual data generation
└── README.md                 # You're reading it!
```
