# Equity Research Skill

[Chinese documentation](README.zh-CN.md)

An AI agent skill for researching listed companies and producing evidence-backed investment reports. It connects **business economics → financial quality → independent forecasts → valuation → investment judgment**.

Use it to understand a business, assess its earnings and cash prospects, and judge whether the prospective return justifies the observed share price. The framework adapts to a company's operating stage and economics; it does not prescribe one valuation model, earnings year, multiple, or rating for every company.

The skill is written in English. Reports follow your requested language, or the language of your conversation.

## What it produces

An ordinary request for a company report defaults to a complete initiation report with:

- **17 research sections**, from the investment conclusion and business model to financial analysis, forecasts, competition, valuation, catalysts, risks and falsification.
- **Eight financial-statement capabilities**, with the relevant calculations and investment implications.
- A clear investment judgment tied to an observed price and stated horizon, normally about 12 months.
- Bear, representative base and bull target prices, with sensitivity intervals distinguished from economic scenarios.
- Supporting workpapers with sources, definitions, forecast and valuation workings, and coverage/consistency checks.

The report carries the decisive reasoning; workpapers hold detailed checks. For multiple companies, each receives a standalone analysis. Earnings updates, price refreshes and document reviews are also supported without requiring a full initiation every time.

Output format is flexible: ask for Markdown, HTML or another format supported by your agent. This repository supplies a report template, not a fixed renderer or a market-data service.

## Installation

### Requirements

Use an agent that can load `SKILL.md` and read its supporting files. Current research also requires access to recent filings, prices and news through the agent's browsing or data tools, plus a way to perform and save calculations. The skill does not supply paid data subscriptions, API credentials, or browsing capabilities.

No package manager, MCP server, or model-specific runtime is required by the skill itself. Git is needed only for the clone method below; downloading the repository ZIP is an alternative.

### 1. Download

```sh
git clone https://github.com/xdnloveme/equity-research-skill.git
cd equity-research-skill
```

The repository root is the skill package. Install `SKILL.md` together with `references/`, `assets/` and `agents/` into a folder named **`equity-research-brief`**; copying only `SKILL.md` leaves the framework incomplete.

### 2. Choose your agent and scope

| Agent | Personal installation root | Project installation root | Explicit invocation |
|---|---|---|---|
| Codex | `~/.agents/skills/` | `<project>/.agents/skills/` | `$equity-research-brief` |
| Claude Code | `~/.claude/skills/` | `<project>/.claude/skills/` | `/equity-research-brief` |
| Cursor | `~/.cursor/skills/` | `<project>/.cursor/skills/` | Type `/` and select the skill |

