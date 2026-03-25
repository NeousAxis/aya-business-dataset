# AYA Business Dataset — Individual JSON Files

> Auto-generated on 2026-03-25 from the [AYA Registry](https://ai-visionary.com/aya) by AI Visionary.

## What is this?

One JSON file per business entity, with an **ultra-simple 8-field format** designed for LLM consumption.
The same data is available via:
- **API**: `GET https://ai-visionary.com/api/aya/llm/{domain}`
- **HuggingFace**: [NeousAxis/aya-business-dataset](https://huggingface.co/datasets/NeousAxis/aya-business-dataset)

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `entity_id` | string | Unique UUID identifier |
| `name` | string | Entity display name |
| `what_it_does` | string | One sentence — what the entity does |
| `for_who` | string | Target audience |
| `category` | string | Business category |
| `location` | string | Country or "Global" |
| `aio_score` | integer | AI-readability score (0-100) |
| `certificate_url` | string | Link to AYA certificate page |

## Stats

- **3339** entities
- **71** countries
- **17** sectors

## License

CC-BY-4.0 — Free to use with attribution to AI Visionary.

## Links

- Website: https://ai-visionary.com
- API docs: https://ai-visionary.com/api/aya/docs
- GitHub: https://github.com/NeousAxis/ai-visionary
