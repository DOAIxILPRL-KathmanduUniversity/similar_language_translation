---
language:
- hi
- ne
license: cc0-1.0
multilinguality:
- translation
size_categories:
- 100K<n<1M
source_datasets:
- extended|other
task_categories:
- translation
task_ids:
- machine-translation
pretty_name: "Hindi-Nepali Parallel Corpus for Similar Language Translation"
tags:
- machine-translation
- hindi
- nepali
- south-asian-languages
- low-resource-nlp
- devanagari
- similar-languages
---

# Dataset Card: Hindi-Nepali Parallel Corpus

## Dataset Description
- **Repository:** [DOAIxILPRL-KathmanduUniversity/similar_language_translation](https://github.com/DOAIxILPRL-KathmanduUniversity/similar_language_translation)
- **Credits:**
  - Aadarsh Pandit (DOAI & ILPRL, Kathmandu University)
  - Ishan Pandey (DOAI, Kathmandu University)
  - Yudhin Khanal (DOAI, Kathmandu University)
- **Language Pair:** Hindi (`hi`) ↔ Nepali (`ne`)
- **Total Sentence Pairs:** 274,170
- **Total Words:** ~14.68 Million (7,124,671 Hindi words, 7,561,177 Nepali words)
- **License:** Creative Commons Zero v1.0 Universal (CC0-1.0)

---

## Dataset Summary
This dataset contains a parallel corpus of Hindi (`hi`) and Nepali (`ne`) sentence pairs for Similar Language Machine Translation. Both languages share the Devanagari script, Subject-Object-Verb (SOV) sentence structure, and substantial lexical overlap (~55% to 71%).

### Splits & Files Overview

| Split | Raw File(s) in `data/raw/` | Format | Raw Rows / Lines | Valid Pairs | Hindi Words | Nepali Words |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Train (Adversarial)** | `adversarial/finalhi-ne-en.hi.txt`<br>`adversarial/finalhi-ne-en.ne.txt` | Line-by-line text | 254,207 lines | 254,199 | 6,507,397 | 6,939,595 |
| **Validation** | `finalval - val.csv` | CSV (`input_text`, `target_text`) | 10,001 rows | 9,970 | 308,119 | 311,130 |
| **Test** | `finaltest - test.csv` | CSV (`input_text`, `target_text`) | 10,001 rows | 10,001 | 309,155 | 310,452 |
| **Total** | | | | **274,170** | **7,124,671** | **7,561,177** |

---

## Data Structure

### Formats & Column Mapping
1. **CSV Files (`finalval - val.csv`, `finaltest - test.csv`):**
   - `input_text` (string): Hindi sentence in Devanagari script.
   - `target_text` (string): Corresponding Nepali sentence in Devanagari script.

2. **Parallel Text Files (`adversarial/finalhi-ne-en.hi.txt`, `finalhi-ne-en.ne.txt`):**
   - `finalhi-ne-en.hi.txt`: Hindi sentence per line.
   - `finalhi-ne-en.ne.txt`: Synchronized Nepali sentence per line.

### Example Record
```json
{
  "hindi": "मधुमेह ने विश्व में एक महामारी का रूप ले लिया है और इसके कई प्रकार के सामाजिक और आर्थिक दुष्परिणाम भी सामने आ रहे हैं।",
  "nepali": "मधुमेहले विश्‍वमा एउटा महामारीको रूप लिइसकेको छ तथा यसका धेरै प्रकारका सामाजिक अनि आर्थिक दुष्‍परिणाम पनि अघि आइरहेका छन्।"
}
```

---

## Provenance & Methodology
- **Adversarial Collection:** Sourced across diverse domains and compiled into parallel training text.
- **LLM Synthesis:** Synthesized using OpenAI ChatGPT (GPT-4 and predecessor models) with seed sentences grounded from native Nepali sources (Roundtrip OCR dataset on Hugging Face). Synthesis strictly maintained the word utterance order of Nepali in Hindi translations.
- **Methodological Reference:** Inspired by the augmentation approach in *Duwal & Bal (2019), Efforts in the Development of an Augmented English–Nepali Parallel Corpus (LT4All)*.

---

## Use Cases
- Similar Language Machine Translation between Hindi and Nepali.
- Sequence-to-sequence model training and evaluation (e.g., NLLB, mT5).
- Linguistic and lexical overlap analysis between Indo-Aryan sister languages.
