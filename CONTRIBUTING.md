# Contributing

Thanks for helping keep this list useful. Quality over quantity: every entry should save a defender time.

## Adding a resource

1. Put it in the right section, in this format:
   ```
   - [Name](https://link) - What it does, in one sentence.
   ```
2. The description starts with a capital letter and ends with a period.
3. Link to the canonical source (official repo, paper on arXiv, vendor advisory), not to a re-post.
4. One resource per pull request, with a short note on why it belongs here.

## Adding an incident

Add a row to **Incident Timeline** with:

| Field | Rule |
|-------|------|
| Date | `YYYY-MM-DD` if known, otherwise `YYYY-MM` or `YYYY`. Never guess a day. |
| Incident | One line, factual, no speculation. |
| Class | Use an existing class where possible (Prompt injection, LLMjacking, MCP tool poisoning, ...). |
| Source | A primary or reputable secondary source. Vendor advisories and original research preferred. |

## What doesn't belong

- Tools without a public repo or documentation
- Marketing pages without technical content
- Offensive tooling with no defensive or research value
- Unverified claims or incidents sourced only from social media

## Corrections

Spotted a dead link, a wrong date or an incident whose scope changed? Open an issue or a PR. Corrections are always welcome.
