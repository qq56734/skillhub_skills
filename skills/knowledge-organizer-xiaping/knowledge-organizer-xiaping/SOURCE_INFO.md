# Skill 来源与协议说明：knowledge-organizer-xiaping

- 上游源仓库：https://github.com/cjke84/knowledge-organizer
- 核实方式：jsDelivr 文件树（data.jsdelivr.com）逐文件比对，本地 scripts/ 目录 16 个脚本与上游一致（check_duplicate.py、feishu_kb.py、ima_kb.py、knowledge_sync.py 等），上游另有 tests/ 目录未随本地分发
- 开源协议：MIT（上游仓库根目录 LICENSE，版权人 Jingke Chen，2026）
- 本地 SKILL.md frontmatter 亦自带 `license: MIT` 声明，与上游一致
- 本地 LICENSE：按上游 MIT 原文重建，版权行与上游一致
- 再分发结论：MIT 允许上传 skillhub，需保留本 LICENSE 版权声明
- 审查日期：2026-08-17
- 审查批次：skill_list_119.xlsx 序号 41-81（本 skill 序号 56）

## 典型用例

- 输入：一批文章/笔记素材（Markdown/URL/微信收藏等），目标知识库根目录
- 输出：导入归档、自动打标签、查重、生成摘要、关联推荐；可同步 Obsidian / 飞书知识库 / 腾讯 IMA
- 质量评估：脚本体系完整（导入/去重/同步/状态管理均有实现），上游带 pytest 测试（test_skill_contract.py 等 16 个测试文件）。工程化程度高。注意：飞书/IMA 同步需要 FEISHU_APP_ID、FEISHU_APP_SECRET、IMA_OPENAPI_APIKEY 等环境变量；纯本地 Obsidian 模式无需任何 key。

## API key 说明

- Obsidian 本地模式：无需 key（可完整验证）
- 飞书同步：FEISHU_APP_ID / FEISHU_APP_SECRET / FEISHU_ACCESS_TOKEN / FEISHU_KB_ID 等
- 腾讯 IMA 同步：IMA_OPENAPI_CLIENTID / IMA_OPENAPI_APIKEY
