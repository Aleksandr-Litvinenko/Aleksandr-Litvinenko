# Aleksandr Litvinenko

**AI Product Manager · AI × 1C · Bitrix24 · open source**

[Русский](README.md) · **English**

I collect and verify the ways an AI agent can actually connect to 1C:Enterprise and Bitrix24, then publish what works — together with the boundaries of each claim.

[![AI × 1C Guide](https://img.shields.io/badge/guide-AI%20×%201C-0d7d7d)](https://github.com/Aleksandr-Litvinenko/1c-ai-guide)
[![Telegram](https://img.shields.io/badge/Telegram-@DED__GENA-26A5E4?logo=telegram&logoColor=white)](https://t.me/DED_GENA)

> 1C:Enterprise is an ERP and business-application platform used across Russia and the CIS. Its ecosystem documentation is mostly Russian-only, which is why my 1C projects are Russian-first with English versions where they help.

---

## Main project: an open registry of AI connections to 1C and Bitrix24

[**AI × 1C Guide**](https://github.com/Aleksandr-Litvinenko/1c-ai-guide/blob/main/README.en.md) is a guide and a machine-readable catalog answering one question: which methods actually connect an AI agent to 1C:Enterprise and Bitrix24, what each method gives you, and where it becomes dangerous.

The catalog holds 14 ecosystem projects. Each entry records a pinned commit, license, prerequisites, access surface, and known write operations — and states separately what was checked: documentation, a release artifact, a local CLI smoke test, or a live endpoint.

Three connections are documented from integrations in my own projects:

| Connection | What is verified | Guide |
|---|---|---|
| **OData in 1C:Fresh** | A private live GET against 1C:UNF: `$metadata`, document listing, read by `Ref_Key`. Creating an unposted document is implemented in working code | [Read and test-write](https://github.com/Aleksandr-Litvinenko/1c-ai-guide/blob/main/guides/1cfresh-odata.en.md) |
| **Bitrix24 tasks** | A working runtime in `task2bitrix24`: `tasks.task.list`, results, logged time, users, related CRM objects, pagination and `batch` | [List tasks and read one by ID](https://github.com/Aleksandr-Litvinenko/1c-ai-guide/blob/main/guides/bitrix24-tasks.en.md) |
| **Bitrix24 leads** | A private `crm.lead.add` with a verification read of the stored fields; the current example moved to the universal `crm.item.add` | [Backend webhook and lead creation](https://github.com/Aleksandr-Litvinenko/1c-ai-guide/blob/main/guides/bitrix24-leads.en.md) |

The Python examples are safe by default: read commands cannot call write methods, sensitive output is redacted, and writes are bound to a fingerprint of one specific endpoint. Secrets stay in the local environment and never reach a prompt.

**What the registry still needs:** end-to-end results on Windows and Linux against a real test 1C database, negative tests for denied operations, exact platform versions, and license and authentication details. Start with [CONTRIBUTING](https://github.com/Aleksandr-Litvinenko/1c-ai-guide/blob/main/CONTRIBUTING.md).

---

## Projects

| Project | What it solves | Stack |
|---|---|---|
| [**1c-ai-guide**](https://github.com/Aleksandr-Litvinenko/1c-ai-guide) | Tool selection and safer AI connection scenarios for 1C and Bitrix24 | Markdown · Python · GitHub Actions |
| [**task2bitrix24**](https://github.com/Aleksandr-Litvinenko/task2bitrix24) | Task-quality checks, closed-hours reports, and 1C:UNF workflows | PHP · Bitrix24 REST · OData |
| [**1cProductMap**](https://github.com/Aleksandr-Litvinenko/1cProductMap) · [map.product1c.ru](https://map.product1c.ru/) | Choosing 1C ecosystem products by task, company size, and budget | Python · JSON Schema |
| [**ProjectControl**](https://github.com/Aleksandr-Litvinenko/ProjectControl) · [projectcrm.ru](https://projectcrm.ru/) | A self-hosted workspace for project portfolio and PMO management | TypeScript · React · PostgreSQL · Docker |
| [**education1c**](https://github.com/Aleksandr-Litvinenko/education1c) · [edu.product1c.ru](https://edu.product1c.ru/) | An onboarding curriculum for 1C interns and sales managers | HTML · CSS · Learning design |

### AI code-generation experiments

A separate line of repositories holds prototypes built end to end by different AI tools: browser games, simulators, early CRM versions. They are labeled as experiments, and they exist to compare how Claude Code, Codex, and Qwen behave on identical tasks — not to pass a prototype off as a product.

### Open-source contributions

- [OpenIntegrations in Awesome 1C MCP Servers](https://github.com/Untru/1c-mcp/pull/5) — an industry catalog connecting the 1C integration library with the wider MCP ecosystem.

---

## How I work

- I start from the business problem, not the model name.
- Read-only access and explicit human approval are the default.
- I keep verified facts separate from experiments and assumptions, visibly, in the text.
- I do not call anything safe until the denial is proven by a negative test.
- I publish documentation alongside the code, and limitations alongside the result.

## Key topics

**1C:** 1C:Enterprise 8.3, 1C:Fresh, 1C:UNF, the standard OData interface, HTTP services, BSL, 1C:EDT, configuration export.

**Bitrix24:** REST API, incoming webhooks, tasks, CRM and leads, `batch`, rate limits.

**AI:** MCP (Model Context Protocol), Agent Skills, Claude Code, Codex, Cursor, function calling, RAG, AI-assisted development.

**Product:** product management, business-process audits, operational dashboards, learning products for 1C teams.

## Contact

- Telegram: [@DED_GENA](https://t.me/DED_GENA)
- Project questions: open an issue in the relevant repository
