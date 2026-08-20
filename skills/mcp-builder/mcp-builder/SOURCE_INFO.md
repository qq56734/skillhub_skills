# Skill 来源与协议说明：mcp-builder

- 上游源仓库：https://github.com/anthropics/skills（Anthropic 官方 skills 仓库，目录 /skills/mcp-builder/）
- 核实方式：jsDelivr 抓取 /skills/mcp-builder/LICENSE.txt 原文（200 状态，11357 字节）
- 开源协议：Apache-2.0（版权人 Anthropic, PBC，2026）
- 本地 LICENSE.txt：按上游 Apache-2.0 原文重建，版权行与上游一致；本地 SKILL.md frontmatter 中 "license: Complete terms in LICENSE.txt" 与该文件对应
- 再分发结论：Apache-2.0 允许上传 skillhub；要求再分发时附带本许可证副本、修改文件需标注变更（若后续有改动）
- 审查日期：2026-08-17
- 审查批次：skill_list_119.xlsx 序号 41-81（本 skill 序号 66）

## 典型用例

- 输入：需求描述（例："做一个访问内部天气 API 的 MCP server，Python 实现"）
- 输出：按 SKILL.md 指南产出 MCP server 骨架（FastMCP/Python 或 MCP SDK/TypeScript），含工具设计、错误处理、评估脚本（scripts/evaluation.py + example_evaluation.xml）
- 质量评估：指南型 skill，含 4 个 reference 文档（Python/Node 服务器最佳实践、评估方法）与可运行的评估脚本；内容来自 modelcontextprotocol.io 官方规范与官方 SDK README。结构完整、权威性高。质量优秀。

## API key 说明

无需 API key（生成代码所需的连接脚本 scripts/connections.py 在实际连接 MCP server 时按目标服务而定）。
