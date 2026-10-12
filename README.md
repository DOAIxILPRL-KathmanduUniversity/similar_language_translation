<div align="center">

# 🌐 Hindi–Nepali Parallel Corpus for Similar Language Translation

[![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-blue.svg)](LICENSE)
[![Language: Hindi](https://img.shields.io/badge/Language-Hindi%20(hi)-orange.svg)](#)
[![Language: Nepali](https://img.shields.io/badge/Language-Nepali%20(ne)-red.svg)](#)
[![Pairs: 274k](https://img.shields.io/badge/Sentence%20Pairs-274%2C170-brightgreen.svg)](#)
[![Words: 14.6M](https://img.shields.io/badge/Tokens-14.68M-purple.svg)](#)
[![HuggingFace: Compatible](https://img.shields.io/badge/HuggingFace-Compatible-yellow.svg)](docs/DATASET_CARD.md)
[![Institution: Kathmandu University](https://img.shields.io/badge/KU-DOAI%20x%20ILPRL-blueviolet.svg)](https://github.com/DOAIxILPRL-KathmanduUniversity)

**A large-scale parallel translation corpus between Hindi and Nepali featuring 274,170 sentence pairs (~14.68 Million tokens), grounded synthetic generation, and multi-source adversarial curation.**

Developed at the **Department of Artificial Intelligence (DOAI)** & **Intelligent Language Processing Research Lab (ILPRL)**, **Kathmandu University (KU)**.

</div>

---

## 📌 Executive Summary

Hindi and Nepali are closely related Indo-Aryan sister languages that share the Devanagari script, Subject-Object-Verb (SOV) sentence order, and extensive cognate vocabulary. Despite these structural symmetries, high-quality open parallel translation data between Hindi and Nepali remains scarce.

This repository provides a parallel corpus of **274,170 synchronized sentence pairs** across Train, Validation, and Test splits.

---

## 📊 Dataset Overview & Statistics

| Dataset Split | Sentence Pairs | Hindi Words | Nepali Words | Avg Length (HI) | Avg Length (NE) | Lexical Overlap (%) | Files |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Train (Adversarial)** | **254,199** | 6,507,397 | 6,939,595 | 25.6 words | 27.3 words | **55.1%** | `data/raw/adversarial/` |
| **Validation** | **9,970** | 308,119 | 311,130 | 30.9 words | 31.2 words | **69.0%** | `data/raw/finalval - val.csv` |
| **Test** | **10,001** | 309,155 | 310,452 | 30.9 words | 31.0 words | **71.1%** | `data/raw/finaltest - test.csv` |
| **Total** | **274,170** | **7,124,671** | **7,561,177** | **26.0 words** | **27.6 words** | **63.4% (avg)** | Raw archives |

---

## 🔬 Provenance & Synthesis Methodology

As documented in the project notes:

### 1. Grounded LLM Synthesis
- **Model:** OpenAI ChatGPT (GPT-4 and predecessor models).
- **Grounded Seed Corpus:** Extracted from native Nepali text sources (including Roundtrip OCR datasets on Hugging Face).
- **Alignment Guideline:** Synthesis strictly adhered to the rule that the **order of words uttering in Nepali is mirrored faithfully in the Hindi translation**, preserving syntactic cadence and minimizing distortion.

### 2. Multi-Resource Adversarial Curation
- The primary training split combines diverse multi-domain text collected from various resources to provide adversarial linguistic robustness. The original collection also included an English counterpart (currently omitted in this release).
- Methodology inspired by:
  > **Duwal, S., & Bal, B. K. (2019).** *Efforts in the Development of an Augmented English–Nepali Parallel Corpus.* Proceedings of the International Conference on Language Technologies for All (LT4All 2019), ELRA. [Paper Link](https://lt4all.elra.info/proceedings/lt4all2019/pdf/2019.lt4all-1.94.pdf).

---

## 📁 Repository Structure

```text
similar_language_translation/
├── data/
│   └── raw/                       # Source parallel data archives
│       ├── adversarial/
│       │   ├── finalhi-ne-en.hi.txt   # Training Hindi text (~254k lines)
│       │   └── finalhi-ne-en.ne.txt   # Training Nepali text (~254k lines)
│       ├── finaltest - test.csv       # Test split (10,001 rows)
│       └── finalval - val.csv         # Validation split (10,001 rows)
├── docs/
│   ├── CREDITS.md                 # Full project credits & methodology
│   └── DATASET_CARD.md            # Hugging Face compliant dataset card
├── .gitattributes                 # Line endings and format rules
├── .gitignore                     # Git ignore rules
├── LICENSE                        # CC0-1.0 Universal License
└── README.md                      # Dataset documentation
```

---

## 🚀 Quickstart

Clone the repository and load the parallel splits using `pandas`:

```bash
git clone https://github.com/DOAIxILPRL-KathmanduUniversity/similar_language_translation.git
cd similar_language_translation
```

```python
import pandas as pd

# 1. Load Validation and Test splits (CSV: input_text = Hindi, target_text = Nepali)
val_df  = pd.read_csv("data/raw/finalval - val.csv")
test_df = pd.read_csv("data/raw/finaltest - test.csv")

# 2. Load Adversarial Training split (line-by-line text files)
with open("data/raw/adversarial/finalhi-ne-en.hi.txt", "r", encoding="utf-8") as f:
    train_hi = [line.strip() for line in f]

with open("data/raw/adversarial/finalhi-ne-en.ne.txt", "r", encoding="utf-8") as f:
    train_ne = [line.strip() for line in f]

train_df = pd.DataFrame({"hindi": train_hi, "nepali": train_ne})

print(f"Loaded {len(train_df):,} training pairs, {len(val_df):,} validation rows, {len(test_df):,} test rows.")
print(train_df.head(5))
```

---

## 🤝 Credits

- **Aadarsh Pandit** – Department of Artificial Intelligence (DOAI) & Intelligent Language Processing Research Lab (ILPRL), Kathmandu University
- **Ishan Pandey** – Department of Artificial Intelligence (DOAI), Kathmandu University
- **Yudhin Khanal** – Department of Artificial Intelligence (DOAI), Kathmandu University

For complete provenance, synthesis methodology, and background notes, refer to [CREDITS.md](docs/CREDITS.md).

---

## 📄 License

This dataset is dedicated to the public domain under the **Creative Commons Zero v1.0 Universal ([CC0 1.0](LICENSE))** license.
