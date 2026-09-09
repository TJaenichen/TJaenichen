# Thorsten Jaenichen

**Software architect and AI practice lead** in Montreal. 25+ years across .NET, C++, GPU and geospatial systems. The last three years went into one question: how does a small team ship at large-team scale when AI agents write most of the code, and how do you verify that output well enough to run it in production?

My answer is a harness. Specs go in, agents implement, and every change passes verification gates (differential tests against production traffic, mutation testing, multi-agent review panels) before a human signs off. Most of what follows is that harness, made public.

---

### Start here

| Project | What it is | Why it matters |
|---|---|---|
| [**Drawbridge**](https://github.com/TJaenichen/Drawbridge) | A declarative, secure MCP gateway. Exposes private-network APIs to cloud AI agents as typed, allowlisted tools. Auth is injected server-side, anything not declared is refused, every request is logged. | One spec, two implementations (TypeScript and C#), proven equivalent by a shared golden-fixture conformance suite. CI, mutation testing on both sides, a threat model, and a `proofs/` tree of re-runnable evidence per feature. |
| [**claude-code-harness**](https://github.com/TJaenichen/claude-code-harness) | The skills, agents, hooks and `CLAUDE.md` templates I run Claude Code with every day, generalized from a real .NET / Azure DevOps monorepo. | 27 skills, a five-reviewer PR panel with confidence scoring, a headless review prompt for a review service, and hooks that track sessions. The shape of AI-assisted engineering a team that reviews every PR can live with. |
| [**t2c-migration-presentation**](https://github.com/TJaenichen/t2c-migration-presentation) | A talk on migrating 1,500+ T-SQL stored procedures to C# with LLMs, at production scale. [Live slides](https://tjaenichen.github.io/t2c-migration-presentation/). | The pipeline, one-shot prompting with full context, generated tests, and Claude Code automation with a human gate. Written while doing it, not after. |

Also in production: a gradient-boosted model that picks the payment processor for each live credit-card transaction. Built from a standing start, measured lift in approval rate.

---

### Private repos, described

Most of my recent work is in private repos. What they are, so the public pieces have context:

- **grant-explorer**: matches Canadian businesses to government funding programs, with clause-level eligibility citations. Ingests the program documents, extracts each one's eligibility rules as a logical tree, and scores a business against them. Seven registered LLM agents (extraction, judge, adversarial verifier, interview, discovery, URL inference, adjudicator) sit behind one gateway with pinned prompts, per-agent budget rings and tripwire tests. The corpus is 1,600+ programs. The adjudicator design is the part I would show first: one ruling per (criterion, field) pair, ever, which is simultaneously the spend guard, the termination proof and the resume marker. A dry run, then a 200-ruling audited sample, then a full sweep that cleared a 4,400-item ambiguity queue to zero for about $33 of model spend, every ruling logged with its reason. Python, FastAPI, PostgreSQL, React and TypeScript, Docker, Azure, 21 ADRs.
- **circleofenterprise**: a "SQL Server intelligence" MCP server. Schema and stored-procedure analysis, dependency mapping, Query Store insights, shipped as a dotnet global tool. C# / .NET 9, CQRS, ScriptDOM.
- **donna**: an inbound-agent platform. A hosted AI representative of a person that humans and other agents can talk to, with profiles, personas and permissioned context. C# / .NET 10, Microsoft Agent Framework, EF Core and PostgreSQL, React PWA.
- **strata**: a colony survival simulation with conservative thermodynamics, autonomous bots and a full mine-haul-craft economy. Engine-agnostic, deterministic C# core with 250+ tests, Unity 6 shell on top.

All of it built the same way: spec first, agents implement, verification gates before merge.

---

### Open source

- [**tghamm/Anthropic.SDK**](https://github.com/tghamm/Anthropic.SDK) (220+ stars): structured output support for the Microsoft.Extensions.AI `IChatClient`, so Claude works with Microsoft Agent Framework's `ResponseFormat`. [PR #180](https://github.com/tghamm/Anthropic.SDK/pull/180)

### Credentials

- **ISO/IEC 42001 Lead Implementer**, PECB, certified August 2026. AI management systems, meaning the governance side of putting agents into production.

### Stack

C# / .NET, Python, TypeScript, SQL Server, PostgreSQL (PostGIS, pgvector), Azure and Azure DevOps.
Claude Code, Model Context Protocol, Microsoft Agent Framework, Anthropic API.

### Earlier work

- [**CityGML2GameObject**](https://github.com/TJaenichen/CityGML2GameObject): runtime import of CityGML geospatial data into Unity.
- [**PoolEditor**](https://github.com/TJaenichen/PoolEditor): React + TypeScript shot-planning component with trajectory physics, packaged as a Vite library.
- A decade of GPU ray tracing (NVIDIA OptiX), Unity, VR and IoT before that. Happy to talk about any of it.

---

[LinkedIn](https://www.linkedin.com/in/tjaenichen) · [jaenichen.ca](https://jaenichen.ca) · tjaenichen@gmail.com
