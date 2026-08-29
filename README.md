# AYA Business Dataset

Open data on **367,013 businesses** worldwide, each scored for AI readability
(AIO score 0-100) by the [AYA Registry](https://ai-visionary.xyz/aya), operated by
[AI Visionary](https://ai-visionary.xyz) from Geneva, Switzerland.

Snapshot of 29 August 2026. 9 entities are ASR-certified, 207 countries are represented.

## Files

| File | Format | Contents |
|------|--------|----------|
| `aya_business_dataset.csv.gz` | gzipped CSV | 10 flat columns, one row per entity |
| `aya_business_dataset.jsonl.gz` | gzipped JSONL | the CSV columns plus `entity_id`, `legal_name`, `description`, `data_origin`, `keywords`, `services`, `aio_blocks` |

Both files are gzipped because GitHub refuses any file above 100 MB and the raw
JSONL is around 222 MB. Decompress with `gunzip`, or read them directly:

```python
import pandas as pd

df = pd.read_csv("aya_business_dataset.csv.gz")                      # pandas handles .gz natively
rich = pd.read_json("aya_business_dataset.jsonl.gz", lines=True)
```

> **Note on the format.** Until August 2026 this repository held one JSON file per
> entity. At 367 000 entities that layout reached 1.64 GB and made cloning
> impractical, so the dataset moved to flat files. The per-entity records remain in
> the git history, and every entity is still individually reachable through the API
> and its certificate page.

## Columns

| Field | Description |
|-------|-------------|
| `name` | Business display name |
| `website` | Primary website URL |
| `country` | ISO 2-letter country code |
| `sector` | Macro sector classification |
| `entity_type` | `company`, `association` or `public_body` |
| `aio_score` | AI-readability score, 0-100, over 7 weighted blocks |
| `certified` | Whether the entity holds a signed ASR |
| `keywords` | Semicolon-separated keywords extracted from the website |
| `url` | The entity's AYA certificate page |

JSONL adds `entity_id`, `legal_name`, `description`, `data_origin`
(`FUSION-WDC` and `FUSION-WDC-MIN3` for public directory ingestion, `AYA-BOT` for
crawling, `AYO-SCAN` and `AYO` for diagnostics), `keywords` as an array, `services`
and the per-block score breakdown `aio_blocks`.

## Other ways to reach the same data

- **Live API**, no auth: [`/api/aya/search`](https://ai-visionary.xyz/api/aya/search?q=stripe), [`/api/aya/entity/{domain}`](https://ai-visionary.xyz/api/aya/entity/stripe.com), [`/api/aya/llm/{domain}`](https://ai-visionary.xyz/api/aya/llm/stripe.com), [`/api/aya/stats`](https://ai-visionary.xyz/api/aya/stats)
- **Remote MCP connector** for AI agents, one URL and no key: `https://ai-visionary.xyz/agents/mcp` ([guide](https://ai-visionary.xyz/for-agents))
- **HuggingFace**, uncompressed and ML-ready: [NeousAxis/aya-business-dataset](https://huggingface.co/datasets/NeousAxis/aya-business-dataset)

## Data quality

- Entities scoring below 20 are excluded
- Adult-content entities are excluded from the public registry and from this dataset
- Contact emails are never published
- Countries are normalized to ISO 2-letter codes

## License

[CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/). Share and adapt freely,
with credit to AI Visionary and the AYA Registry.

Contact: hello@ai-visionary.xyz
