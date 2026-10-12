# Credits

## 🤝 Project Credits

- **Aadarsh Pandit** – Department of Artificial Intelligence (DOAI) & Intelligent Language Processing Research Lab (ILPRL), Kathmandu University
- **Ishan Pandey** – Department of Artificial Intelligence (DOAI), Kathmandu University
- **Yudhin Khanal** – Department of Artificial Intelligence (DOAI), Kathmandu University

**Institutional Affiliations:**
- Department of Artificial Intelligence (DOAI), Kathmandu University, Dhulikhel, Nepal
- Intelligent Language Processing Research Lab (ILPRL), Kathmandu University, Dhulikhel, Nepal

---

## 🔬 Dataset Provenance & Methodology

The details below reflect the exact provenance and methodology recorded for this parallel corpus:

### 1. Data Collection & Adversarial Curation
- Adversarial data was collected from diverse resources and compiled into a unified training split.
- The raw source data originally had an English counterpart as well, which is currently missing/omitted in this release.

### 2. LLM Synthesis
- **Engines:** OpenAI ChatGPT (GPT-4 and predecessor models).
- **Grounded Seed Source:** Native Nepali text grounded from the Roundtrip OCR dataset on Hugging Face.
- **Syntactic Alignment Rule:** Synthesis adhered to a strict guideline and philosophy ensuring that the **word utterance order in Nepali was mirrored faithfully in the Hindi translation**.

### 3. Project Background
- A prior Hindi–Nepali parallel corpus had been constructed during the 4th semester as a semester project; however, this synthetic data was determined to be superior for current work.

### 4. Methodological Reference
- The augmentation approach is inspired by:
  > **Duwal, S., & Bal, B. K. (2019).** *Efforts in the Development of an Augmented English–Nepali Parallel Corpus.* Proceedings of the International Conference on Language Technologies for All (LT4All 2019), ELRA. [Paper Link](https://lt4all.elra.info/proceedings/lt4all2019/pdf/2019.lt4all-1.94.pdf).
- Under this framework, synthetic data serves as the primary training corpus, with plans to generate NLLB- or T5-based parallel data for comparative evaluation.

---

## 📜 Archival Reference (from `Credits.docx`)

```text
Credits to aadash pandit, ishan and yudin khanal.  - adversarial data is collected from all kinds of resources then put together. The data also had english counterpart which we miss currently.
LLM Synthesis
Chatgpt 4 and before were used
The strict guideline was using grounded nepali dataset from Roundtrip OCR data from huggingface then as per our philosophy enforced the rule that the order or words uttering in nepali is meant to be seen in hindi translation. 
Expectations
We did have a corpus for hindi nepali parallel corpus which was made during 4th semester during our semester project yet we thought this synthetic data is better.
We will use https://lt4all.elra.info/proceedings/lt4all2019/pdf/2019.lt4all-1.94.pdf Efforts in the Development of an Augmented English–Nepali Parallel Corpus Sharad Duwal, Bal Krishna Bal like method but use synthetic is primary training and for rest of data we generate our nllb or t5 based data and compare for further work.
```
