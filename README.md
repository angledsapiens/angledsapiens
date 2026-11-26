## Angled Sapiens

I build tools that catch what breaks quietly in AI systems: retired models, swapped models and changed behaviour.

## modelshift: know what breaks before your LLM is switched off

[![npm](https://img.shields.io/npm/v/modelshift)](https://www.npmjs.com/package/modelshift) [![ci](https://github.com/angledsapiens/modelshift/actions/workflows/ci.yml/badge.svg)](https://github.com/angledsapiens/modelshift/actions/workflows/ci.yml) [![license: MIT](https://img.shields.io/badge/license-MIT-blue)](https://github.com/angledsapiens/modelshift/blob/master/LICENSE)

Model providers retire models on a schedule, and inference hosts sometimes remove or swap them with no notice. [**modelshift**](https://github.com/angledsapiens/modelshift) finds every model your code uses, tells you which are retiring, gone or silently served as something else, and tests the replacement on your own requests before you switch.

```bash
npx modelshift scan     # which models in this repo are retiring? no API key needed
```

- **Honest statistics:** it measures how much the old model disagrees with itself first, and only flags changes bigger than that.
- **Nothing hidden:** failed calls, skipped checks and settings the new model rejected are listed at the top of every report.
- **Local and vendor-neutral:** your keys, your machine; OpenAI, Anthropic, Gemini, Azure, Bedrock, Mistral, DeepInfra, Together, Fireworks, Groq and OpenRouter.
- **Works in CI:** a GitHub Action for pull-request gates and a daily retirement watch.

**Real example:** testing GPT-4o mini against its replacement, GPT-6 Luna, found three request settings that now fail, empty answers at small token limits, and replies that stay correct but read differently. [See the report →](https://github.com/angledsapiens/modelshift/tree/master/examples/gpt-4o-migration)

## Other projects

- [**watchmen**](https://github.com/angledsapiens/watchmen): agentic low-latency awareness system for financial legos
- [**Agentic-Economy**](https://github.com/angledsapiens/Agentic-Economy): agent-to-agent (A2A) autonomous payments
- [**modulus**](https://github.com/angledsapiens/modulus): measures how on-chain systems behave under state change

---

Found a model retirement modelshift is missing? [Report it](https://github.com/angledsapiens/modelshift/issues/new?template=retirement.yml). Every entry needs an official source.
