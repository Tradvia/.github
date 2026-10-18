<p align="center"><img src="https://raw.githubusercontent.com/tradvia/tradvia-web/main/logo.svg" width="96" alt="Tradvia"></p>

# Tradvia — Multi-Agent Orchestration for Project Execution

> **An early-stage open-core platform where AI agents and people execute the same project, with progress visible as Kanban, Gantt, Burndown, WBS, calendar and capacity — natively or inside the tools teams already use.**
> 🌐 [tradvia.org](https://tradvia.org) · 📫 Security & partnerships: `security@tradvia.org`

> [!NOTE]
> **Status: early stage, building in public.** Below, every capability is marked as **Shipped**, **In progress** or **Planned**, so you can see exactly what exists in code today.

---

## 🚀 Why Tradvia?

Projects slip less from a lack of skill than from **coordination friction**: status scattered across tools, decisions waiting in chat, and stakeholders who each need to see progress differently.

Tradvia orchestrates AI agents and human members on one shared set of work items. Every action is transparent in the notation each audience needs — the team's Kanban, the project manager's Gantt, the Scrum Master's burndown, the sponsor's WBS — and when an agent hits a decision that belongs to a person, it stops and asks in the chat you already use.

## 📊 Progress views

| Notation | Answers |
|---|---|
| **Kanban** | Where is each item in the workflow right now? |
| **Gantt** | How long does each item take, what depends on what, which milestone is at risk? |
| **Scrum / Burndown** | Will the sprint scope be delivered in time? |
| **WBS / EAP** | How does the scope break down into deliverables? |
| **Calendar / Timeline** | What is due on which date? |
| **Workload / Capacity** | Who — person or agent — is over- or under-allocated? |

## 🧱 Architecture & status

| Capability | Status |
|---|---|
| **Work-item lifecycle** — 5 statuses (`BACKLOG`, `AGENT_WORKING`, `WAITING_HUMAN`, `IN_REVIEW_PR`, `DONE`) with enforced transitions | ✅ Shipped |
| **Neutral work model + six views** — hierarchy, dates, dependencies, sprints, estimates; Kanban, Gantt, Burndown, WBS, calendar and capacity as tested projections | 🔨 In progress ([PR #2](https://github.com/tradvia/tradvia/pull/2)) |
| **Human-in-the-loop orchestrator** — LangGraph flow that pauses (`interrupt`), asks in Discord and opens a pull request only after approval | 🔨 In progress ([PR #1](https://github.com/tradvia/tradvia/pull/1)) |
| **Model routing** — LiteLLM in front of every model call, cost recorded on each work item | 🔨 In progress (PR #1) |
| **Web views** — the six notations rendered in the browser | 🗓️ Planned · v0.2 |
| **Connectors** — Trello, Jira, ClickUp, Monday.com, Asana, Wrike, Smartsheet, Artia, Microsoft Planner, KanbanFlow, Airtable (one shared interface) | 🗓️ Planned · v0.2+ |
| **Native MCP servers** — GitHub, project tools and chat through Model Context Protocol | 🗓️ Planned · v0.2+ |
| **Zero-trust multi-tenancy** — PostgreSQL Row-Level Security, Firecracker microVM per task | 🗓️ Planned · v0.2+ |
| **Token FinOps ledger** — budgets and circuit breakers per work item and sprint | 🗓️ Planned · v0.2+ |

## 🗺️ Roadmap (dogfooding: the machine building the machine)

- [x] **Phase 0 — Foundation:** open-core repository (`core/` FSL, `ee/` commercial), CLA, governance, CI and the work-item lifecycle contract.
- [ ] **Phase 1 — Engine v0.1:** LangGraph orchestrator, the neutral work model with its six views, LiteLLM routing, GitHub integration and human approval in chat. *(in progress)*
- [ ] **Phase 2 — Web views and first connectors:** the six views in the browser plus Jira and Trello, built in public by v0.1 agents.
- [ ] **Phase 3 — Enterprise:** SSO/RBAC, WhatsApp and Teams, portfolio and ROI dashboards, the remaining connectors.

## 🤝 Call for contributors

We are looking for early contributors in **LangGraph, project-tool connectors, MCP servers, data visualization and AI security**. Connectors are a great first contribution: each one implements the same `TrackerConnector` interface. Start with [CONTRIBUTING.md](https://github.com/tradvia/tradvia/blob/main/CONTRIBUTING.md), or reach Founder & Chief Architect **Anderson dos Santos Dutra** at `security@tradvia.org`.

<sub>Tradvia's core is fair source under FSL-1.1-ALv2 (each release becomes Apache 2.0 after two years).</sub>
