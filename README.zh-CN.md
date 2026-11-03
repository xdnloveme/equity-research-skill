# Equity Research Skill — AI 个股研报与股票基本面分析

[English](README.md) / **中文版本**

**看懂公司，判断价格，知道接下来该关注什么。**

Equity Research Skill 帮你把分散的公司公告、财报和市场新闻整理成一份完整的**个股研究报告**：这家公司靠什么赚钱，未来盈利由什么驱动，当前股价对应的潜在回报与风险是否值得考虑。你会得到明确的投资判断、悲观／基准／乐观目标价，以及可能改变结论的关键变化；数据来源和计算依据也能逐项复核。

适用于 **Codex、Claude Code、Cursor 及其他支持 Agent Skills 的工具**。无论是研究一只新股票、财报后重新评估持仓，还是分别研究多家公司，都可以直接提出请求。股票基本面分析框架会根据公司的商业模式和经营阶段调整重点，报告默认使用当前对话语言，也可以单独指定。

## 你会得到什么

提出普通的个股研报请求，默认就会启动完整研究。

| 交付内容 | 包含什么 |
|---|---|
| **投资结论** | 区分公司质量、盈利前景和价格吸引力，给出一个主评级、判断依据及改变结论的条件 |
| **完整研报** | 17 个模块，覆盖商业模式、财务表现、独立预测、竞争、估值、催化剂与风险 |
| **估值情景** | 明确期限内的悲观、代表性基准和乐观价格，默认期限为 12 个月；计算预期回报，单独展示敏感性区间 |
| **研究底稿** | 数据来源、财务勾稽、预测假设、估值计算和覆盖检查，便于复核 |

正文解释为什么得出这个结论，底稿保留可追溯的分析依据。可以指定 Markdown、HTML 或当前工具支持的其他格式；内置[简报模板](assets/brief-template.md)规定研究内容，不限定视觉样式。

## 安装与使用：Codex、Claude Code 和 Cursor

### 1. 安装到你的 AI 工具

**Skills CLI（推荐）**

安装 Node.js 22.20+ 和 Git 后，在项目目录运行以下命令，选择你的 AI 工具：

```sh
npx skills add xdnloveme/equity-research-skill --skill equity-research-brief
```

