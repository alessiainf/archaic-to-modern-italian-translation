# Archaic to Modern Italian Translation with LLMs

This project explores automatic translation from **archaic Italian (13th–15th century)** to **modern Italian** using Large Language Models (LLMs) and various prompting strategies.

## Overview

We evaluated three instruction-tuned multilingual LLMs:

- **LLaMA 3 8B instruct**
- **Minerva 7B instruct**
- **Qwen 2.5 3B instruct**

Each model was tested under multiple prompting configurations:
- Zero-shot (LLaMA only)
- Few-shot
- Few-shot with POS tagging (LLaMA only)
- TEaR-inspired prompting (Translate–Evaluate–Refine)  (Qwen only)

Translations were evaluated using:
- **Human annotators**
- **LLM-based judges**: Gemini 2.0 Flash and M-Prometheus 7B

---

## Methodology

- **Dataset**: Sentences from historical Italian texts and AI-generated examples.
- **Prompting**: Custom few-shot examples per model, written in Italian or English.
- **Inference**: Deterministic decoding (`do_sample=False`) for reproducibility.
- **Evaluation rubric** (1–5 scale): Semantic fidelity, fluency, grammatical correctness, style adaptation.

---

## Results

| Model   | Human Avg. Score | Prometheus Avg. | Human 4–5 Ratings (out of 30) |
|---------|------------------|------------------|-------------------------------|
| LLaMA   | 3.57             | 3.47             | 14                            |
| Minerva | 3.27             | 3.00             | 10                            |
| Qwen    | 3.20             | 2.73             | 8                             |

- **LLaMA** produced the most fluent and accurate translations.
- **Minerva** often paraphrased too much, reducing fidelity.
- **Qwen**, with TEaR-like prompting, improved but struggled with historical references and add improper terms.

---

## Conclusions

All models performed reasonably well, with LLaMA aligning most closely with human preferences. Prompt design significantly affects translation quality. Automatic judges like **M-Prometheus** were more reliable than **Gemini**, showing closer agreement with human evaluation.

---

## Authors

- [A. Infantino 1922069](https://github.com/alessiainf)
- [A. Di Chiara 1938462](https://github.com/AlessandroDiChiara)
- [F. Fragale 2169937](https://github.com/Bannfrost99)

---

## Reference

- Feng et al., 2024 – [TEaR: Improving LLM-based Machine Translation with Systematic Self-Refinement](https://arxiv.org/abs/2402.16379)


