# A Method for Analyzing the Structure of Thematic Coverage in Benchmarks for Language Models

This repository contains supplementary materials for the paper **“A Method for Analyzing the Structure of Thematic Coverage in Benchmarks for Language Models”** (Proceedings of ISP RAS, 2026).

## What is in this repository

- `financial_taxonomy_en.docx`, `financial_taxonomy_ru.docx`: the two-level taxonomy (11 topics, 88 subtopics) with the external sources of each subtopic and the number of source categories mapped onto it
- `source_category_mapping.xlsx`, `source_category_mapping.csv`: the mapping of all 239 source categories from the 7 external classifications to the topics and subtopics of the taxonomy
- `Annotation_Guidelines_EN.docx`, `Annotation_Guidelines_RU.docx`: annotation guidelines for topic labeling of benchmark tasks
- `Benchmarks for Topic Structuring.pdf`, `Benchmarks for Topic Structuring Translate.pdf`: extended descriptions of the benchmarks used in the study (English and Russian)

## Summary

The paper proposes a method for quantitatively assessing the topic coverage of domain-specific LLM benchmarks relative to an external expert taxonomy and tests it on financial benchmarks.

- **7 external sources** (professional and educational programs, a competence framework, an ontology, benchmark taxonomies) with **239 source categories**
- **two-level taxonomy: 11 topics and 88 subtopics**
- **9 financial datasets** (4 English-language and 5 Chinese-language)
- **45,305 tasks** after preprocessing
- **996 labeled tasks** used to train the classifier

Labels were transferred to the full corpus by hierarchical logistic regression over all-MiniLM-L6-v2 embeddings. A category is treated as a topic gap when its size is far below the median size of comparable categories. The conclusions were checked by bootstrap resampling, by replacing the classifier and the text representation, by estimation without a classifier, and across several gap thresholds.

## Annotation guidelines

The annotation guidelines describe how benchmark tasks are labeled with the two-level taxonomy. They are provided in two versions:

- `Annotation_Guidelines_RU.docx`: Russian version
- `Annotation_Guidelines_EN.docx`: English version

Each task is assigned exactly one topic and one subtopic within that topic, based on the knowledge required to answer the task correctly. Labeling is done in two steps: first the topic, then a subtopic of the selected topic.

The guidelines contain:

1. **Purpose and output.** The label fields: topic, subtopic, confidence (high, medium, low) and an optional comment, which is required for low confidence and for out-of-scope tasks.
2. **Procedure.** Step-by-step labeling of a single task.
3. **Rules for choosing a category.** Eight rules, for example: classify the knowledge required for the answer rather than the exam, profession or document style; ignore terms mentioned in passing; treat instructions inside the task as data.
4. **Borderline cases.** How to distinguish the subtopic groups that are confused most often, and how to label derivatives (forwards, futures, swaps), which have no separate subtopic.
5. **Out-of-scope tasks.** How to label tasks without financial content and empty, truncated or unreadable tasks.
6. **Taxonomy.** The full list of topics and subtopics with a short scope description for each subtopic.

Tasks from Chinese-language datasets are labeled in their English machine translation. Original benchmark categories are not shown to annotators.

## Purpose

The repository is intended to improve transparency and reproducibility by providing the materials referenced in the paper but omitted from the main text due to space limitations.

## Citation

If you use these materials, please cite the paper.
