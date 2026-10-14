# CART
### Clustering-based Analysis of Recurring narratives for Taxonomy construction

CART is an unsupervised, clustering-based framework designed to identify, extract, and organize recurring political narratives from large-scale textual data without requiring predefined narrative categories or extensively annotated training datasets.

Constructing a taxonomy of political narratives traditionally requires substantial manual effort, including the identification of relevant textual material, the interpretation of recurring narrative patterns, and the development of a classification scheme. These tasks become increasingly challenging when analyzing large collections of political discourse, where narratives may be expressed through diverse linguistic formulations and evolve over time.

CART addresses these challenges by integrating semantic embeddings, unsupervised ensemble-based confidence estimation and data screening, LLM-assisted narrative extraction, and quality-driven cluster discovery within a unified analytical workflow. Rather than starting from a predetermined set of narrative labels, the framework identifies recurring patterns in the data and progressively organizes them into an interpretable narrative taxonomy.

The approach is designed to reduce the dependence on extensive manual annotation, facilitate the exploration of large textual corpora, and support the systematic identification of narrative structures that might otherwise be difficult to detect through manual analysis alone.

The methodology is developed and demonstrated through an analysis of Greek parliamentary discourse surrounding the 2023 Tempi railway disaster. Using a corpus of 216,396 parliamentary paragraphs, CART combines paragraph-level thematic filtering, LLM-assisted narrative extraction, and narrative-level clustering to identify recurring political narratives concerning the disaster, institutional responsibility, accountability, and railway safety.

The resulting taxonomy comprises ten political narrative families, providing a structured representation of the dominant narrative patterns emerging from parliamentary debates and enabling their subsequent comparative and temporal analysis.

This repository provides the analytical notebooks, datasets, intermediate outputs, original LLM prompts, and visualizations documenting the complete research workflow.

## Research Pipeline

CART employs a three-stage workflow that progressively transforms unstructured parliamentary discourse into an interpretable taxonomy of recurring political narratives.

The first stage identifies thematically relevant paragraphs through semantic representations, clustering, and confidence-based screening. The second stage employs DeepSeek-R1 to extract narrative statements from the selected material. Finally, the extracted statements are semantically grouped into recurring narrative families through narrative-level clustering.

![CART Research Pipeline](figs/pipeline.png)

## Repository Structure

The CART repository contains the computational framework, datasets, narrative taxonomy, human annotation materials, and supporting documentation associated with the research.

```text
cart/
├── framework/
│   ├── 00_dataset_integrity_check.ipynb
│   ├── 1_preperation.ipynb
│   ├── 2_screening_extraction.ipynb
│   └── 03_narrative_clustering.ipynb
│
├── dataset/
│   ├── 1_preparation/
│   ├── 2_screening_extraction/
│   └── 3_narrative_taxonomy/
│
├── annotation/
│   ├── Guidelines.pdf
│   ├── annotation_sheet.xlsx
│   ├── narratives_clean.xlsx
│   ├── annotations/
│   └── analysis/
│
├── taxonomy/
│   └── narrative_taxonomy_ksil.csv
│
├── prompts_used/
│   ├── 02_cluster_titles_prompt.txt
│   ├── 02_narrative_extraction_prompt.txt
│   └── 02_narrative_extraction_retry_prompt.txt
│
├── figs/
│   ├── pipeline.png
│   ├── evolution.png
│   └── activity.pdf
│
├── LICENSE
└── README.md
```

The repository is organized into six main directories:

- **`framework/`** contains the Jupyter notebooks implementing the computational workflow, including dataset integrity checks, corpus preparation, thematic screening, LLM-assisted narrative extraction, and narrative clustering.
- **`dataset/`** contains the original parliamentary corpus, preprocessed datasets, semantic embeddings, intermediate analytical outputs, and final narrative taxonomy.
- **`annotation/`** provides the materials associated with the human annotation study, including annotation guidelines, annotation spreadsheets, and notebooks for analyzing annotation results.
- **`taxonomy/`** provides the resulting narrative taxonomy as a standalone CSV file.
- **`prompts_used/`** contains the original prompts employed for LLM-generated cluster titles and narrative extraction, including the retry procedure.
- **`figs/`** contains visualizations of the research pipeline, parliamentary activity, and the temporal evolution of narrative families.

The following sections describe the analytical notebooks and document how the published datasets connect the successive stages of the CART workflow.
