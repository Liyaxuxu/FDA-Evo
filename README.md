# FDA-Evo

FDA-Evo contains **60 FDA food-safety events, 304 stages, and 3,318 source blocks**. It provides frozen source text and reference annotations for studying how food-safety information changes over time.

The dataset supports research on cumulative information extraction from evolving FDA investigation records.

## Contents

| Path | Description |
|---|---|
| `data/sources/frozen/` | Frozen FDA page text |
| `data/sources/staged/` | Source blocks arranged by update stage |
| `data/gold/cases/` | Six-variable annotations with supporting evidence IDs |
| `data/gold/targeted_v4_gold.json` | Three-variable reference used in the main experiment |
| `data/gold/GOLD_FREEZE_2026-10-18.txt` | Reference freeze record |
| `data/manifest.json` | Source URLs, file paths, and source hashes |
| `data/cases.csv` | Case inventory |
| `data/stages.csv` | Stage inventory |
| `data/statistics.json` | Dataset statistics |

## Annotations

The full annotations cover case counts, hospitalisations, deaths, recall status, implicated products, and recalled products.

The main reference contains only:

- `recall_status`: YES or NO.
- `implicated_product`: a list of product names.
- `recalled_product`: records containing product name, recalling company, brands, and recall scope.

Count variables belong to a preliminary experiment. Across all stages, the main reference contains **627 implicated-product occurrences** and **1,149 recalled-product records**.

## Using the data

At stage Rk, use source blocks from **R1 through Rk only**. Each reference answer describes the cumulative state at that stage, not just newly reported information. Evidence IDs link annotations to blocks within the same case.

Use `data/manifest.json` to locate source files and their original FDA URLs. Some staged files retain historical workspace paths.

Stages were reconstructed from archived pages rather than separately captured historical snapshots. The dataset is a research resource, not current recall guidance. No official train/dev/test split is provided.

## Version and citation

This is **version 1.0.0**, released on 14 November 2026. For a fixed snapshot,
use [the v1.0.0 tag](https://github.com/Liyaxuxu/FDA-Evo/tree/v1.0.0).

Xu, L. (2026). *FDA-Evo* (Version 1.0.0) [Data set]. GitHub.
https://github.com/Liyaxuxu/FDA-Evo/tree/v1.0.0

Machine-readable citation metadata is provided in `CITATION.cff`.

## Reuse terms

This version does not specify a dataset-wide reuse license. Original FDA
source materials and author-created annotations are distinct components;
do not assume that the source material's terms also license the annotations.
See `RIGHTS.md` for the current licensing status.
