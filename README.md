# Equity Research Skill — Stock Analysis for AI Agents

**English** / [中文版本](README.zh-CN.md)

**Understand the business. Assess the price. Know what to watch.**

Equity Research Skill helps you turn scattered filings, earnings releases and market news into a complete **stock research report**. Understand how a company makes money, what could drive future earnings, and whether the current share price offers an attractive balance of potential return and risk. Get a clear investment view, bear/base/bull price targets, and the developments that would change the conclusion—with sources and calculations you can inspect.

Built for **Codex, Claude Code, Cursor and other agents that support Agent Skills**. Use it to research a new investment, reassess a holding after earnings, or produce separate reports on several companies. The fundamental analysis framework adapts to each company's business model and operating stage; reports follow your conversation language unless you request another language.

## What you get

A simple request for a company report starts a complete research assignment by default.

| Deliverable | What it contains |
|---|---|
| **Investment conclusion** | Business quality, earnings outlook and price attractiveness; one main rating, its rationale and what would change the judgment |
| **Complete report** | 17 sections covering the business, financial statements, forecasts, competition, valuation, catalysts and risks |
| **Valuation scenarios** | Bear, representative base and bull prices for a stated horizon, normally 12 months; expected returns and separately labeled sensitivities |
| **Supporting workpapers** | Sources, financial reconciliations, forecast assumptions, valuation calculations and coverage checks |

The main report explains the decision. Workpapers make the supporting analysis traceable. Request Markdown, HTML or another format your agent can produce; the included [report template](assets/brief-template.md) defines the content rather than a fixed visual design.

## Quick start: install and run your first report

**Before you start:** use an AI agent with access to company filings, current prices and news, plus calculation and file-output tools. The skill supplies the research workflow; it does not include a market-data service or subscriptions.

### 1. Install for your agent

**Skills CLI (recommended)**

With Node.js 22.20+ and Git installed, run this from your project and select your agent:

```sh
npx skills add xdnloveme/equity-research-skill --skill equity-research-brief
```

