# Aleksandr Litvinenko

**AI Product Manager · AI × 1C · Bitrix24 · open source**

[Русский](README.md) · **English**

I test ways to connect AI agents to 1C:Enterprise and Bitrix24 and publish what works, along with where it stops working. I also build small services around 1C and a few websites; most of them run on product1c.ru.

[![AI × 1C Guide](https://img.shields.io/badge/guide-AI%20×%201C-0d7d7d)](https://github.com/Aleksandr-Litvinenko/1c-ai-guide)
[![Telegram](https://img.shields.io/badge/Telegram-@DED__GENA-26A5E4?logo=telegram&logoColor=white)](https://t.me/DED_GENA)

> 1C:Enterprise is an ERP and business-application platform used across Russia and the CIS. Its ecosystem documentation is mostly in Russian, so my 1C projects are Russian-first, with English versions where they help.

---

## AI × 1C Guide

[**AI × 1C Guide**](https://github.com/Aleksandr-Litvinenko/1c-ai-guide/blob/main/README.en.md) answers one question: which methods connect an AI agent to 1C:Enterprise and Bitrix24, what each one gives you, and where it gets dangerous.

The catalog covers 14 ecosystem projects. Each entry records a pinned commit, license, prerequisites, access surface, and known write operations, plus what was checked: documentation, a release artifact, a local CLI smoke test, or a live endpoint.

Four connections are documented step by step:

| Connection | What is verified | Guide |
|---|---|---|
| **OData in 1C:Fresh** | A private live GET against 1C:UNF: `$metadata`, document listing, read by `Ref_Key`. Creating an unposted document is implemented in working code | [Read and test-write](https://github.com/Aleksandr-Litvinenko/1c-ai-guide/blob/main/guides/1cfresh-odata.en.md) |
| **Bitrix24 tasks** | A working runtime in `task2bitrix24`: `tasks.task.list`, results, logged time, users, related CRM objects, pagination and `batch` | [List tasks and read one by ID](https://github.com/Aleksandr-Litvinenko/1c-ai-guide/blob/main/guides/bitrix24-tasks.en.md) |
| **Bitrix24 leads** | A private `crm.lead.add` with a verification read of the stored fields; the current example moved to the universal `crm.item.add` | [Backend webhook and lead creation](https://github.com/Aleksandr-Litvinenko/1c-ai-guide/blob/main/guides/bitrix24-leads.en.md) |
| **1C-Connect + Jira + Bitrix24** | The Jira half verified with live anonymous calls to the Apache Software Foundation's public Jira, repeatable without an account. The 1C-Connect SOAP API documented from the official reference | [Reconciling three systems](https://github.com/Aleksandr-Litvinenko/1c-ai-guide/blob/main/guides/connect-jira-bitrix24.en.md) |

The Python examples are safe by default: read commands cannot call write methods, sensitive output is redacted, and writes are bound to a fingerprint of one specific endpoint. Secrets stay in the local environment and never reach a prompt.

The registry still needs end-to-end results on Windows and Linux against a real test 1C database, negative tests for denied operations, exact platform versions, and license and authentication details. If you can help, start with [CONTRIBUTING](https://github.com/Aleksandr-Litvinenko/1c-ai-guide/blob/main/CONTRIBUTING.md).

---

## Services

| Project | What it does | Stack |
|---|---|---|
| [**1cProductMap**](https://github.com/Aleksandr-Litvinenko/1cProductMap) · [map.product1c.ru](https://map.product1c.ru/) | A map of the 1C product line: pick by task and company size, price a bundle from the official price list, send the request straight to Bitrix24 | Python · JSON Schema |
| [**ProjectControl**](https://github.com/Aleksandr-Litvinenko/ProjectControl) · [projectcrm.ru](https://projectcrm.ru/) | A PMO workspace: project portfolio, mandatory checklists, Gantt chart, team capacity | TypeScript · React · PostgreSQL · Docker |
| [**task2bitrix24**](https://github.com/Aleksandr-Litvinenko/task2bitrix24) | A panel on top of Bitrix24 and 1C:UNF: closed-hours reports in Excel, task checks before invoicing, KPIs, one-click UNF documents | PHP · Bitrix24 REST · OData |
| [**Ondal**](https://github.com/Aleksandr-Litvinenko/ondal) · [demo](https://ondal.product1c.ru) | Management accounting: invoices with approvals, inventory, P&L, cash flow, payment calendar, and export to 1C over OData | TypeScript · React · PostgreSQL |
| [**Ladno**](https://github.com/Aleksandr-Litvinenko/ladno) · [demo](https://ladno.product1c.ru) | An accounting demo that runs entirely in the browser: invoices, inventory, P&L, payment calendar | Dependency-free JavaScript |
| [**education1c**](https://github.com/Aleksandr-Litvinenko/education1c) · [edu.product1c.ru](https://edu.product1c.ru/) | An onboarding curriculum for 1C interns and sales managers, not launched yet | HTML · CSS · Learning design |

## Websites

Sites built around WebGL graphics. The code is private; each repository explains how the site was made and how it was checked.

- [**Product1C**](https://github.com/Aleksandr-Litvinenko/beautydesign) · [beautydesign.product1c.ru](https://beautydesign.product1c.ru): the studio site, with a chrome object and a depth effect.
- [**Product1C 3D**](https://github.com/Aleksandr-Litvinenko/product1c-new) · [new.product1c.ru](https://new.product1c.ru/): a single Three.js particle scene that moves through five shapes as you scroll.
- [**cBrain**](https://github.com/Aleksandr-Litvinenko/cbrain) · [cbrain.product1c.ru](https://cbrain.product1c.ru): a swarm of 110,000 particles in plain WebGL2 that rebuilds itself on scroll.

## Agent skills in Russian

- [**agent-skills-ru**](https://github.com/Aleksandr-Litvinenko/agent-skills-ru) · [claude.product1c.ru](https://claude.product1c.ru): a translation of Addy Osmani's agent-skills, 24 skills from spec to release. The site lets you search them and build your own set.
- [**ladny-interface**](https://github.com/Aleksandr-Litvinenko/ladny-interface): an adaptation of Emil Kowalski's design-engineering skills, with an example interface for 1C.

## AI code-generation experiments

Prototypes written end to end by AI tools. I don't present them as products: they exist to compare Claude Code, Codex, and Qwen on identical tasks, which is why some of them come in pairs.

- **Crown Defender TD**, a 3D tower defense: [Claude Code version](https://github.com/Aleksandr-Litvinenko/Claude-code.-Crown-Defender-TD-3D-browser-tower-defense-game) and [Codex version](https://github.com/Aleksandr-Litvinenko/Codex.-Crown-Defender-TD-3D-browser-tower-defense-game).
- **AI Project Executor**, scheduled project documents: [Claude Code implementation](https://github.com/Aleksandr-Litvinenko/Claude_code.-project-crm) and [Codex specification](https://github.com/Aleksandr-Litvinenko/Codex.-project-crm).
- **Browser arcades**: [GamesIO](https://github.com/Aleksandr-Litvinenko/GamesIO) with ten games and [GeneratedGamesIO](https://github.com/Aleksandr-Litvinenko/GeneratedGamesIO) with eight phone games.
- [**NEUROCORP**](https://github.com/Aleksandr-Litvinenko/neuro_company_claude): a company staffed by AI agents where a human only approves the project and the quote.
- [**Mini Moba**](https://github.com/Aleksandr-Litvinenko/mini_mobile): a Unity MOBA, 1v1 online or against a bot.
- [**Outpost Siege**](https://github.com/Aleksandr-Litvinenko/OutpostSiegeTD): a plain-JS tower defense with 20 sieges of 20 waves.

---

## How I work

- I figure out the business problem first and pick the model later.
- By default the agent gets read-only access, and a human approves every write.
- I keep verified facts apart from experiments and assumptions in the text.
- I don't call anything safe until a negative test proves the denial.
- I publish documentation with the code and limitations with the result.

## Topics

**1C:** 1C:Enterprise 8.3, 1C:Fresh, 1C:UNF, the standard OData interface, HTTP services, BSL, 1C:EDT, configuration export.

**Bitrix24:** REST API, incoming webhooks, tasks, CRM and leads, `batch`, rate limits.

**AI:** MCP (Model Context Protocol), Agent Skills, Claude Code, Codex, Cursor, function calling, RAG, AI-assisted development.

**Product:** product management, business-process audits, operational dashboards, learning products for 1C teams.

**Web:** React, Three.js and WebGL, static sites behind nginx, release-based deploys with rollback.

## Contact

- Telegram: [@DED_GENA](https://t.me/DED_GENA)
- Project questions: open an issue in the relevant repository
