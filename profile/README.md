<p align="center"><img src="https://raw.githubusercontent.com/tradvia/tradvia-web/main/logo.svg" width="96" alt="Tradvia"></p>

# Tradvia — Zero-Trust Multi-Agent Engineering Orchestration

> **An early-stage open-core control plane that puts AI agents on your team's Kanban board, with human approval gates and token cost tracking.**
> 🌐 [tradvia.org](https://tradvia.org) · 📫 Security & partnerships: `security@tradvia.org`

> [!NOTE]
> **Status: early stage, building in public.** Below, every capability is marked as **Shipped**, **In progress** or **Planned**, so you can see exactly what exists in code today.

---

## 🚀 Why Tradvia?

AI coding assistants made individual developers type faster, but teams still lose days to **coordination friction** across issue trackers, Git and chat (Slack, Teams, Discord, WhatsApp).

Tradvia puts specialized AI agents next to human engineers on one **hybrid Kanban board**. Agents plan and code; when they hit a decision that belongs to a human, they stop and ask in the chat you already use.

## 🧱 Architecture & status

| Capability | Status |
|---|---|
| **Card-state contract** — 5 statuses (`BACKLOG`, `AGENT_WORKING`, `WAITING_HUMAN`, `IN_REVIEW_PR`, `DONE`) with enforced transitions | ✅ Shipped |
| **Human-in-the-loop orchestrator** — LangGraph flow that pauses (`interrupt`), asks in Discord and opens a pull request only after approval | 🔨 In progress ([PR #1](https://github.com/tradvia/tradvia/pull/1)) |
| **Model routing** — LiteLLM in front of every model call, cost recorded on each card | 🔨 In progress (PR #1) |
| **GitHub integration** — via the GitHub REST API | 🔨 In progress (PR #1) |
| **Native MCP servers** — migrate GitHub, issue trackers and chat to Model Context Protocol | 🗓️ Planned · v0.2+ |
| **Zero-trust multi-tenancy** — PostgreSQL Row-Level Security, Firecracker microVM per task | 🗓️ Planned · v0.2+ |
| **Token FinOps ledger** — budgets and circuit breakers per card and sprint | 🗓️ Planned · v0.2+ |
| **Episodic knowledge distillation** — lessons from finished cards reused to cut future token cost | 🗓️ Planned · v0.2+ |

## 🗺️ Roadmap (dogfooding: the machine building the machine)

- [x] **Phase 0 — Foundation:** open-core repository (`core/` FSL, `ee/` commercial), CLA, governance, CI and the card-state contract.
- [ ] **Phase 1 — Headless engine v0.1:** LangGraph orchestrator + LiteLLM routing + GitHub integration + human approval in chat. *(in progress)*
- [ ] **Phase 2 — Dogfooding:** v0.1 agents build the v0.2 web Kanban (Next.js) in public.
- [ ] **Phase 3 — Enterprise:** SSO/RBAC, WhatsApp and Teams connectors, ROI dashboards.

## 🤝 Call for contributors

We are looking for early contributors in **LangGraph, MCP servers, sandboxing, Next.js and AI security**. Start with [CONTRIBUTING.md](https://github.com/tradvia/tradvia/blob/main/CONTRIBUTING.md), or reach Founder & Chief Architect **Anderson dos Santos Dutra** at `security@tradvia.org`.

<sub>Tradvia's core is fair source under FSL-1.1-ALv2 (each release becomes Apache 2.0 after two years).</sub>
