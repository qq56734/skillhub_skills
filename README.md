# skillhub-skills-ace-batch-41-81

从 `C:\Users\qq567\Desktop\codes\projects\ace_skills\_review_41_81` 审查批次导入的 6 个 Claude / agent skill，打包成 SkillHub 格式。

**与主仓库 `skillhub_skills`（含 22 个科研/法律类 skill）完全独立**，本仓库只含审查批次 41-81 中协议可验证的 6 个 skill。

## 审查来源

详细审查过程与依据见：`C:\Users\qq567\Desktop\codes\projects\ace_skills\_review_41_81\review_report_41_81.md`

审查日期：2026-08-17（初稿）→ 2026-08-18（含作者线索深搜更新）→ 2026-08-20（含 VPN 下的 GitHub API 复核）

## 目录结构

```
README.md                                  # 本文件
manifest.json                              # skill 清单（来源 / license / 类目 / 状态）
skills/<name>/
  plugin.yaml                              # SkillHub 元数据
  <name>/
    SKILL.md                               # 原始 skill 描述
    LICENSE / UPSTREAM-LICENSE.txt          # LICENSE 文本
    references/                            # 部分 skill 的参考文档
    scripts/                               # 部分 skill 的脚本
```

## Skill 清单

### ready（4 个）— 协议完整可直接上传

| skill | 来源 | license | 类目 |
|---|---|---|---|
| grill-me | mattpocock/skills | MIT | 元方法论 |
| knowledge-organizer-xiaping | cjke84/knowledge-organizer | MIT | 数据与科研 |
| landing-page-generator | jezweb/claude-skills | MIT | 前端开发 |
| mcp-builder | anthropics/skills | Apache-2.0 | 开发工具 |

### caution（2 个）— 上游 MIT 已核实，包装文件作者未知

| skill | 来源 | license | 协议说明文件 | 风险点 |
|---|---|---|---|---|
| markitdown-skill | microsoft/markitdown | MIT（上游核实） | UPSTREAM-LICENSE.txt | 包装文件作者未知 |
| oracle | steipete/oracle | MIT（上游核实） | UPSTREAM-LICENSE.txt | 包装文件作者未知 |

## 署名与 License

- `ready` 类的 skill 在 `skills/<name>/<name>/LICENSE`（或 `LICENSE.txt`）下提供原始 LICENSE 文本。
- `caution` 类的 skill 在 `skills/<name>/<name>/UPSTREAM-LICENSE.txt` 保留上游 MIT 全文，入库时注明"包装文件作者未知"。
- 每个 skill 的来源、commit/license 字段记录在 `manifest.json` 中。

## 后续动作

1. **ready 类 4 个**：可直接用 SkillHub 工具链打包上传。
2. **caution 类 2 个**：保留 `UPSTREAM-LICENSE.txt`，入库时注明"包装文件作者未知"即可。
