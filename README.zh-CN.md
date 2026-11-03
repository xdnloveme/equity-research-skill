# Equity Research Skill

[English documentation](README.md)

面向上市公司研究的通用 AI Agent Skill，帮助研究者形成有依据的个股投资判断。研究主线是：**商业模式 → 财务质量 → 独立预测 → 估值 → 投资结论**。

它用于理解公司如何创造价值、判断盈利和现金回报前景，并结合当前股价评估预期回报是否合理。框架会根据经营阶段和业务经济特征选择研究重点与估值工具，不为所有公司固定盈利年份、估值倍数或评级。

skill 本体使用英文维护；报告遵循你指定的语言，未指定时使用当前对话语言。

## 可以得到什么

普通的个股研报请求默认交付完整研究，包括：

- **17 个研究模块**：投资结论、商业模式、财务表现、独立预测、竞争、估值、催化剂、风险及反证。
- **八项财报分析能力**：保留相关计算、推导和投资含义。
- 围绕明确股价与持有期的投资判断，默认评估约 12 个月的预期总回报。
- 悲观、代表性基准和乐观目标价，并将情景区间与参数敏感性区间区分。
- 包含来源、口径、模型计算及完整性和一致性检查的配套底稿。

正文保留影响判断的关键依据，详细核对放在底稿。多公司研究应分别交付完整分析，也支持财报更新、价格刷新和已有研报审查。

可以指定 Markdown、HTML 或当前工具支持的其他格式。仓库提供研究框架和简报模板，不包含固定渲染器或行情数据服务。

## 安装

### 使用条件

需要能够加载 `SKILL.md` 并读取关联文件的 AI 工具。实时研究还需要该工具能够通过浏览或数据接口获取最新财报、股价和新闻，并能够进行和保存计算。skill 不附带付费数据订阅、API 密钥或浏览能力。

skill 本身不依赖特定模型、MCP 服务或包管理器。下面的克隆方式需要 Git，也可以下载仓库 ZIP 后解压。

### 1. 下载仓库

```sh
git clone https://github.com/xdnloveme/equity-research-skill.git
cd equity-research-skill
```

仓库根目录就是 skill 安装包。请将 `SKILL.md`、`references/`、`assets/` 和 `agents/` 一起放入名为 **`equity-research-brief`** 的安装文件夹，不要只复制 `SKILL.md`。

### 2. 选择工具和安装范围

| 工具 | 个人安装根目录 | 项目安装根目录 | 显式调用 |
|---|---|---|---|
| Codex | `~/.agents/skills/` | `<project>/.agents/skills/` | `$equity-research-brief` |
| Claude Code | `~/.claude/skills/` | `<project>/.claude/skills/` | `/equity-research-brief` |
| Cursor | `~/.cursor/skills/` | `<project>/.cursor/skills/` | 输入 `/` 并选择 skill |

