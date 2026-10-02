# Awesome EU LLM [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of European LLM inference providers, with their headquarters, their real hosting setup, and what their published sub-processor lists say about sovereignty.

"Hosted in the EU" and "European" are not the same thing. A provider can be headquartered in Paris and still depend on a US company for compute, or be a US company running a Frankfurt region. This list separates those cases by reading the providers' own sub-processor pages (DPA annexes, trust centers) instead of relying on marketing pages.

_Last verified: 2026-10-02. Sub-processor lists change often: always check the linked page before signing a DPA._

## Contents

- [Sovereignty tiers](#sovereignty-tiers)
- [Providers](#providers)
- [Routers and gateways](#routers-and-gateways)
- [EU-hosted, non-EU companies](#eu-hosted-non-eu-companies)
- [Outside Europe (reference)](#outside-europe-reference)
- [Provider notes](#provider-notes)
- [To document](#to-document)
- [Sources and credits](#sources-and-credits)

## Sovereignty tiers

| Tier | Meaning |
|---|---|
| 🟢 **SOV** | Company headquartered in the EU/EFTA, running on its own or EU-owned infrastructure. No non-EU company with operational access to customer content in the published sub-processor list. |
| 🟡 **C-EU** | Data is processed in the EU, but the company is non-EU, or a non-EU company (US cloud, US hardware operator, non-EU group entity) is a sub-processor with access to customer content. |
| 🔴 **XEU** | Company and/or processing outside Europe. |
| ⚪ **UNK** | Unknown: not enough public information (no sub-processor list, conflicting or missing hosting details). Treat as unverified until documented. |

Switzerland and the UK are not in the EU. Swiss providers are shown with `CH` and are 🟢 because they are EFTA and self-hosted, but note the different legal regime (Swiss law, not GDPR directly).

## Providers

**Sub-processors**: "Verified" (with a link) means we read the provider's own published sub-processor list. "Not verified" means we found no readable list: the tier is then based on provider claims only.

| Provider | HQ | Tier | Own infra | Sub-processors | Notes |
| --- | --- | --- | --- | --- | --- |
| [Scaleway AI](https://www.scaleway.com/en/generative-apis/) | 🇫🇷 FR | 🟢 SOV | Yes | [Verified](https://www.scaleway.com/en/subprocessorlist/) | Some colocation at US-headquartered operators (Equinix, Digital Realty). |
| [OVHcloud AI Endpoints](https://www.ovhcloud.com/en/public-cloud/ai-endpoints/) | 🇫🇷 FR | 🟢 SOV | Yes | [Verified](https://us.ovhcloud.com/legal/data-processing-agreement/) (DPA Annex III) | Group entities outside the EU; US SaaS vendors in the DPA annex. |
| [IONOS AI Model Hub](https://docs.ionos.com/cloud/ai/ai-model-hub/ai-model-hub) | 🇩🇪 DE | 🟢 SOV | Yes | Not verified | Processing in Germany, per docs. |
| [Infomaniak AI Tools](https://www.infomaniak.com/en/hosting/ai-tools) | 🇨🇭 CH | 🟢 SOV | Yes | Not verified | Own Swiss datacenters. |
| [AKI.IO](https://aki.io/) | 🇩🇪 DE | 🟢 SOV | Yes | Not verified | Own infrastructure. |
| [Entrim](https://entrim.ai/) | 🇸🇮 SI | 🟢 SOV | Yes | Not verified | Own datacenter in Slovenia. |
| [Berget AI](https://berget.ai/en) | 🇸🇪 SE | 🟢 SOV | Yes (affiliates) | [Verified](https://berget.ai/en/dpa) | Swedish affiliates only, plus Stripe for billing. |
| [Melious AI](https://melious.ai/) | 🇩🇪 DE | 🟢 SOV | Via EU providers | [Verified](https://melious.ai/legal/subprocessors) | All sub-processors EU-headquartered. Also a router. |
| [LLM Tech](https://llmtech.eu/) | 🇵🇱 PL | ⚪ UNK | Rented | Not verified | Single model. GPU location unclear (Seeweb IT or Verda FI). |
| [Inceptron](https://www.inceptron.io/) | 🇸🇪 SE | ⚪ UNK | Mixed | Not verified | Relies on unnamed third-party clouds. |
| [Arkane Cloud](https://arkanecloud.com/) | 🇫🇷 FR | ⚪ UNK | Yes (claimed) | Not verified | No legal pages or sub-processor list found. |
| [Mistral AI](https://mistral.ai/) | 🇫🇷 FR | 🟡 C-EU | Partly | [Verified](https://trust.mistral.ai/subprocessors) | US companies in the inference and cloud path (CoreWeave, Microsoft, Google). A US API endpoint exists. |
| [Infercom](https://infercom.ai/) | 🇱🇺 LU | 🟡 C-EU | Colocation | [Verified](https://infercom.ai/trust/) + [DPA](https://infercom.ai/dpa/) | Hardware operated with SambaNova (US), which has operational access. |
| [Nebius AI Studio](https://nebius.com/) | 🇳🇱 NL | 🟡 C-EU | Yes | [Verified](https://docs.nebius.com/legal/sub-processors) | US and Israeli group entities in the sub-processor list. Serverless endpoints now "Global". |
| [TensorX](https://tensorx.ai/) | 🇮🇪 IE / 🇬🇧 UK | 🟡 C-EU | Rented | [Verified](https://tensorx.ai/sub-processors/) | US sub-processors (AWS, Cloudflare, Google). UK or IE entity, unclear. |
| [Nscale](https://www.nscale.com/) | 🇬🇧 UK | 🟡 C-EU | Yes | [Verified](https://www.nscale.com/legal/sub-processors) | UK company. US SaaS stack. |

## Routers and gateways

A router sends your request to one of several underlying providers. Your sovereignty is the weakest of the hosts you allow.

| Router | HQ | Tier | Notes | Sub-processors |
| --- | --- | --- | --- | --- |
| [Cortecs](https://cortecs.ai/) | 🇦🇹 AT | 🟢 SOV | Routing hosted on OVH. Some selectable models run on US clouds (EU regions). | [Verified](https://cortecs.ai/dpa) |
| [Melious AI](https://melious.ai/) | 🇩🇪 DE | 🟢 SOV | 12 EU inference providers, EU hosting. | [Verified](https://melious.ai/legal/subprocessors) |
| [EUrouter](https://www.eurouter.ai/) | 🇳🇱 NL | 🟡 C-EU | Hosted on Scaleway. AWS and Microsoft selectable as model providers. | [Verified](https://www.eurouter.ai/dpa) |

## EU-hosted, non-EU companies

US (or other non-EU) companies offering EU regions. Data can stay in the EU, but the company remains subject to its home jurisdiction (for example the US CLOUD Act).

| Provider | HQ | Notes | Sub-processors |
| --- | --- | --- | --- |
| [AWS Bedrock](https://aws.amazon.com/bedrock/) | 🇺🇸 US | Claude and other models in EU regions. | Not verified |
| [Google Vertex AI](https://cloud.google.com/vertex-ai) | 🇺🇸 US | Gemini in EU datacenters. | Not verified |
| [Microsoft Foundry (Azure)](https://azure.microsoft.com/en-us/products/ai-foundry) | 🇺🇸 US | Azure OpenAI and others in EU regions. | Not verified |
| [DigitalOcean](https://www.digitalocean.com/) | 🇺🇸 US | EU compute available. | Not verified |

## Outside Europe (reference)

Included only for contrast: US companies whose default API processes data in the US. Check each provider's data residency options.

- [OpenAI](https://openai.com/), [Anthropic](https://www.anthropic.com/), [Together AI](https://www.together.ai/), [Groq](https://groq.com/)


## To document

Candidates not yet researched. PRs welcome.

- [STACKIT](https://stackit.com/) (DE), [Telekom / T-Systems AI Foundation Services](https://www.telekom.com/) (DE), [Aleph Alpha](https://aleph-alpha.com/) (DE)
- Listed as upstreams by EUrouter and Melious: GreenPT (NL), Lyceum Technology (DE), Nebul (NL), Regolo.ai / Seeweb (IT), DataCrunch / Verda (FI), weber.cloud (DE)
- [Exoscale](https://www.exoscale.com/) (CH/AT), [Outscale](https://outscale.com/) (FR)

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) to add or correct an entry.

## License

[CC0 1.0](LICENSE)
