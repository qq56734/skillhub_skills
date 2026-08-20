# Skill 来源与协议说明：landing-page-generator

- 上游源仓库：https://github.com/jezweb/claude-skills
- 上游源文件：plugins/frontend/skills/landing-page/SKILL.md（经 jsDelivr 抓取原文核实，200 状态）
- 开源协议：MIT（上游仓库根目录 LICENSE，版权人 Jeremy Dawes (Jezweb)，2025）
- 本地 LICENSE：按上游 MIT 原文重建，版权行与上游一致
- 版本差异说明：本地版本为上游的本地化改写版（增加 description_zh/description_en 字段、version 1.0.0），核心工作流（brief 收集 -> 单文件 HTML 生成 -> section 模式 -> 响应式/暗色模式/SEO 规范）与上游一致。MIT 允许修改与再分发，保留版权声明即可
- 再分发结论：允许上传 skillhub，需保留本 LICENSE 版权声明
- 审查日期：2026-08-17
- 审查批次：skill_list_119.xlsx 序号 41-81（本 skill 序号 57）

## 典型用例（实测产物见 _review_41_81/test_runs/landing_page_demo.html）

- 输入：业务简报（产品名、价值主张、目标受众、CTA、品牌色，例："Acme Plumbing，24/7 应急管道服务，Get a Quote"）
- 输出：单文件自包含 HTML 落地页（Tailwind CDN、响应式、三态暗色切换、语义化标签、OG meta、FAQ 手风琴、Schema.org 标记）
- 质量评估：prompt 型 skill 但规范非常细（section 模式、a11y、性能、色板接入、变体表齐全），按其规范实测生成的 demo 结构完整、无 JS 依赖核心内容、可直接部署。质量良好。

## API key 说明

无需任何 API key。
