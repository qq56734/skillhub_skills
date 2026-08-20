# skillhub-imported-skills

从 GitHub 开源社区精选的 Claude / agent skill，打包成 SkillHub 格式后批量上传到本地 SkillHub 市场。

## 目标类目

- **数据与科研 (data-science-research)** — 数据分析、统计、科研、文献综述
- **合规与法律 (compliance-legal)** — 政策解读、合规检查、风控、法律起草、监管分析
- **元方法论 (meta)** — 决策与方案审查类方法论
- **前端开发 (frontend-dev)** — 落地页、UI/UX 设计
- **开发工具 (developer-tools)** — MCP、CLI 等开发辅助

## 目录结构

```
manifest.json             # skill 清单（来源 / license / 类目 / 状态）
scripts/
  fetch-and-package.mjs   # 下载 tarball -> 抽取 skill -> 生成 plugin.yaml -> 打 zip
  validate-skills.mjs     # 调 skillhub .venv 干跑校验打包格式
  publish-all.mjs         # 批量上传 dist/*.zip 到 SkillHub
skills/<name>/
  plugin.yaml             # SkillHub 元数据
  <name>/
    SKILL.md              # 原始 skill 描述
    LICENSE               # ready 类完整 LICENSE 文本
    UPSTREAM-LICENSE.txt  # caution 类上游 MIT 全文
    references/           # 部分 skill 的参考文档
    scripts/              # 部分 skill 的脚本
dist/<name>.zip           # SkillHub 打包产物（gitignore）
publish-results.json      # 上传结果（gitignore）
test-results/             # 22 个原 skill 的批量测试报告（2026-07-25）
  README.md               #   测试汇总文档（方法 / 结果 / 目录说明）
  summary-dashboard.png   #   测试结果汇总仪表盘
  skillhub-22-skills-test-results.xlsx  # 原始 xlsx + 4 列测试数据
  research/               #   14 个数据与科研类 skill 测试报告 (.md)
  legal/                  #   8 个合规与法律类 skill 测试报告 (.md)
  assets/                 #   测试过程中生成的图表和辅助文件
```

## 工具链用法

```bash
# 1. 下载 + 打包（按 manifest.json）
node scripts/fetch-and-package.mjs

# 2. 干跑校验格式（需 skillhub 项目的 .venv）
node scripts/validate-skills.mjs

# 3. 一键上传（需先起 skillhub 本地后端 127.0.0.1:8100）
node scripts/publish-all.mjs
```

以后加 skill：编辑 `manifest.json` 加一条，重跑 1->2->3。

## 署名与 License

每个 skill 的原始 LICENSE 文本保留在 `skills/<name>/<name>/LICENSE`（或 `LICENSE.txt` / `UPSTREAM-LICENSE.txt`）。所有源 skill 均为 MIT 或 Apache-2.0。上游来源与 commit 记录在 `manifest.json` 的 `source_repo` / `fetched_commit` 字段。

### 22 个首批 skill（2026-07-25 完成批量测试）