These locations and invocation conventions follow the official [Codex](https://developers.openai.com/codex/skills/), [Claude Code](https://code.claude.com/docs/en/skills) and [Cursor](https://cursor.com/docs/skills) documentation. Local installation does not automatically install a skill in remote or cloud sessions; follow your host's deployment instructions there.

For macOS/Linux, from the cloned repository, select one root and copy:

```sh
# Codex; change to "$HOME/.claude/skills" for Claude Code
# or "$HOME/.cursor/skills" for Cursor.
skill_root="$HOME/.agents/skills"
mkdir -p "$skill_root"
# Do not overwrite an existing installation without reviewing it.
if [ -e "$skill_root/equity-research-brief" ]; then
  echo "An installation already exists. Review it before updating."
else
  mkdir "$skill_root/equity-research-brief" &&
    cp -R SKILL.md references assets agents "$skill_root/equity-research-brief/"
fi
```

For a project installation, set `skill_root` to the corresponding directory in your project. On Windows, create an `equity-research-brief` folder under your chosen installation root and copy `SKILL.md`, `references/`, `assets/` and `agents/` into it; `~` means your user home directory. If the agent runs in WSL, a container or a remote machine, install inside that environment.

The result should be `<installation-root>/equity-research-brief/SKILL.md`. Start a new agent session if the skill is not discovered immediately, then check that it appears in the available skills.

### Other agents

Agents supporting the [Agent Skills format](https://agentskills.io/specification) can use the same package in their documented skill directory. `agents/openai.yaml` is optional Codex UI metadata; the research instructions do not depend on it. Tool availability and skill discovery differ by host. These installation routes are documented compatibility, not a claim that every host/model has passed an end-to-end research test.

If your tool does not support skill discovery but can read local files, point it to `SKILL.md` and ask it to follow the linked references and template. This is manual use, not automatic installation.

## Usage

After installation, invoke the skill and make an ordinary research request.

**Codex**

```text
Use $equity-research-brief to produce a complete research report on
[company] ([ticker], [exchange]). Use the latest available financial
results, share price and material news. Write in English and save an
HTML report with linked workpapers and reproducible calculations.
```

**Claude Code**

```text
/equity-research-brief Research [company] ([ticker], [exchange]) using
the latest available information. Deliver a complete report in English
with supporting workpapers.
```

**Cursor or another compatible agent**

Select `equity-research-brief` in the skill menu, then ask:

```text
Produce separate complete research reports on [company A] and
[company B], using the latest available information.
```

Useful variations:

- **Earnings update:** “Update the research after the latest results; explain what changed in the thesis, forecast and valuation.”
- **Price refresh:** “Refresh the investment judgment at the latest price and check for material news since the report.”
- **Historical research:** “Analyze the company using only information published by [date/time/timezone].”
- **Report review:** “Review this report's evidence, financial reasoning and valuation assumptions.”

Specify the ticker, exchange and share class when ambiguous. You can also specify the horizon, output language, format or your institution's rating policy. You do not need to repeat the 17-section structure or request the eight capabilities separately.

## Research coverage

| Sections | Focus |
|---|---|
| M01–M02 | Investment decision; company and security snapshot |
| M03–M05 | Business model; revenue mix; investment theses and expectations gap |
| M06–M08 | Latest results; guidance; independent forecasts |
| M09–M12 | Commercialization roadmap; capital and cash; dependencies; competition |
| M13 | Valuation, price attractiveness and one main rating |
| M14–M17 | Catalysts; risks; contrary case and falsification; synthesis and logic map |
| M00 / workpapers | Scope, sources, definitions, calculations and validation evidence |

The eight financial capabilities are:

1. Definitions and statement reconciliation.
2. Revenue growth attribution.
3. Margins and operating leverage.
4. Earnings quality and accounting judgments.
5. Cash flow and working capital.
6. Investment, capital returns and growth quality.
7. Balance sheet and funding resilience.
8. Earnings surprise and independent forecasting.

The framework starts with primary evidence and independent reasoning, then uses institutional views to challenge the conclusion. Valuation methods—including multiples, DCF, SOTP and asset-based approaches—are selected for economic fit and evidence quality. Earnings periods and multiples must be matched; a later earnings year does not automatically justify a higher target price.

## Repository layout

```text
equity-research-skill/
├── README.md
├── README.zh-CN.md
├── SKILL.md
├── agents/openai.yaml
├── assets/brief-template.md
└── references/
    ├── research-modules.md
    ├── financial-analysis.md
    ├── valuation-rating.md
    ├── information-freshness.md
    └── business-adaptation.md
```

The repository contains the reusable framework and template, not historical company reports, private source documents, credentials, or research-session files. Research rules live in the skill; this README explains installation and use.

## Updating and limitations

Run `git pull --ff-only` in your downloaded repository, review changes, then replace your installed skill folder with the updated package after preserving any local customizations. Avoid keeping conflicting copies of the same skill in multiple discovery locations.

The skill is a research method, not a deterministic valuation engine. Results depend on the model, available evidence, tools and execution. Its checks support review but do not guarantee complete facts, identical forecasts across runs, or investment performance. Scenario endpoints are conditional estimates, not guaranteed price floors or ceilings. Ratings use the definitions in `references/valuation-rating.md` unless you specify another policy.

Review generated analysis before making financial decisions. The skill does not execute trades.
