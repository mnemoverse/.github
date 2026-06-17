<div align="center">
  <img src="../files/logo.png" alt="Mnemoverse" width="72"/>
  <h1>Mnemoverse</h1>
  <p><strong>One memory. Every AI tool.</strong></p>
  <p>Persistent memory infrastructure for AI agents — write once, recall anywhere.<br/>
  One API key; the same memory across Claude, ChatGPT, Cursor, VS Code, and any MCP client.</p>

  <p>
    <a href="https://mnemoverse.com/docs/"><img src="https://img.shields.io/badge/Docs-mnemoverse.com-1f6feb?style=flat-square" alt="Docs"/></a>
    <a href="https://console.mnemoverse.com"><img src="https://img.shields.io/badge/Console-sign%20up%20free-0aa?style=flat-square" alt="Console"/></a>
    <a href="https://www.npmjs.com/package/@mnemoverse/mcp-memory-server"><img src="https://img.shields.io/npm/v/@mnemoverse/mcp-memory-server?style=flat-square&label=npm&color=cb3837" alt="npm"/></a>
    <a href="https://pypi.org/project/mnemoverse/"><img src="https://img.shields.io/pypi/v/mnemoverse?style=flat-square&label=PyPI&color=3776ab" alt="PyPI"/></a>
    <a href="https://arxiv.org/abs/2603.08965"><img src="https://img.shields.io/badge/arXiv-2603.08965-b31b1b?style=flat-square" alt="arXiv"/></a>
  </p>
</div>

---

### Not a vector database

Mnemoverse stores preferences, decisions, lessons, and context — and serves them back to your agent in any tool. Memory that **learns** (Hebbian associations), **consolidates** (HDBSCAN, like sleep), and **improves with use** (outcome feedback) — not just similarity search.

```bash
# Claude Code — one command
claude mcp add mnemoverse -e MNEMOVERSE_API_KEY=mk_live_YOUR_KEY -- npx -y @mnemoverse/mcp-memory-server@latest

# Python
pip install mnemoverse
```

Free API key at **[console.mnemoverse.com](https://console.mnemoverse.com)** — no credit card, 1,000 queries/day.

### For AI agents

Point your agent at our machine-readable docs — API reference, per-tool setup, and pricing in one file ([llms.txt standard](https://llmstxt.org/)):

```
https://raw.githubusercontent.com/mnemoverse/.github/main/llms.txt
```

### Public repositories

| Repository | What it does |
|---|---|
| **[mcp-memory-server](https://github.com/mnemoverse/mcp-memory-server)** | MCP server for Claude Code, Cursor, VS Code, Windsurf — and any MCP client |
| **[mnemoverse-vscode](https://github.com/mnemoverse/mnemoverse-vscode)** | VS Code extension — persistent memory for AI coding assistants |
| **[mnemoverse (PyPI)](https://github.com/mnemoverse/mnemoverse-sdk-python)** | Python SDK — sync + async clients, retry & circuit breaker |
| **[mnemoverse-slod-paper](https://github.com/mnemoverse/mnemoverse-slod-paper)** | Code companion to the SLoD paper (arXiv:2603.08965) |

### Built on research

- **Semantic Level of Detail (SLoD)** — published on [arXiv:2603.08965](https://arxiv.org/abs/2603.08965)
- Benchmarked on public memory benchmarks — LoCoMo, LongMemEval, HotpotQA
- 7 provisional patents filed (INPI, 2026)
- NVIDIA Inception Program member

### Links

- **[Documentation](https://mnemoverse.com/docs/)** — guides, API reference, integration setup
- **[Console](https://console.mnemoverse.com)** — sign up, API keys, usage dashboard
- **[Research library](https://mnemoverse.com/docs/research/)** — the science behind the memory layer
- **[ChatGPT setup](https://mnemoverse.com/docs/api/chatgpt)** — Custom GPT with Actions

---

<div align="center">
  <sub><strong>Mnemoverse</strong> — persistent memory for AI agents · <a href="https://mnemoverse.com">mnemoverse.com</a></sub>
</div>