默认仅安装到当前项目。添加 `-g` 可进行跨项目的个人安装；使用 `-a codex`、`-a claude-code` 或 `-a cursor` 可直接指定工具。详见 [Skills CLI 文档](https://github.com/vercel-labs/skills#install-a-skill)，也可以[在 Skills.sh 查看本技能](https://www.skills.sh/xdnloveme/equity-research-skill/equity-research-brief)。

已用 Skills CLI 1.7.6 验证 Codex、Claude Code 和 Cursor 的项目安装，八份研究包文件均与仓库一致。这验证的是安装过程，不代表每个工具中的研报质量均已验证。

**通过 Git 手动安装**

也可以选择下列一条命令进行个人安装。目标目录已存在时，克隆操作不会覆盖它。选择一种安装方式即可，避免重复安装。

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

仓库名是 `equity-research-skill`，安装后的技能名和调用名是 **`equity-research-brief`**。

如果只想在某个项目中使用，改用下表中的项目目录。目录和调用方式可对照链接中的官方文档。

| 工具 | 项目安装目录 | 调用方式 |
|---|---|---|
| [Codex](https://developers.openai.com/codex/skills/) | `.agents/skills/equity-research-brief/` | `$equity-research-brief` |
| [Claude Code](https://code.claude.com/docs/en/skills) | `.claude/skills/equity-research-brief/` | `/equity-research-brief` |
| [Cursor](https://cursor.com/docs/skills) | `.cursor/skills/equity-research-brief/` | 输入 `/` 并选择 `equity-research-brief` |

**不使用 Git：**下载仓库 ZIP，解压后将文件夹改名为 `equity-research-brief`，放入对应工具的技能目录。保留完整的 `SKILL.md`、`references/`、`assets/` 和 `agents/`。

如果没有立即发现技能，请新开一个会话。使用 WSL、容器或远程会话时，应安装到工具实际运行的环境中。避免在个人与项目目录中重复安装。

### 2. 提出研究请求

在 Codex 中：

```text
使用 $equity-research-brief 研究[公司名]（[股票代码]、[交易所]）。
财报、股价和重要新闻使用最新可获取的信息。
用中文输出完整研报，并附上研究底稿。
```

Claude Code 中以 `/equity-research-brief` 开头提出请求；Cursor 中先选择该技能，再发送研究请求。

这样就会使用完整框架，无需反复强调模块数量或财报分析要求。存在歧义时请说明股份类别；也可以补充报告格式、持有期限或机构自己的评级政策。

## 它如何开展研究

**商业模式 → 财务质量 → 独立预测 → 估值 → 投资判断。**

- **先看原始证据。**从公告、财务报表和公司披露出发，先独立推导，再用机构观点核对和挑战预测与估值。
- **解释经营机制。**把需求、竞争优势和执行进展，连接到收入、利润、资本需求和股东现金回报。
- **按公司特点选择估值工具。**倍数估值、DCF、分部估值等方法取决于经济适用性与证据质量，不固定 PE、盈利年份或模型。
- **先形成判断，再检验替代情景。**说明为什么选择这一基准、为什么得出主结论；悲观、乐观和敏感性分析用于检验判断，而不是替代判断。
- **保持实时性与口径一致。**交付前刷新重大新闻和股价，匹配盈利窗口与估值倍数，核对正文和计算结果。

具体研究要求由 [SKILL.md](SKILL.md) 及其参考文件维护。README 负责介绍和上手，不另外定义一套规则。

## 个股研究与财报分析覆盖

<details>
<summary><strong>17 个正文模块</strong></summary>

| 编号 | 模块 |
|---|---|
| M01 | 投资结论与评级 |
| M02 | 公司与证券概况 |
| M03 | 商业模式与价值创造 |
| M04 | 收入结构与增长来源 |
| M05 | 投资逻辑与预期差 |
| M06 | 最新业绩与盈利趋势 |
| M07 | 管理层指引与近期展望 |
| M08 | 独立预测与市场预期对照 |
| M09 | 产品、技术及商业化路线 |
| M10 | 资本配置、地域布局、现金流与韧性 |
| M11 | 客户、地域与供应依赖 |
| M12 | 竞争格局与竞争优势 |
| M13 | 估值、价格与动态评级 |
| M14 | 催化剂与跟踪指标 |
| M15 | 主要风险与损失情景 |
| M16 | 相反观点与证伪条件 |
| M17 | 最终结论与投资逻辑图 |

M00 负责研究范围、数据定义与证据记录，体现在报告头部和底稿中，不额外增加正文模块。

</details>

<details>
<summary><strong>八项财报分析能力</strong></summary>

| 编号 | 分析能力 |
|---|---|
| F01 | 口径定义与财务报表勾稽 |
| F02 | 收入增长归因 |
| F03 | 利润率与经营杠杆 |
| F04 | 盈利质量与会计判断 |
| F05 | 现金流与营运资本 |
| F06 | 投入、资本回报与增长质量 |
| F07 | 资产负债表与融资韧性 |
| F08 | 业绩预期差与独立预测 |

每项能力都将分析发现和计算结果连接到预测或投资判断；详细推导保留在关联底稿中。

</details>

## 更多用法

调用 skill 后，可以这样提出请求：

| 任务 | 请求示例 |
|---|---|
| 多公司研究 | “分别为[公司 A]和[公司 B]出完整研报。” |
| 财报更新 | “根据最新财报更新报告，说明投资逻辑、预测和估值发生了哪些变化。” |
| 价格刷新 | “按最新股价更新投资判断，并检查报告发布后的重大事件。” |
| 历史研究 | “仅使用[日期、时间及时区]之前已公开的信息。” |
| 研报审查 | “审查这份报告的证据、财务推导和估值假设。” |

## 文件与通用性

| 文件或目录 | 用途 |
|---|---|
| [SKILL.md](SKILL.md) | 入口、研究流程与交付检查 |
| [references/](references/) | 研究模块、财报分析、估值、信息实时性和业务适配方法 |
| [assets/brief-template.md](assets/brief-template.md) | 研报与底稿模板 |
| [agents/openai.yaml](agents/openai.yaml) | 可选的 Codex 界面元数据，研究框架不依赖它 |

安装包采用 [Agent Skills 格式](https://agentskills.io/specification)，不要求专属运行时或特定 MCP 服务。其他兼容工具可以放入其官方支持的技能目录。不支持自动发现技能的工具，也可以通过读取 `SKILL.md` 及关联文件手动使用。格式兼容不代表所有模型和工具的研究质量完全一致。

## 更新

通过 Skills CLI 安装时，在原项目目录执行以下命令；个人安装添加 `-g`：

```sh
npx skills update equity-research-brief
```

通过 Git 手动安装时，在已安装的 `equity-research-brief` 目录中执行：

```sh
git pull --ff-only
```

更新前审阅变化并保留本地自定义修改。通过 ZIP 或复制安装时，重新下载并替换安装包即可。

## 使用条件与边界

AI 工具需要能获取财务披露、最新股价和新闻，并具备计算和文件输出能力。数据订阅、访问凭据及浏览能力不包含在 skill 中。

这是研究框架，不是确定性估值程序或交易系统，生成结果仍需审阅。情景上下限是有条件的估值，不是股价保证底线或上限。除非另行指定，评级遵循[公开的评级口径](references/valuation-rating.md)。skill 不执行交易，也不保证投资收益。
