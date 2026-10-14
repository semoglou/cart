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

```text
cart/
│
├── framework/
│   ├── 00_dataset_integrity_check.ipynb
│   ├── 01_preparation.ipynb
│   ├── 02_screening_extraction.ipynb
│   └── 03_narrative_clustering.ipynb
│
├── dataset/
│   ├── 1_preparation/
│   │   ├── 01_paragraphs_clean.csv.zip
│   │   ├── 01_stopwords_all.txt
│   │   └── 05_Tempi_paragraphs_clean.csv.zip
│   │
│   ├── 2_screening_extraction/
│   │   ├── 02_cluster_metadata.csv
│   │   ├── 02_clusters_with_titles.csv
│   │   ├── 02_dataset_clustered.csv.zip
│   │   ├── 03_tempi_df_dataset.csv
│   │   ├── 04_tempi_df_R1_narratives.csv
│   │   ├── 05_tempi_df_R1_extra_narratives.csv
│   │   ├── 05_tempi_df_R1_invalid_jsons.csv
│   │   ├── 06_tempi_df_R1_final_narratives.csv
│   │   └── par_embeddings.npy
│   │
│   └── 3_narrative_taxonomy/
│       ├── narrative_embeddings.npy
│       └── narrative_taxonomy_ksil.csv
│
├── annotation/
│   ├── analysis/
│   │   ├── annotation_results_analysis.ipynb
│   │   └── error_analysis_similarity.ipynb
│   │
│   ├── annotations/
│   │   ├── annotation_1.xlsx
│   │   ├── annotation_2.xlsx
│   │   ├── annotation_3.xlsx
│   │   ├── annotation_4.xlsx
│   │   └── annotation_5.xlsx
│   │
│   ├── Guidelines.pdf
│   ├── annotation_sheet.xlsx
│   └── narratives_clean.xlsx
│
├── prompts_used/
│   ├── 02_cluster_titles_prompt.txt
│   ├── 02_narrative_extraction_prompt.txt
│   └── 02_narrative_extraction_retry_prompt.txt
│
└── taxonomy/
    └── narrative_taxonomy_ksil.csv
```