| skill | 来源 | license | 类目 | 状态 |
|---|---|---|---|---|
| citation-management | hmzainjamil/claude-scientific-skills | MIT | 数据与科研 | ready |
| data-analysis | Marazii/research-co-pilot | MIT | 数据与科研 | ready |
| exploratory-data-analysis | K-Dense-AI/scientific-agent-skills | MIT | 数据与科研 | ready |
| experimental-design | K-Dense-AI/scientific-agent-skills | MIT | 数据与科研 | ready |
| literature-review | Marazii/research-co-pilot | MIT | 数据与科研 | ready |
| methodology-advisor | Marazii/research-co-pilot | MIT | 数据与科研 | ready |
| paper-search-pro | O0000-code/paper-search-pro | Apache-2.0 | 数据与科研 | ready |
| peer-review | Marazii/research-co-pilot | MIT | 数据与科研 | ready |
| recursive-research | Anjos2/recursive-research | MIT | 数据与科研 | ready |
| scholar-evaluation | K-Dense-AI/scientific-agent-skills | MIT | 数据与科研 | ready |
| scientific-visualization | K-Dense-AI/scientific-agent-skills | MIT | 数据与科研 | ready |
| scientific-writing | K-Dense-AI/scientific-agent-skills | MIT | 数据与科研 | ready |
| statistical-analysis | TerryFYL/claude-statistical-analysis-skill | MIT | 数据与科研 | ready |
| statistical-power | K-Dense-AI/scientific-agent-skills | MIT | 数据与科研 | ready |
| ai-act-compliance | abk1969/ai-act-skills | MIT | 合规与法律 | ready |
| ai-deployment-checklist | ThomasMoreAI/legal-skills-open | Apache-2.0 | 合规与法律 | ready |
| china-pipl | ThomasMoreAI/legal-skills-open | Apache-2.0 | 合规与法律 | ready |
| gdpr | ThomasMoreAI/legal-skills-open | Apache-2.0 | 合规与法律 | ready |
| harvey | xkaluv/harvey | MIT | 合规与法律 | ready |
| kevin | kcass16/kevin | MIT | 合规与法律 | ready |
| master-claude-for-legal | sboghossian/master-claude-for-legal | MIT | 合规与法律 | ready |
| terms-generator | ThomasMoreAI/legal-skills-open | Apache-2.0 | 合规与法律 | ready |

### 6 个新增 skill（2026-08-17 → 2026-08-20 来自 ace_skills 41-81 审查批次）

#### ready（4 个）— 协议完整可直接上传

| skill | 来源 | license | 类目 |
|---|---|---|---|
| grill-me | mattpocock/skills | MIT | 元方法论 |
| knowledge-organizer-xiaping | cjke84/knowledge-organizer | MIT | 数据与科研 |
| landing-page-generator | jezweb/claude-skills | MIT | 前端开发 |
| mcp-builder | anthropics/skills | Apache-2.0 | 开发工具 |

#### caution（2 个）— 上游 MIT 已核实，包装文件作者未知

| skill | 来源 | license | 协议说明文件 | 风险点 |
|---|---|---|---|---|
| markitdown-skill | microsoft/markitdown | MIT（上游核实） | UPSTREAM-LICENSE.txt | 包装文件作者未知 |
| oracle | steipete/oracle | MIT（上游核实） | UPSTREAM-LICENSE.txt | 包装文件作者未知 |

**新增 6 个 skill 的来源审查**：`C:\Users\qq567\Desktop\codes\projects\ace_skills\_review_41_81\review_report_41_81.md`（2026-08-17 初稿 → 2026-08-18 作者线索深搜 → 2026-08-20 VPN 下的 GitHub API 复核）。

## 41-81 审查批次的排除说明

41-81 范围另审查了 30 个"协议未声明"的 skill，均未找到可验证的 GitHub 上游仓库（office-claw-skills 是本地 clawhub 集合，无整体上游；`VoltAgent/awesome-openclaw-skills` 仅为索引仓库；TPD/BytesAgain 等作者线索均搜过 GitHub）。详细原因见上述 review_report_41_81.md 第 6-7 节。

## 测试结果

22 个首批 skill 已于 2026-07-25 完成批量测试，详见 [`test-results/`](test-results/) 目录。

- 测试报告：`test-results/research/`（14 个科研类）+ `test-results/legal/`（8 个法律类）
- 汇总仪表盘：`test-results/summary-dashboard.png`
- 含测试数据的完整表格：`test-results/skillhub-22-skills-test-results.xlsx`
- 测试生成的图表：`test-results/assets/`

**结果：22 个 skill 中 21 个 PASS，1 个 FAIL\*（skill 功能正常，测试场景结果为不合规）。**

详见 [`test-results/README.md`](test-results/README.md)。