安装目录和调用方式依据 [Codex](https://developers.openai.com/codex/skills/)、[Claude Code](https://code.claude.com/docs/en/skills) 和 [Cursor](https://cursor.com/docs/skills) 官方文档。个人本机安装不会自动部署到远程或云端会话，后者需按对应工具的部署方式配置。

macOS/Linux 在克隆后的仓库目录执行：

```sh
# Codex; use "$HOME/.claude/skills" for Claude Code
# or "$HOME/.cursor/skills" for Cursor.
skill_root="$HOME/.agents/skills"
mkdir -p "$skill_root"
if [ -e "$skill_root/equity-research-brief" ]; then
  echo "An installation already exists. Review it before updating."
else
  mkdir "$skill_root/equity-research-brief" &&
    cp -R SKILL.md references assets agents "$skill_root/equity-research-brief/"
fi
```

项目安装时，将 `skill_root` 改为项目内相应的目录。Windows 可以在安装根目录下新建 `equity-research-brief` 文件夹，再复制 `SKILL.md`、`references/`、`assets/` 和 `agents/` 到其中；`~` 表示用户主目录。使用 WSL、容器或远程机器时，应安装到 AI 工具实际运行的环境中。

安装后的文件应位于 `<安装根目录>/equity-research-brief/SKILL.md`。如果未立即发现 skill，开启新的工具会话，并在可用技能列表中确认。

### 其他 AI 工具

支持 [Agent Skills 格式](https://agentskills.io/specification) 的工具，可以将同一安装包放入其官方支持的 skill 目录。`agents/openai.yaml` 只是可选的 Codex 界面元数据，研究逻辑不依赖它。

以上是文档支持的安装适配，不代表已在每一种工具或模型中完成端到端研报测试。发现方式、数据和计算工具的可用性仍取决于宿主。

若工具不支持技能发现但能读取本地文件，可以指定 `SKILL.md`，要求它读取关联参考文件和模板。这属于手动使用，不等于自动安装。

## 使用示例

**Codex**

```text
使用 $equity-research-brief 为[公司名]（[代码]、[交易所]）出一份完整研报。
财报、股价和重要新闻使用最新可获取的信息，用中文输出 HTML 报告，
附上关联底稿和可复核的计算。
```

**Claude Code**

```text
/equity-research-brief 为[公司名]（[代码]、[交易所]）出一份完整研报，
使用最新可获取的信息，用中文输出，并附上研究底稿。
```

**Cursor 或其他兼容工具**

在技能菜单中选择 `equity-research-brief`，然后提出普通请求：

```text
分别为[公司 A]和[公司 B]出完整研报，使用最新可获取的信息。
```

其他常用请求：

- **财报更新**：“根据最新财报更新研究，说明投资逻辑、预测和估值发生了哪些变化。”
- **价格刷新**：“按最新股价更新投资判断，并检查报告发布后是否发生重大事件。”
- **历史研究**：“仅使用[日期、时间及时区]之前已公开的信息分析该公司。”
- **研报审查**：“审查这份研报的数据依据、财务推导和估值假设。”

公司有歧义时，说明代码、交易所和股份类别。你也可以指定持有期、输出语言、格式或机构自己的评级政策，无需每次重述 17 个模块和八项财报能力。

## 研究覆盖

| 模块 | 内容 |
|---|---|
| M01–M02 | 投资判断；公司与证券概况 |
| M03–M05 | 商业模式；收入结构；投资逻辑和预期差 |
| M06–M08 | 最新业绩；管理层指引；独立预测 |
| M09–M12 | 商业化路线；资本与现金；业务依赖；竞争优势 |
| M13 | 估值、价格吸引力和主评级 |
| M14–M17 | 催化剂；风险；反证；总结与逻辑图 |
| M00 / 底稿 | 研究范围、来源、定义、计算及检查证据 |

八项财报能力包括：

1. 口径定义与财务报表勾稽。
2. 收入增长归因。
3. 利润率与经营杠杆。
4. 盈利质量与会计判断。
5. 现金流与营运资本。
6. 投入、资本回报与增长质量。
7. 资产负债表与融资韧性。
8. 业绩预期差与独立预测。

先从原始证据独立推导，再使用机构观点核对和挑战结论。倍数估值、DCF、分部估值和资产法等工具按经济适用性与证据质量选择。盈利窗口必须与估值倍数匹配，采用更远期的盈利不自动意味着更高目标价。

## 仓库结构

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

仓库仅包含通用框架、模板与使用文档，不包含历史个股研报、私有源文件、凭据或研究会话的临时文件。研究要求由 skill 本体维护，README 负责介绍与安装使用说明。

## 更新与能力边界

在下载的仓库中执行 `git pull --ff-only`，审阅变化，保留已有自定义修改后，用最新安装包替换已安装的文件夹。避免在多个技能发现目录中保留冲突版本。

skill 是研究方法，不是确定性估值程序。结果取决于模型、证据、工具和执行情况，检查机制不能保证重大事实永不遗漏、不同运行预测完全相同或投资收益。情景上下限是有条件的估值结果，不是股价保证底线或上限。除非另行指定，评级使用 `references/valuation-rating.md` 中的定义。

投资决策前仍需审阅生成的分析。skill 不执行交易。
