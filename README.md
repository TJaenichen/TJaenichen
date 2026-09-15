# Thorsten Jaenichen

**Software architect and AI practice lead** in Montreal. 25+ years across .NET, C++, GPU and geospatial systems. The last three years went into one question: how does a small team ship at large-team scale when AI agents write most of the code, and how do you verify that output well enough to run it in production?

---

### Start here

| Project | What it is | Why it matters |
|---|---|---|
| [**Drawbridge**](https://github.com/TJaenichen/Drawbridge) | A declarative, secure MCP gateway. Exposes private-network APIs to cloud AI agents as typed, allowlisted tools. Auth is injected server-side, anything not declared is refused, every request is logged. | One spec, two implementations (TypeScript and C#), proven equivalent by a shared golden-fixture conformance suite. CI, mutation testing on both sides, a threat model, and a `proofs/` tree of re-runnable evidence per feature. |
| [**claude-code-harness**](https://github.com/TJaenichen/claude-code-harness) | The skills, agents, hooks and `CLAUDE.md` templates I run Claude Code with every day, generalized from a real .NET / Azure DevOps monorepo. | 27 skills, a five-reviewer PR panel with confidence scoring, a headless review prompt for a review service, and hooks that track sessions. The shape of AI-assisted engineering a team that reviews every PR can live with. |
| [**t2c-migration-presentation**](https://github.com/TJaenichen/t2c-migration-presentation) | A talk on migrating 1,500+ T-SQL stored procedures to C# with LLMs, at production scale. [Live slides](https://tjaenichen.github.io/t2c-migration-presentation/). | The pipeline, one-shot prompting with full context, generated tests, and Claude Code automation with a human gate. Written while doing it, not after. |

Also in production: a gradient-boosted model that picks the payment processor for each live credit-card transaction. Built from a standing start, measured lift in approval rate.

---

### Open source

- [**tghamm/Anthropic.SDK**](https://github.com/tghamm/Anthropic.SDK) (220+ stars): structured output support for the Microsoft.Extensions.AI `IChatClient`, so Claude works with Microsoft Agent Framework's `ResponseFormat`. [PR #180](https://github.com/tghamm/Anthropic.SDK/pull/180)
- [**CityGML2GameObject**](https://github.com/TJaenichen/CityGML2GameObject): runtime import of CityGML geospatial data into Unity.
- A decade of GPU ray tracing (NVIDIA OptiX), Unity, VR and IoT before that. Happy to talk about any of it.
-   
### Credentials

- **ISO/IEC 42001 Lead Implementer**, PECB, certified August 2026. AI management systems, meaning the governance side of putting agents into production.

### Stack

C# / .NET, Python, TypeScript, SQL Server, PostgreSQL (PostGIS, pgvector), Azure and Azure DevOps.
Claude Code, Model Context Protocol, Microsoft Agent Framework, Anthropic API.

---

[LinkedIn](https://www.linkedin.com/in/tjaenichen) · [jaenichen.ca](https://jaenichen.ca) · tjaenichen@gmail.com
