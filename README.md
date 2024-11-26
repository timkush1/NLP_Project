# NLP_Project

# Multi-lingual Knowledge Transfer in Large Language Models

### Authors
- **Tim Kushmaro** - Tel-Aviv University ([timk@mail.tau.ac.il](mailto:timk@mail.tau.ac.il))
- **Shir Yakov** - Tel-Aviv University ([shiryakov@mail.tau.ac.il](mailto:shiryakov@mail.tau.ac.il))
- **Omri Tzur** - Tel-Aviv University ([omritzur@mail.tau.ac.il](mailto:omritzur@mail.tau.ac.il))

---

## Abstract
Multilingual capabilities in large language models (LLMs) are crucial for their effectiveness across different domains. This project examines the challenges of cross-lingual knowledge transfer in LLMs, focusing on performance disparities between high-resource and low-resource languages. Strategies such as translation-enhanced evaluation and Chain of Thought (CoT) prompting are evaluated to address these discrepancies and improve multilingual performance.

The findings reveal that:
- Translation-enhanced evaluation effectively reduces performance gaps.
- CoT prompting faces challenges in multilingual contexts.

This work contributes to enhancing multilingual NLP systems, ensuring that LLMs can achieve more equitable performance across various languages.

[View the full code repository here.](https://github.com/timkush1/NLP_Project)

---

## Table of Contents
1. [Introduction](#introduction)
2. [Methodology](#methodology)
3. [Experiments](#experiments)
4. [Results and Observations](#results-and-observations)
5. [Key Insights and Discussion](#key-insights-and-discussion)
6. [Conclusion](#conclusion)
7. [Limitations](#limitations)
8. [Acknowledgments](#acknowledgments)
9. [References](#references)

---

## Introduction
In recent years, Large Language Models (LLMs) have rapidly integrated into various fields, revolutionizing information processing and decision-making. However, their effectiveness significantly drops for low-resource languages due to limited data availability and structural differences from high-resource languages like English. Addressing these disparities is crucial for ensuring equitable global usability.

This project systematically explores these challenges by:
1. Evaluating discrepancies in LLM performance across multiple languages.
2. Testing strategies such as intermediary translation and Chain of Thought (CoT) reasoning to enhance multilingual capabilities.

Our goal is to improve the multilingual proficiency of LLMs, making them reliable tools for an interconnected world.

---

## Methodology

### Objective
This research focuses on enhancing the performance of Large Language Models (LLMs) in low-resource languages. Key strategies include:

1. **Intermediary Translation Phases:** Utilizing high-resource language performance (e.g., English) to improve accuracy and consistency for low-resource languages.
2. **Chain of Thought (CoT) Prompts:** Encouraging step-by-step reasoning to improve logical consistency, especially for complex queries in multilingual tasks.

These approaches aim to bridge performance gaps between high- and low-resource languages, improving both accuracy and reasoning capabilities.

---

### Data Collection
The following datasets were used to evaluate LLM performance:

1. **MLQA (Multilingual Question Answering):** 
   - Contains over 5,000 extractive QA instances across seven languages: English (en), Arabic (ar), German (de), Spanish (es), Hindi (hi), Vietnamese (vi), and Chinese (zh).
   - Designed to test cross-lingual knowledge transfer in question-answering tasks.

2. **SQuAD (Stanford Question Answering Dataset):** 
   - Includes over 100,000 question-answer pairs derived from English Wikipedia.
   - Used to fine-tune the mBERT model for foundational QA capabilities in English before cross-lingual evaluation.

---

### Model
The project utilizes the **mBERT (Multilingual BERT)** model:
- **Version:** `bert-base-multilingual-cased`
- **Capabilities:** Pretrained for multilingual tasks across diverse languages.
- **Fine-Tuning:** 
  - Optimized using the SQuAD dataset for robust QA capabilities in English.
  - Evaluated on the MLQA dataset to measure cross-lingual knowledge transfer.

---

### Preprocessing
Key steps for data preparation:
1. **Tokenization:** Using the mBERT tokenizer to convert questions and contexts into suitable input sequences.
2. **Doc Stride:** Splitting longer contexts into overlapping segments for comprehensive coverage.
3. **Noise Reduction:** Removing special characters, unnecessary whitespace, and irrelevant content.
4. **Translation Phase:**
   - Translating low-resource language questions into English.
   - Processing with mBERT and translating answers back into the original language.
   - Ensuring minimal semantic drift during translation.

---

### Evaluation Metrics
Two primary metrics were used to assess model performance:

1. **Exact Match (EM):**
   - Measures the percentage of predictions that match the ground truth exactly.
   - Indicates strict correctness in QA tasks.

2. **F1 Score:**
   - The harmonic mean of precision and recall.
   - Captures partial correctness by measuring overlap between predicted and true answers.

---

## Experiments

### Metrics Application
Both **EM** and **F1 Score** metrics were applied to the MLQA dataset, providing insights into cross-lingual performance, including disparities between high-resource and low-resource languages.

---

### Experimental Configurations
Three distinct configurations were explored:

1. **Zero-Shot Multilingual Performance:** 
   - Baseline configuration where mBERT, fine-tuned only on English (SQuAD), was tested directly on MLQA without explicit fine-tuning for target languages.
   - Highlighted mBERT's pretraining strengths and generalization challenges.

2. **Translation-Enhanced Evaluation:**
   - Introduced an intermediary translation phase.
   - Questions in low-resource languages were translated into English, processed by mBERT, and translated back for evaluation.
   - Mitigated data scarcity challenges for low-resource languages.

3. **Chain of Thought (CoT) Prompting:**
   - Added structured reasoning prompts to guide step-by-step decision-making.
   - Tested whether reasoning mechanisms improved multilingual task performance.

---

### Results and Observations

1. **Zero-Shot Performance:**
   - Achieved highest performance for high-resource languages (e.g., English, Spanish).
   - Average F1 Score: **55.9**
   - Average EM: **41.2**

2. **Translation Phase:**
   - Notable improvement in low-resource languages (e.g., Hindi, Arabic).
   - Average F1 Score: **53.1**
   - Average EM: **32.2**

3. **Chain of Thought Prompting:**
   - Underperformed compared to other configurations.
   - Average F1 Score: **45.9**
   - Average EM: **31.8**
   - Challenges: Logical inconsistency and verbosity in low-resource languages.

---

### Figures
1. **F1 Score Heatmap Across Languages**
   - Visualizes performance disparities.
2. **Exact Match Heatmap Across Languages**
   - Highlights accuracy differences.

---
---

## Key Insights and Discussion

### Performance Disparities and Data Imbalance
- **Observation:** Significant disparities exist between high-resource and low-resource languages. 
- **Details:** High-resource languages (e.g., English, Spanish) performed significantly better due to abundant pretraining data. In contrast, low-resource languages (e.g., Hindi, Arabic) struggled, reflecting the importance of balanced datasets.
- **Takeaway:** The need for inclusive training data is critical to ensuring equitable global usability of multilingual models.

---

### Effectiveness of Translation-Enhanced Evaluation
- **Observation:** Translation-enhanced evaluation reduced performance gaps between high- and low-resource languages.
- **Details:** By leveraging mBERT's strong English capabilities, translation strategies addressed data scarcity challenges in low-resource languages.
- **Challenges:** Semantic drift during translation occasionally impacted accuracy.
- **Takeaway:** Future work should refine translation mechanisms, possibly with domain-specific fine-tuning to minimize translation artifacts.

---

### Limitations of Chain of Thought Prompting
- **Observation:** CoT prompting, while promising, struggled with multilingual tasks.
- **Details:** Logical inconsistencies and verbosity in low-resource languages hindered performance.
- **Challenges:** The lack of multilingual reasoning datasets and pretraining on structured prompts limited CoT's effectiveness.
- **Takeaway:** Future research could explore pretraining models on multilingual reasoning tasks to improve CoT applicability.

---

### Linguistic Diversity and Structural Differences
- **Observation:** Languages with complex morphology or syntax (e.g., Arabic, Chinese) posed greater challenges.
- **Details:** These languages require more advanced tokenization and pretraining strategies.
- **Takeaway:** Typologically informed pretraining or linguistically diverse architectures may help address structural disparities.

---

### Broader Implications
- **Inclusive Datasets:** Addressing linguistic inequality through balanced pretraining datasets is essential.
- **Hybrid Strategies:** Combining translation-based methods with reasoning-focused techniques could enhance cross-lingual generalization.
- **Future Directions:** Multilingual NLP research should prioritize equitable representation, advanced reasoning techniques, and hybrid approaches.

---

## Conclusion

This study demonstrates that **translation-enhanced evaluation** effectively mitigates performance disparities between high- and low-resource languages, while **Chain of Thought (CoT) prompting**, although promising, requires significant refinement for multilingual contexts.

### Key Takeaways:
1. Translation techniques leverage high-resource language capabilities to improve low-resource language performance but must account for translation drift.
2. CoT prompting struggles with logical consistency in multilingual settings, highlighting the need for specialized reasoning-focused datasets.

### Recommendations:
1. Develop balanced multilingual pretraining datasets to reduce linguistic disparities.
2. Explore hybrid strategies combining translation, fine-tuning, and reasoning mechanisms to enhance performance across diverse languages.

---

## Limitations
This project has several limitations:
1. **Language Coverage:** Focused on seven languages (English, Arabic, German, Spanish, Hindi, Swahili, and Mandarin Chinese). Many low-resource languages remain unexplored.
2. **Translation Challenges:** Translation steps occasionally introduced semantic drift, impacting accuracy.
3. **Generalization:** Results were evaluated primarily on the MLQA dataset and may not generalize to specialized domains (e.g., legal or medical).
4. **Chain of Thought Prompting:** CoT methods require adaptation for low-resource languages with rich morphology and complex syntax.

---

## Acknowledgments
We extend our heartfelt thanks to **Maor Ivgi** for his invaluable guidance and mentorship throughout this project. His expertise in NLP provided the foundational knowledge necessary for tackling the challenges explored in this study.

---

## References
1. W. Xu, B. Haider, and S. Mansour, “End-to-end slot alignment and recognition for cross-lingual NLU,” 2020. [Available Online](https://aclanthology.org/2020.emnlp-main.410/)
2. S. Rajaee and C. Monz, “Analyzing the evaluation of cross-lingual knowledge transfer in multilingual language models,” 2024. [Available Online](https://aclanthology.org/2024.eacl-long.177/)
3. F. Wang, K.-H. Huang, K.-W. Chang, and M. Chen, “Self-augmentation improves zero-shot cross-lingual transfer,” 2023. [Available Online](https://arxiv.org/abs/2309.10891)
4. N. Arivazhagan et al., “Massively multilingual neural machine translation in the wild: Findings and challenges,” 2019. [Available Online](https://arxiv.org/abs/1907.05019)

---