The default scope is the current project. Add `-g` for a personal installation across projects; use `-a codex`, `-a claude-code` or `-a cursor` to select an agent directly. See the [Skills CLI documentation](https://github.com/vercel-labs/skills#install-a-skill) or [view this skill on Skills.sh](https://www.skills.sh/xdnloveme/equity-research-skill/equity-research-brief).

### 2. Ask for a report

Open your AI agent in the same project where you installed the skill. In Codex, send:

```text
Use $equity-research-brief to research [company] ([ticker], [exchange]).
Use the latest available financial results, share price and material news.
Deliver a complete report in English, with supporting workpapers.
```

In Claude Code, start the request with `/equity-research-brief`. In Cursor, select the skill before sending the request.

That's enough to request the full framework. Specify the share class when ambiguous; optionally add an output format, investment horizon or your institution's rating policy. You do not need to repeat the module list or financial-analysis requirements.

<details>
<summary><strong>Other installation methods: Git, ZIP and project paths</strong></summary>

**Manual installation with Git**

Alternatively, choose one command below for a personal installation. An existing destination will not be overwritten. Use one installation method to avoid duplicates.

**Codex**

```sh
git clone https://github.com/xdnloveme/equity-research-skill.git "$HOME/.agents/skills/equity-research-brief"
```

**Claude Code**

```sh
git clone https://github.com/xdnloveme/equity-research-skill.git "$HOME/.claude/skills/equity-research-brief"
```

**Cursor**

```sh
git clone https://github.com/xdnloveme/equity-research-skill.git "$HOME/.cursor/skills/equity-research-brief"
```

The repository is named `equity-research-skill`; the installed skill and invocation name are **`equity-research-brief`**.

For a project-only installation, use the corresponding directory below instead. These locations follow the linked official documentation.

| Agent | Project directory | How to invoke |
|---|---|---|
| [Codex](https://developers.openai.com/codex/skills/) | `.agents/skills/equity-research-brief/` | `$equity-research-brief` |
| [Claude Code](https://code.claude.com/docs/en/skills) | `.claude/skills/equity-research-brief/` | `/equity-research-brief` |
| [Cursor](https://cursor.com/docs/skills) | `.cursor/skills/equity-research-brief/` | Type `/` and select `equity-research-brief` |

**Without Git:** download the repository ZIP, extract it, rename the extracted folder to `equity-research-brief`, and place it in your agent's skill directory. Keep `SKILL.md`, `references/`, `assets/` and `agents/` together.

Start a new session if the skill is not immediately discovered. For WSL, containers or remote sessions, install in the environment where the agent runs. Avoid duplicate installations in personal and project directories.

</details>

## More ways to use it

After invoking the skill:

| Task | Example request |
|---|---|
| Multiple companies | “Produce separate complete reports on [company A] and [company B].” |
| Earnings update | “Update the report after the latest results. Explain changes to the thesis, forecast and valuation.” |
| Price refresh | “Refresh the investment judgment at the latest price and check material events since the report.” |
| Historical research | “Use only information published by [date, time and timezone].” |
| Report review | “Review this report's evidence, financial reasoning and valuation assumptions.” |

## How the research works

**Business economics → financial quality → independent forecasts → valuation → investment judgment.**

- **Primary evidence first.** Start with filings, financial statements and company disclosures. Use institutional views afterward to challenge the independent forecast and valuation.
- **Explain the business mechanism.** Connect demand, competitive advantage and execution to revenue, profit, capital needs and shareholder cash flows.
- **Choose valuation tools for the company.** Use multiples, DCF, segment valuation or other methods when their inputs and economic fit support them. No fixed PE, earnings year or model applies to every company.
- **Make a judgment, then test it.** Explain the representative base and main conclusion. Bear/bull scenarios and sensitivities show what could change; they do not replace the judgment.
- **Keep the evidence current and consistent.** Refresh material news and prices before delivery, match earnings periods to valuation multiples, and reconcile the report with its calculations.

Detailed research requirements live in [SKILL.md](SKILL.md) and its references. The README is an introduction and setup guide, not a second rulebook.

## Equity research and financial statement analysis

<details>
<summary><strong>17 report sections</strong></summary>

| ID | Section |
|---|---|
| M01 | Investment conclusion and rating |
| M02 | Company and security snapshot |
| M03 | Business model and value creation |
| M04 | Revenue mix and growth sources |
| M05 | Investment theses and expectations gap |
| M06 | Latest results and earnings trend |
| M07 | Management guidance and near-term outlook |
| M08 | Independent forecast and expectations bridge |
| M09 | Product, technology and commercialization roadmap |
| M10 | Capital allocation, geographic footprint, cash flow and resilience |
| M11 | Customer, geographic and supply dependencies |
| M12 | Competition and competitive advantage |
| M13 | Valuation, price and dynamic rating |
| M14 | Catalysts and monitoring KPIs |
| M15 | Principal risks and loss scenarios |
| M16 | Contrary case and falsification |
| M17 | Final conclusion and investment logic map |

M00 defines research scope, data definitions and evidence records in the header and supporting workpapers. It is not an additional narrative section.

</details>

<details>
<summary><strong>Eight financial-statement capabilities</strong></summary>

| ID | Capability |
|---|---|
| F01 | Definitions and statement reconciliation |
| F02 | Revenue growth attribution |
| F03 | Margins and operating leverage |
| F04 | Earnings quality and accounting judgments |
| F05 | Cash flow and working capital |
| F06 | Investment, capital returns and growth quality |
| F07 | Balance sheet and funding resilience |
| F08 | Earnings surprise and independent forecasting |

Each capability connects its findings and calculations to the forecast or investment judgment. Detailed workings belong in the linked workpapers.

</details>

## Files and portability

| File or directory | Purpose |
|---|---|
| [SKILL.md](SKILL.md) | Entry point, research workflow and delivery checks |
| [references/](references/) | Research modules, financial analysis, valuation, information freshness and business adaptation |
| [assets/brief-template.md](assets/brief-template.md) | Report and workpaper template |
| [agents/openai.yaml](agents/openai.yaml) | Optional Codex interface metadata; not required by the research framework |

The package uses the [Agent Skills format](https://agentskills.io/specification), with no required proprietary runtime or MCP server. Other compatible agents can load it from their documented skill directories. An agent without skill discovery can use it manually by reading `SKILL.md` and its linked resources. Host compatibility does not mean identical research quality across models or tools.

Project installation was verified with Skills CLI 1.7.6 for Codex, Claude Code and Cursor; all eight research-package files matched the repository. This verifies installation, not report quality in every agent.

## Updates

For a Skills CLI installation, run this from the project where you installed it (add `-g` for a personal installation):

```sh
npx skills update equity-research-brief
```

For a manual Git installation, run this inside the installed `equity-research-brief` directory:

```sh
git pull --ff-only
```

Review changes and preserve local customizations before updating. For ZIP or copied installations, replace the installed package with a newly downloaded copy instead.

## Research limitations

This is a research framework, not a deterministic valuation engine or trading system. Results still require review; scenario endpoints are conditional estimates, not guaranteed price floors or ceilings. Ratings follow the [published conventions](references/valuation-rating.md) unless you specify another policy. The skill does not execute trades or guarantee investment returns.

## Help and feedback

Maintained by [xdnloveme](https://github.com/xdnloveme). [Open an issue](https://github.com/xdnloveme/equity-research-skill/issues) for installation problems, missing analysis or inconsistent results. Include your agent/model, installation method, request and a short report excerpt; remove private information and credentials.

Contributions are welcome. See the [contribution guide](CONTRIBUTING.md) for scope and validation guidance.

## License

This skill and its documentation are licensed under the [MIT License](LICENSE). You may use, modify and redistribute them, including commercially, while retaining the copyright and license notices. This license does not grant rights to third-party financial data or source documents used during research.
