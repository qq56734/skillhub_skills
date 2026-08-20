# skillhub-skills-ace-batch-41-81

从 `C:\Users\qq567\Desktop\codes\projects\ace_skills\_review_41_81` 审查批次导入的 8 个 Claude / agent skill，打包成 SkillHub 格式。

**与主仓库 `skillhub_skills`（含 22 个科研/法律类 skill）完全独立**，本仓库只含审查批次 41-81 的 8 个 skill。

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
    LICENSE                                # ready 类完整 LICENSE 文本
    LICENSE-NOTE.md / UPSTREAM-LICENSE.txt  # caution 类协议说明
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

### caution（4 个）— 协议有条件需附说明

| skill | 来源 | license | 协议说明文件 | 风险点 |
|---|---|---|---|---|
| ios-application-dev | MiniMax-AI/AgentSkills（404） | MIT（frontmatter 自称） | LICENSE-NOTE.md | 上游 404，jsDelivr + GitHub API 双重验证 |
| markitdown-skill | microsoft/markitdown | MIT（上游核实） | UPSTREAM-LICENSE.txt | 包装文件作者未知 |
| note-organizer | bytesagain/ai-skills | MIT（作者主仓库） | LICENSE-NOTE.md | 此 skill 不在作者主仓库中 |
| oracle | steipete/oracle | MIT（上游核实） | UPSTREAM-LICENSE.txt | 包装文件作者未知 |

## 署名与 License

每个 `ready` 类的 skill 在 `skills/<name>/<name>/LICENSE`（或 `LICENSE.txt`）下提供原始 LICENSE 文本。

每个 `caution` 类的 skill：
- 若上游可核实（如 microsoft/markitdown、steipete/oracle），在 `skills/<name>/<name>/UPSTREAM-LICENSE.txt` 保留上游 MIT 全文。
- 若上游不可达（如 MiniMax-AI/AgentSkills）或此 skill 不在作者主仓库（如 bytesagain/ai-skills），在 `skills/<name>/<name>/LICENSE-NOTE.md` 中说明协议来源、风险与上传建议。

每个 skill 的来源、commit/license 字段记录在 `manifest.json` 的 `source_repo` / `fetched_commit` / `license` / `upload_status` 字段中。

## 后续动作

1. **ready 类 4 个**：可直接用 SkillHub 工具链打包上传。
2. **caution 类 4 个**：
   - markitdown-skill 与 oracle 建议保留 `UPSTREAM-LICENSE.txt`，入库时上传说明中注明"包装文件作者未知"。
   - ios-application-dev 建议先联系 `MiniMax-OpenSource`（clawhub 站内）确认协议后再入库。
   - note-organizer 建议先发邮件至 `hello@bytesagain.com` 确认此 skill 是否同样为 MIT，再入库。
