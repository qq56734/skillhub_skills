# skillhub-imported-skills

从 GitHub 开源社区精选的 Claude / agent skill，打包成 SkillHub 格式后批量上传到本地 SkillHub 市场。

## 目标类目

- **数据与科研 (data-science-research)** — 数据分析、统计、科研、文献综述
- **合规与法律 (compliance-legal)** — 政策解读、合规检查、风控、法律起草、监管分析

## 目录结构

```
manifest.json             # skill 清单（来源 / license / 类目）
scripts/
  fetch-and-package.mjs   # 下载 tarball -> 抽取 skill -> 生成 plugin.yaml -> 打 zip
  validate-skills.mjs     # 调 skillhub .venv 干跑校验打包格式
  publish-all.mjs         # 批量上传 dist/*.zip 到 SkillHub
skills/<name>/            # 抽取后的 skill 源文件 + 生成的 plugin.yaml + 原始 LICENSE
dist/<name>.zip           # SkillHub 打包产物（gitignore）
publish-results.json      # 上传结果（gitignore）
test-results/             # 22 个 skill 的批量测试报告（2026-07-25）
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

每个 skill 的原始 LICENSE 文本保留在 `skills/<name>/LICENSE`。所有源 skill 均为 MIT 或 Apache-2.0。上游来源与 commit 记录在 `manifest.json` 的 `source_repo` / `fetched_commit` 字段。

| skill | 来源 | license | 类目 |
|---|---|---|---|
| citation-management | hmzainjamil/claude-scientific-skills | MIT | 数据与科研 |
| data-analysis | Marazii/research-co-pilot | MIT | 数据与科研 |
| exploratory-data-analysis | K-Dense-AI/scientific-agent-skills | MIT | 数据与科研 |
| experimental-design | K-Dense-AI/scientific-agent-skills | MIT | 数据与科研 |
| literature-review | Marazii/research-co-pilot | MIT | 数据与科研 |
| methodology-advisor | Marazii/research-co-pilot | MIT | 数据与科研 |
| paper-search-pro | O0000-code/paper-search-pro | Apache-2.0 | 数据与科研 |
| peer-review | Marazii/research-co-pilot | MIT | 数据与科研 |
| recursive-research | Anjos2/recursive-research | MIT | 数据与科研 |
| scholar-evaluation | K-Dense-AI/scientific-agent-skills | MIT | 数据与科研 |
| scientific-visualization | K-Dense-AI/scientific-agent-skills | MIT | 数据与科研 |
| scientific-writing | K-Dense-AI/scientific-agent-skills | MIT | 数据与科研 |
| statistical-analysis | TerryFYL/claude-statistical-analysis-skill | MIT | 数据与科研 |
| statistical-power | K-Dense-AI/scientific-agent-skills | MIT | 数据与科研 |
| ai-act-compliance | abk1969/ai-act-skills | MIT | 合规与法律 |
| ai-deployment-checklist | ThomasMoreAI/legal-skills-open | Apache-2.0 | 合规与法律 |
| china-pipl | ThomasMoreAI/legal-skills-open | Apache-2.0 | 合规与法律 |
| gdpr | ThomasMoreAI/legal-skills-open | Apache-2.0 | 合规与法律 |
| harvey | xkaluv/harvey | MIT | 合规与法律 |
| kevin | kcass16/kevin | MIT | 合规与法律 |
| master-claude-for-legal | sboghossian/master-claude-for-legal | MIT | 合规与法律 |
| terms-generator | ThomasMoreAI/legal-skills-open | Apache-2.0 | 合规与法律 |

## 测试结果

22 个 skill 已于 2026-07-25 完成批量测试，详见 [`test-results/`](test-results/) 目录。

- 测试报告：`test-results/research/`（14 个科研类）+ `test-results/legal/`（8 个法律类）
- 汇总仪表盘：`test-results/summary-dashboard.png`
- 含测试数据的完整表格：`test-results/skillhub-22-skills-test-results.xlsx`
- 测试生成的图表：`test-results/assets/`

**结果：22 个 skill 中 21 个 PASS，1 个 FAIL\*（skill 功能正常，测试场景结果为不合规）。**

详见 [`test-results/README.md`](test-results/README.md)。
