# LICENSE-NOTE for ios-application-dev

## 协议声明来源

`SKILL.md` frontmatter 自带声明：

```yaml
license: MIT
metadata:
  author: MiniMax-OpenSource
```

## 上游仓库核查记录

`SKILL.md` 中虽未直接列出 `homepage`，但按命名习惯推测上游为
`https://github.com/MiniMax-AI/AgentSkills`。本审查使用两种方式
交叉验证：

### 1. jsDelivr CDN 文件树（2026-08-18，无 VPN 时）

| 端点 | 结果 |
|---|---|
| `https://data.jsdelivr.com/v1/package/gh/MiniMax-AI/AgentSkills` | 404 |
| `https://cdn.jsdelivr.net/gh/MiniMax-AI/AgentSkills@main/SKILL.md` | 404 |
| `https://cdn.jsdelivr.net/gh/MiniMax-AI/AgentSkills@master/SKILL.md` | 404 |

### 2. GitHub API 直连（2026-08-20，开 VPN 后复核）

| 端点 | 结果 |
|---|---|
| `https://api.github.com/repos/MiniMax-AI/AgentSkills` | 404 `{"message":"Not Found"}` |
| `https://api.github.com/repos/MiniMax-AI/AgentSkills/contents/skills/ios-application-dev` | 404 |
| `https://api.github.com/search/repositories?q=MiniMax-AgentSkills` | 0 results |
| `https://api.github.com/search/repositories?q=MiniMax-OpenSource+ios` | 0 results |
| `https://api.github.com/search/repositories?q=AgentSkills+MiniMax` | 0 results |
| `https://api.github.com/search/repositories?q=openclaw+ios-application-dev` | 0 results |
| `https://api.github.com/search/repositories?q=ios-application-dev+skill` | 1 hit: `flaqai/ios-application-development-skills`（owner 是 flaqai Organization，**非 MiniMax-OpenSource**，描述仅 "develop, ASO etc"，与本 skill 的 10 个 UIKit/SwiftUI references 不匹配） |

**结论**：通过两条独立渠道（CDN + GitHub API）均无法定位到 frontmatter
声称的 `MiniMax-OpenSource` 仓库。`MiniMax-OpenSource` 这个 author 标识在
GitHub 上找不到任何公开仓库对应。

## 风险说明

- 声称的源代码仓库为 `MiniMax-AI/AgentSkills`，**经 jsDelivr 与 GitHub API 双重核实均返回 404**。
- author 标识 `MiniMax-OpenSource` 在 GitHub 平台上无任何对应账户或仓库。
- 本目录中的 `SKILL.md` 与 9 个 `references/*.md` 文档（`accessibility`、
  `graphics-animation`、`layout-system`、`metal-shader`、`navigation-patterns`、
  `swift-coding-standards`、`swiftui-design-guidelines`、`system-integration`、
  `uikit-components`）均为本 skill 自带内容，frontmatter 中包含完整的
  MIT 条款引用，但本目录未附带独立的 `LICENSE` 文本。
- `MiniMax-OpenSource` 看起来像是为 OpenClaw/MiniMax 生态定制（命名风格类似
  `MiniMax-OpenSource/<skill-name>`），可能存在于内网/私有仓库或
  MiniMax 官方内部系统，但**对 SkillHub 而言无法独立验证**。

## 上传建议

1. **若可接受风险**（如内部/团队使用）：可按 `SKILL.md` 中 frontmatter 的
   `license: MIT` 声明入库。建议在 SkillHub 元数据中显式标注
   `source_repo_status: unverified_author_only_404`。
2. **若需对外公开发布**：建议先通过以下渠道之一确认协议：
   - clawhub 站内 `MiniMax-OpenSource` 账号私信，要求提供公开仓库地址
   - 查找 MiniMax 官方 OpenClaw 文档中是否列出该 skill 的源仓库
   - 直接联系 MiniMax 团队获取 `LICENSE` 文件原文
3. **不建议**：在未确认前将该 skill 标注为 `ready` 状态发布。
4. 入库时建议在 SkillHub 元数据中保留本 `LICENSE-NOTE.md`，并标记为
   `caution` 状态。

## 审查记录

详细审查过程见
`C:\Users\qq567\Desktop\codes\projects\ace_skills\_review_41_81\review_report_41_81.md`
第三章节（谨慎处理的 4 个）。
