<p align="center"><img src="https://raw.githubusercontent.com/tradvia/tradvia-web/main/logo.svg" width="96" alt="Tradvia"></p>

# Tradvia — Open-Core AgentOps & Hybrid Execution Control Plane

> **Orchestrate humans, multi-model APIs and isolated container sessions in a single control plane.**
> 🌐 [tradvia.org](https://tradvia.org) · 📫 Security & partnerships: `security@tradvia.org`

> [!NOTE]
> **Status: early stage, building in public.** Every capability below is marked **Shipped**, **In progress**, **Partial** or **Planned**, so you can see exactly what exists in code today.

---

## 🚀 Why Tradvia?

Tradvia removes the coordination friction between project management and autonomous execution. Work is dispatched as cards on a hybrid Kanban, routed to multi-vendor LLM APIs or to stateful browser/CLI containers, tracked to the token and the compute second, and handed back and forth between AI agents and human engineers without losing context.

## 🧱 Architecture pillars

| Pillar | Status |
|---|---|
| **Dual-runtime execution** — stateless LLM APIs (OpenAI, Anthropic, Gemini, Ollama) plus stateful CLI/browser session workers (Playwright/CDP) with session mutex locks and persistent auth contexts | 🟦 Partial — APIs via LiteLLM ([PR #1](https://github.com/tradvia/tradvia/pull/1)) |
| **Multi-account pool & Token FinOps** — load spread within each account's RPM/TPM quota, cross-vendor fallback, cost per token or compute second, budget circuit breakers | 🟦 Partial — cost recorded per card |
| **Executable hybrid Kanban & Live Session Takeover** — every card is a durable state machine; humans take over a frozen browser/terminal (WebRTC/VNC), unblock it and hand control back | 🔨 In progress — state machine + approval in chat |
| **Zero-trust sandbox** — ephemeral Firecracker MicroVMs, PostgreSQL Row-Level Security, encrypted credential and session vaults | 🗓️ Planned · v0.2+ |
| **Native MCP & AST GraphRAG** — episodic knowledge distillation to cut token cost over time | 🗓️ Planned · v0.2+ |
| **Open-core monorepo** — self-hosted `/core` (Docker Compose); `/ee` + Cloud with team session pools, RBAC and FinOps governance | 🔨 In progress — monorepo, licenses, CI |

**Ground rules:** the account pool respects every vendor's rate limits and terms, and 2FA or CAPTCHA prompts are always resolved by a human through live takeover.

## 🗺️ Roadmap

- [x] **Phase 0 — Foundation:** open-core monorepo (`core/` FSL, `ee/` commercial), CLA, CI and the card state-machine contract.
- [ ] **Phase 1 — Engine v0.1:** LangGraph orchestrator, LiteLLM API runtime with cost per card, GitHub integration and approval gates in chat. *(in progress)*
- [ ] **Phase 2 — Session workers & takeover:** browser/CLI workers in Firecracker MicroVMs, live takeover over WebRTC, multi-account pool with budget breakers, MCP, Docker Compose self-hosting.
- [ ] **Phase 3 — Enterprise & Cloud:** team session pools, SSO/RBAC, WhatsApp and Teams, AST GraphRAG, FinOps governance and project-tool connectors.

## 🤝 Call for contributors

We are looking for early contributors in **LangGraph, Playwright/CDP session workers, Firecracker, MCP servers, FinOps and AI security**. Start with [CONTRIBUTING.md](https://github.com/tradvia/tradvia/blob/main/CONTRIBUTING.md), or reach Founder & Chief Architect **Anderson dos Santos Dutra** at `security@tradvia.org`.

<sub>Tradvia's core is fair source under FSL-1.1-ALv2 (each release becomes Apache 2.0 after two years).</sub>
