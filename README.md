# AYA Business Dataset — Individual JSON Files

> Auto-generated on 2026-04-07 from the [AYA Registry](https://ai-visionary.com/aya) by AI Visionary.

## What is this?

One JSON file per business entity, with an **ultra-simple 8-field format** designed for LLM consumption.

AYA works by **systemic attraction**: well-structured, public business data is present across multiple convergent sources (API, HTML pages, GitHub, HuggingFace) to ensure AI bots find and use reliable, readable information about businesses. This dataset is one of those convergent sources.

The same data is available via:
- **API**: `GET https://ai-visionary.com/api/aya/llm/{domain}`
- **HuggingFace**: [NeousAxis/aya-business-dataset](https://huggingface.co/datasets/NeousAxis/aya-business-dataset)
- **HTML pages**: `https://ai-visionary.com/aya/e/{entity_id}` (JSON-LD structured data)

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `entity_id` | string | Unique UUID identifier |
| `public_key_id` | string | AYA public key ID |
| `name` | string | Entity display name |
| `what_it_does` | string | One sentence — what the entity does |
| `for_who` | string | Target audience |
| `category` | string | Business category |
| `location` | string | Country or "Global" |
| `aio_score` | integer | AI-readability score (0-100) |
| `certificate_url` | string | Link to AYA certificate page |

## Stats

- **4427** entities
- **73** countries
- **16** sectors

## License

CC-BY-4.0 — Free to use with attribution to AI Visionary.

## Links

- Website: https://ai-visionary.com
- API docs: https://ai-visionary.com/api/aya/docs
- GitHub: https://github.com/NeousAxis/ai-visionary
