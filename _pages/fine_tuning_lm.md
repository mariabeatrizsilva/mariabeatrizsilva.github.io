---
layout: single
title: "Fine-Tuning Language Models"
permalink: /projects/fine_tuning_lm/
author_profile: true
classes: wide
---

**Course Project for Natural Language Processing (Graduate Level)**  
**Fall 2025**

[📂 GitHub Repository](https://github.com/mariabeatrizsilva/FineTuningLMs)

---

## Overview

This project explores fine-tuning strategies for two types of language models: an encoder-only model (BERT) for sentiment classification and an encoder-decoder model (T5) for natural language to SQL translation. The project investigates challenges in model generalization, robustness to out-of-distribution data, and conditional generation of structured outputs.

---

## Part 1: Fine-Tuning BERT for Sentiment Classification

### Task
Fine-tuned BERT on the IMDB dataset to perform sentiment analysis, achieving **>91% accuracy** on the test set.

### Data Transformations & Robustness Testing

To evaluate model robustness, I designed realistic out-of-distribution (OOD) transformations that simulate real-world test-time inputs:

**Transformation Strategy:**
- **Typo Addition**: Created a keyboard-proximity map to introduce realistic typos (e.g., 'a' → 'q', 'w', 's', 'z') at a controlled rate
- **Synonym Replacement**: Used WordNet to replace words with synonyms while maintaining semantic meaning and implementing case-matching to prevent errors
- **Letter-to-Number Substitution**: Converted visually similar characters (e.g., O→0, t→7) to test perceptual robustness

These transformations were carefully ordered (synonyms → typos → letter-to-number) to ensure the data remained human-readable while testing model robustness.

**Results:**
- Original test accuracy: **91.1%**
- Transformed test accuracy: **~85%** (4-6% decrease)
- The performance drop demonstrated the model's sensitivity to realistic input variations

### Data Augmentation Implementation

**Approach:** Augmented the training set with 5,000 transformed examples using the same transformation pipeline.

**Impact:**
- **Transformed test set**: Accuracy improved from ~85% → **89%** (4% gain)
- **Original test set**: Minimal performance decrease (0.1%, potentially negligible)

This demonstrates that targeted data augmentation can significantly improve robustness to OOD data with minimal cost to in-distribution performance.

**Key Implementation:**
- Implemented custom `create_augmented_dataloader` function to combine original and transformed training data
- Designed transformation pipeline with tunable rates for each transformation type
- Balanced augmentation to maintain readability while improving model robustness

---

## Part 2: Fine-Tuning T5 for Natural Language to SQL

### Task
Fine-tuned T5-small to translate natural language flight booking queries into executable SQL statements, achieving **≥65 F1 score** on structured output generation.

**Example:**
- Input: "Show me flights from Boston to San Francisco"
- Output: `SELECT * FROM flight WHERE from_airport = 'BOS' AND to_airport = 'SFO'`

### Implementation Contributions

Working from a skeleton codebase, I implemented:

**Evaluation Pipeline:**
- Designed and implemented complete evaluation loop for conditional generation
- Integrated three metrics: Record F1, Record Exact Match, and SQL Query Exact Match
- Implemented database execution to validate SQL query correctness

**Hyperparameter Tuning:**
- Systematically explored learning rates, batch sizes, and stopping criteria
- Optimized for F1 score on development set before final test evaluation
- Documented ablation studies showing impact of different design choices

**Data Processing & Experimentation:**
- Experimented with T5 tokenization strategies for structured SQL output
- Analyzed error patterns across query types and complexity levels
- Conducted detailed error analysis identifying common failure modes

---

## Technical Stack

**Models:** BERT (encoder-only), T5-small (encoder-decoder)  
**Frameworks:** PyTorch, Hugging Face Transformers  
**Datasets:** IMDB (sentiment), Custom flight booking natural language to SQL  
**Tools:** WordNet (for synonym replacement), SQL database evaluation

---

## Key Takeaways

1. **OOD Robustness**: Models can be brittle to realistic input variations; data augmentation is an effective mitigation strategy
2. **Structured Generation**: Conditional generation requires careful evaluation beyond string matching
3. **Design Choices Matter**: Systematic experimentation with data processing, tokenization, and architecture decisions significantly impacts performance
4. **Trade-offs**: Improving robustness to transformed data can be achieved with minimal performance cost on original data

