# Skill 来源与协议说明：grill-me

- 上游源仓库：https://github.com/mattpocock/skills （目录 /grill-me/）
- 上游源文件：https://github.com/mattpocock/skills/tree/main/grill-me （SKILL.md，635 字节，经 jsDelivr 文件树核实）
- 开源协议：MIT（上游仓库根目录 LICENSE，版权人 Matt Pocock，2026）
- 本地 LICENSE：按上游 MIT 原文重建，版权行与上游一致
- 再分发结论：MIT 允许上传 skillhub，需保留本 LICENSE 版权声明
- 审查日期：2026-08-17
- 审查批次：skill_list_119.xlsx 序号 41-81（本 skill 序号 47）

## 典型用例（实测方式：方法论走查 + prompt 型交互演示）

- 输入：用户给出一个方案/设计（例："我打算把个人博客从 Hugo 迁移到 Astro，帮我 grill me"）
- 输出：按 SKILL.md 的 relentless interview 模式，逐层拆解决策分支（迁移动机、内容量、主题兼容、CI 变更、SEO 影响等），每个分支追问直到达成共识
- 质量评估：单文件 prompt 型 skill，结构清晰（决策树逐层追问 + 共识收敛），仅依赖 Read/Grep 工具，无外部依赖，触发词明确。质量良好。

## 备注

上游仓库同目录还包含 tdd、qa、write-a-prd 等 skill；本仓库根 LICENSE 为 MIT，覆盖全部目录。
