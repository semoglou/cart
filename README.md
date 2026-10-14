# CART
### Clustering-based Analysis of Recurring narratives for Taxonomy construction

CART is an unsupervised, clustering-based framework designed to identify,
extract, and organize recurring political narratives from large-scale
textual data without requiring predefined narrative categories or
extensively annotated training datasets.

Constructing a taxonomy of political narratives traditionally requires
substantial manual effort, including the identification of relevant
textual material, the interpretation of recurring narrative patterns,
and the development of a consistent classification scheme. These tasks
become increasingly challenging when analyzing large collections of
political discourse, where narratives may be expressed through diverse
linguistic formulations and evolve over time.

CART addresses these challenges by combining semantic embeddings,
ensemble clustering, confidence-based screening, and large language
models (LLMs) within a unified analytical workflow. Rather than
starting from a predetermined set of narrative labels, the framework
identifies recurring patterns in the data and progressively organizes
them into an interpretable narrative taxonomy.

The approach is designed to reduce the dependence on extensive manual
annotation, facilitate the exploration of large textual corpora, and
support the systematic identification of narrative structures that
might otherwise be difficult to detect through manual analysis alone.

The methodology is developed and demonstrated through an analysis of
Greek parliamentary discourse surrounding the 2023 Tempi railway
disaster. Using a corpus of 216,396 parliamentary paragraphs, CART
combines paragraph-level thematic filtering, LLM-assisted narrative
extraction, and narrative-level clustering to identify recurring
political narratives concerning the disaster, institutional
responsibility, accountability, and railway safety.

The resulting taxonomy comprises ten political narrative families,
providing a structured representation of the dominant narrative
patterns emerging from parliamentary debates and enabling their
subsequent comparative and temporal analysis.

This repository provides the analytical notebooks, datasets,
intermediate outputs, original LLM prompts, and visualizations
documenting the complete research workflow.
