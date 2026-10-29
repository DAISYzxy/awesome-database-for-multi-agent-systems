# Contributing

Thank you for helping build the Database for Multi-Agent Systems reading list.

## Suggest a paper

Open an issue or submit a pull request with an entry under the relevant topic in [README.md](README.md#paper-list).

Include the paper title, a primary-source link, venue and year, and a classification from the [topic table](README.md#topic-taxonomy): **layer → data perspective → topic**. Briefly explain how the work uses database or data-system techniques to support multi-agent collaboration. Use an official publication page, DOI, or author-hosted preprint for the paper link. Identify preprints as such.

## Classification and tags

Use the layer and data perspective tags that match the mechanism described in each entry. The active list requires verified 2024–2026 ICDE, SIGMOD/PACMMOD or PVLDB publication, or the explicitly labeled CIDR extension; explicit collaborating LLM agents; and primary-source evidence for a data-system mechanism or dedicated MAS support vision. Distinguish implemented systems, visions, and specifically evaluated support components embedded in applications. Workshops, other venues, single-agent work, unverified records and merely transferable methods remain in the exclusion/discovery audit.

Do not infer MAS from multiple LLM calls, multiple pipeline candidates, multiple models, or inclusion in an awesome list. A data-task application qualifies only for an identifiable MAS support component, with evidence describing that component and its evaluation. Publication year and conference cycle must be recorded separately.

| Layer | Tag |
| --- | --- |
| Perception | `perception` |
| Planning | `planning` |
| Execution | `execution` |
| Action | `action` |
| Memory | `memory` |
| Data Interface | `data-interface` |
| Inference Infrastructure | `inference-infrastructure` |

| Data perspective | Tag |
| --- | --- |
| Data Management | `data-management` |
| Data Preparation | `data-preparation` |
| Data Analysis | `data-analysis` |

Place papers under the topics supported by primary-source evidence. Cross-layer works may appear in multiple layers or topics: explain the specific mechanism and evidence boundary in each entry, and provide source and PDF links. Count each publication only once in unique-paper totals; primary-layer labels in the review inventory are bookkeeping, not a restriction on display. Cells marked with an em dash (—) have no assigned topic in the current taxonomy; Perception is retained as an architecture layer with no topic entries yet.

Keep topic headings identical to those in the classification table. If proposing a taxonomy change, explain it separately and update the table and matching paper-list headings together.

## Entry format

```markdown
##### Exact topic heading from the classification table

- **[Paper Title](PAPER_URL)** - Venue, Year. `layer-tag` `perspective-tag`
  - Relevance: one sentence describing its contribution to DB for MAS.
  - [Code](CODE_URL)
```

Replace the example fields with verified metadata and omit the code link when unavailable. Add the entry beneath the existing heading without duplicating it. An optional short note may explain the collaboration mechanism or data-system technique studied in the paper.

## Corrections

Corrections to metadata, links, and layer assignments are welcome. Include the source or reasoning supporting the proposed change.
