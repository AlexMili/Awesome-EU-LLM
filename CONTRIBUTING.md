# Contributing to Awesome EU LLM

Thanks for helping keep this list accurate. Sovereignty claims are only useful if they can be checked, so every entry is tied to a public source.

## What belongs here

- LLM inference providers (API or hosted chat) and routers that offer European hosting or are European companies.
- A public website and, ideally, a public sub-processor list or DPA.
- No duplicates, no pure marketing descriptions.

## How an entry is structured

One row in the Providers table:

```markdown
| [Name](https://provider.example/) | 🇫🇷 FR | 🟢 SOV | Yes | [Verified](https://provider.example/subprocessors) | One or two factual sentences. |
```

| Column | What to fill in |
|---|---|
| **Provider** | Name linked to the product or home page. |
| **HQ** | Flag and ISO country of the legal entity that contracts with customers. |
| **Tier** | 🟢 SOV, 🟡 C-EU or 🔴 XEU, see [Sovereignty tiers](README.md#sovereignty-tiers). |
| **Own infra** | Yes, Rented, Colocation, Mixed. |
| **Sub-processors** | Link to the provider's list with `Verified`, or `Not found`. |
| **Notes** | Facts only: non-EU sub-processors, group entities outside the EU, caveats. |

## Rules for the tier

- Base it on the published sub-processor list, not on marketing copy.
- Name the non-EU sub-processor that justifies a 🟡 in the notes.
- If you disagree with another list (for example awesome-eu-infra), say why.
- If a page could not be read or is rendered by JavaScript, say so rather than guessing.

## Pull requests

- One provider per PR.
- Include the date you checked the sub-processor page.
- Keep the language neutral: no "best", no "unfortunately".
