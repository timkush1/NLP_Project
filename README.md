# NLP_Project

# Multi-lingual Knowledge Transfer in Large Language Models

### Authors
- **Omri Tzur** - Tel-Aviv University ([omritzur@mail.tau.ac.il](mailto:omritzur@mail.tau.ac.il))
- **Shir Yakov** - Tel-Aviv University ([shiryakov@mail.tau.ac.il](mailto:shiryakov@mail.tau.ac.il))
- **Tim Kushmaro** - Tel-Aviv University ([timk@mail.tau.ac.il](mailto:timk@mail.tau.ac.il))

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
2. [Related Work](#related-work)
3. [Methodology](#methodology)
4. [Experiments](#experiments)
5. [Results and Observations](#results-and-observations)
6. [Key Insights and Discussion](#key-insights-and-discussion)
7. [Conclusion](#conclusion)
8. [Limitations](#limitations)
9. [Acknowledgments](#acknowledgments)
10. [References](#references)

---

## Introduction
In recent years, Large Language Models (LLMs) have rapidly integrated into various fields, revolutionizing information processing and decision-making. However, their effectiveness significantly drops for low-resource languages due to limited data availability and structural differences from high-resource languages like English. Addressing these disparities is crucial for ensuring equitable global usability.

This project systematically explores these challenges by:
1. Evaluating discrepancies in LLM performance across multiple languages.
2. Testing strategies such as intermediary translation and Chain of Thought (CoT) reasoning to enhance multilingual capabilities.

Our goal is to improve the multilingual proficiency of LLMs, making them reliable tools for an interconnected world.

---

## Related Work
### Challenges in Multilingual NLP
High-resource languages benefit from extensive pretraining, while low-resource languages often suffer from limited generalization capabilities. Evaluation frameworks for multilingual models are often benchmark-specific and fail to address deeper linguistic structures, particularly for underrepresented languages.

### Strategies for Cross-Lingual Performance Enhancement
- **Cross-Lingual Thought Prompting (XLT):** Structured reasoning prompts that improve performance in low-resource languages but require extensive resources.
- **Transfer Learning:** Fine-tuning multilingual models with high-resource language data significantly boosts performance for low-resource tasks.

Despite progress, multilingual models still face limitations in linguistic generalization, requiring more robust strategies.

---

## Methodology
### Objective
The project explores strategies to improve the performance of LLMs in low-resource languages using:
- **Intermediary Translation:** Leveraging high-resource language capabilities to reduce performance disparities.
- **Chain of Thought (CoT) Prompts:** Encouraging step-by-step reasoning for logical consistency in responses.

More details will follow in the next iterations, expanding sections like **Experiments**, **Results**, and **Key Insights**.
