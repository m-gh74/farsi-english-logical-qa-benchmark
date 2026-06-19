# A Wikidata-Based Farsi–English Logical QA Benchmark

A bilingual (Farsi–English) benchmark for **compositional logical reasoning** in Large
Language Models, grounded in verified **Wikidata** relations and anchored in Iranian
cultural, historical, and geographical domains. Each natural-language question maps to a
formal Boolean logical expression (AND, OR, NOT) and a verifiable gold answer set anchored
to Wikidata Q-IDs.

This is the dataset accompanying the paper:

> Ghorbaniparvariji, M. & Raganato, A. *From Atomic to Compositional: A Wikidata-Based
> Farsi–English Logical QA Benchmark.* (Manuscript submitted to *Information Sciences*.)

## Contents

| File | Items | Description |
|------|-------|-------------|
| `data/mcq.csv` | 500 | Four-option multiple-choice questions (discriminative format) |
| `data/open_ended.csv` | 500 | Open-ended questions with full gold answer sets (generative format) |

**1,000 queries total**, spanning **12 domains** and logical depths from atomic facts
(0 operators) to three nested operators.

### `mcq.csv` columns
- `question_id` — unique id
- `question_fa` / `question_en` — the question (with options) in Farsi / English
- `gold_answer` — correct option label (A/B/C/D)
- `question_mode` — `MCQ`
- `sheet_name` — logical-depth category (e.g., `Atomic-MCQ`, `Single-op`, …)

### `open_ended.csv` columns
- `question_id` — unique id
- `domain` — one of 12 cultural/factual domains (e.g., `cinema`, `music`, …)
- `operator_types` — Boolean operators used (`ATOMIC`, `AND`, `OR`, `AND, OR`, `AND, NOT`, `AND, OR, NOT`)
- `num_logical_ops`, `reasoning_hops`, `operation_variety` — complexity metadata
- `logical_form` — symbolic logical form
- `question_fa` / `question_en` — the question in Farsi / English
- `template_fa` / `template_en` — the bilingual template the question was realized from
- `source` — knowledge source (`wikidata`)
- `sparql_query` — the executable SPARQL query used to derive the gold set
- `gold_wikidataids` — gold answer entities (Q-IDs)
- `gold_labels_en` / `gold_labels_fa` — gold entity labels
- `gold_display_label`, `answer_count` — display label and gold-set size
- `notes`, `sheet_name` — auxiliary fields

## License
The dataset is released under the **Creative Commons Attribution 4.0 International
(CC BY 4.0)** license — see `LICENSE`. You are free to share and adapt the data with
attribution.

## How to cite
If you use this benchmark, please cite the paper (see `CITATION.cff`).

## Contact
Morteza Ghorbaniparvariji — morteza.ghorbaniparvariji@studenti.unimi.it
