# CART
### Clustering-based Analysis of Recurring narratives for Taxonomy construction

CART is a computational framework for identifying, extracting, and
organizing recurring political narratives in large collections of text.

The framework combines semantic text representations, clustering-based
thematic filtering, confidence-based screening, large language models
(LLMs), and narrative-level clustering to construct interpretable
taxonomies of political narratives.

This repository provides the implementation and research outputs of
CART's application to Greek parliamentary discourse concerning the
2023 Tempi railway disaster.

The analysis examines parliamentary debates from March 2023 onward,
focusing on how political actors construct, communicate, and reproduce
narratives surrounding the disaster, institutional responsibility,
accountability, and railway safety.

The repository includes the analytical notebooks, intermediate and
final datasets, original LLM prompts, and figures required to
understand the research workflow and reproduce the published
computational analyses using the provided checkpoints.

---

## Research Pipeline

CART follows a three-stage analytical workflow:

1. **Paragraph-Level Thematic Filtering:** Semantic embeddings,
   clustering, and confidence-based screening are used to identify
   parliamentary paragraphs relevant to the research topic.

2. **LLM-Assisted Narrative Extraction:** A large language model
   identifies and extracts political narrative statements from
   the selected parliamentary paragraphs.

3. **Narrative-Level Clustering:** Extracted narrative statements
   are represented semantically and grouped into recurring
   narrative families to construct a political narrative taxonomy.

![CART Research Pipeline](figs/pipeline.png)

*Figure 1. Overview of the CART framework, illustrating the three
analytical stages from parliamentary discourse to political
narrative taxonomy.*

### Application to Greek Parliamentary Discourse

The empirical application begins with a corpus of **216,396 parliamentary
paragraphs**.

Following corpus preparation and thematic filtering, **10,229
Tempi-related paragraphs** are selected for narrative extraction.

The LLM-assisted extraction stage produces **4,537 narrative
statements**, which are subsequently organized into **10 recurring
political narrative families**.

| Analytical stage | Output |
|---|---:|
| Original parliamentary corpus | 216,396 paragraphs |
| Cleaned parliamentary corpus | 117,716 paragraphs |
| Tempi-related sub-corpus | 10,229 paragraphs |
| Extracted narrative statements | 4,537 statements |
| Final political narrative taxonomy | 10 narrative families |

The following sections document the analytical notebooks, the
relationships between the published datasets, the methodological
choices underlying each stage, and the procedures for reproducing
the analysis.
