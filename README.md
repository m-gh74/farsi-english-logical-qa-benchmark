# Wikidata-Grounded Persian–English Benchmark for Entity-Set Question Answering

A bilingual Persian–English benchmark for Boolean compositional question answering over Iranian cultural, historical, geographical, artistic, and heritage domains. Each item is grounded in executable Wikidata/SPARQL structure and associated with language-independent Wikidata Q-ID answer sets for set-based evaluation of list-valued entity answers.

## Contents

| File | Rows | Description |
|---|---:|---|
| `data/mcq.csv` | 500 | Multiple-choice task instances. Each row contains Persian and English formulations of the same underlying logical query. |
| `data/open_ended.csv` | 500 | Open-ended task instances with full Wikidata Q-ID gold answer sets. Each row contains Persian and English formulations of the same underlying logical query. |


The benchmark contains 500 underlying logical queries. Each query is realized in two task formats—open-ended question answering (OEQ) and multiple-choice question answering (MCQ)—yielding 1,000 format-level task instances. Each format-level instance is provided in Persian and English, yielding 2,000 language-specific formulations. The queries span 12 domains and logical complexities from atomic facts (0 operators) to three-operator Boolean compositions.

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

## Contact
Morteza Ghorbaniparvariji — morteza.ghorbaniparvariji@studenti.unimi.it
