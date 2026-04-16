# Switchy

**The memory layer for multi-model AI.**

One persistent, shared memory across every model, agent, and session. Drop-in API. Works with 450+ models via OpenRouter, or bring your own key.

→ [switchy.build](https://switchy.build)  ·  [Docs](https://switchy.build/docs)  ·  [Blog](https://switchy.build/blog)  ·  [@switchy_ai](https://x.com/switchy_ai)

---

## Why Switchy

Every serious AI product now runs multiple models — a reasoning model, a code model, an image model, embeddings. None of them share state. Teams end up rebuilding memory from scratch inside every product, and usually doing it badly.

Switchy is memory as infrastructure. Four composable layers, one namespaced API, and an adaptation layer that translates context between modalities so text models and image models can finally share the same memory.

### The four layers

- **Working memory** — session-scoped state with frame-based summaries
- **Episodic memory** — persistent session recall, scored by recency, relevance, and importance, with decay
- **Semantic memory** — LLM-extracted facts, preferences, and decisions, deduplicated and confidence-tracked
- **Knowledge graph** — typed entities and relations, resolved across sessions

All four run in parallel on retrieval, token-budgeted per model.

---

## Open source

Public repositories in this org:

- **[awesome-ai-memory](https://github.com/Switchy-AI/awesome-ai-memory)** — curated list of memory tools, papers, and patterns for AI systems
- **[switchy-examples](https://github.com/Switchy-AI/switchy-examples)** — copy-pasteable integration examples for LangChain, LlamaIndex, Vercel AI SDK, CrewAI, and more
- **[memory-bench](https://github.com/Switchy-AI/memory-bench)** — open benchmark for agent memory systems, with reproducible scores

More coming. Contributions welcome.

---

## Integrations

Switchy works everywhere your models do:

- LangChain  ·  LlamaIndex  ·  Vercel AI SDK  ·  CrewAI  ·  OpenPipe
- OpenAI  ·  Anthropic  ·  Google  ·  Mistral  ·  Llama  ·  450+ models via OpenRouter

Bring your own OpenRouter key and pay nothing to us for model calls — we only charge for the memory layer.

---

## Get started

1. Sign up at [switchy.build](https://switchy.build) — free tier, no card
2. Grab your API key from the dashboard
3. `npm install @switchy/sdk` or `pip install switchy`

```ts
import { Switchy } from '@switchy/sdk';

const memory = new Switchy({ apiKey: process.env.SWITCHY_API_KEY }).memory;

await memory.write({ namespace: 'user_123', content: 'I prefer TypeScript over Python' });
const context = await memory.buildContext({ namespace: 'user_123', query: 'help me write a function', modelType: 'chat' });
```

---

## Community

- [@switchy_ai](https://x.com/switchy_ai) on X
- [Switchy on LinkedIn](https://www.linkedin.com/company/switchy-ai)
- [Dev.to](https://dev.to/switchy)
- [Newsletter](https://switchy.build/newsletter) — weekly posts on AI memory, agent architecture, and lessons from building infrastructure in public

---

*Switchy is a small team building memory infrastructure for AI. We ship in public, write honestly, and care about the craft.*
