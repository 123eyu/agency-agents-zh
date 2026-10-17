# 上游差异与开发建议

核对日期：2026-10-17。本报告的“主站”指英文上游 [msitarzewski/agency-agents](https://github.com/msitarzewski/agency-agents)，不是课程网站或在线专家库。

## 结论与范围

本地基线记录停留在 6 月，不能继续宣称已覆盖当前上游。当前页面核对发现角色增量、工具格式变化与安装能力差异。本次只比对公开 README 中取到的部分路径和本地脚本，不是完整 Git diff；下方缺失路径是待同步候选，不是最终新增数量。已有同名角色的正文变化仍需固定上游 commit 后逐项比较。

核对来源：[上游 README](https://github.com/msitarzewski/agency-agents/blob/main/README.md)、[上游目录](https://github.com/msitarzewski/agency-agents)、[中文仓库 issues](https://github.com/jnMetaCode/agency-agents-zh/issues)。页面可能更新或存在缓存；本次未取得可复核的最新完整 commit SHA。

## 已完成

- 根据开放 issue #97 的标题新增嵌入式算法工程师、嵌入式应用工程师；详情页及两条评论未成功读取，未声称满足评论中的额外要求。
- 两个角色分别聚焦数值与资源验证、设备业务与恢复，保留现有固件、Linux 驱动、IoT、FPGA 与测试角色的职责边界。
- 本地规模由 277 更新为 283（含第一批 2 个原创与本批 4 个中文精编），原创由 64 更新为 66；工程部 47、营销部 43。
- 更新简繁入口、名单、速查表、包描述与上游状态；线上专家库数量由线上页面决定，去除过时的固定人数。
- CI 执行计数检查，补齐 GIS / security 变更的 lint 触发范围。

- 第二批已补充 RAG、身份与访问、支付与计费、测试自动化四个中文精编角色；正文按上游职责整理，未宣称逐行完整翻译。
- 第三批完整翻译桌面应用工程师、AI 生成代码安全审计师、密钥与凭据治理工程师三个角色，原文固定于上游 commit `652b269`（`652b2692f8d8ec2b1f1a38e559073e287dfdc469`）。本地规模更新为 286（翻译 220 / 原创 66）；工程部 48、安全部 12。
- 第四批完整翻译 API 平台工程师、数据库可靠性工程师、平台工程师三个角色，原文同样固定于 `652b269`。本地规模更新为 289（翻译 223 / 原创 66）；工程部 51。
- 第五批完整翻译开发者工具工程师、FinOps 工程师、隐私工程师三个角色，原文同样固定于 `652b269`。本地规模更新为 292（翻译 226 / 原创 66）；工程部 54。
- 第六批完整翻译国际化工程师、知识图谱工程师、搜索相关性工程师三个角色，原文同样固定于 `652b269`。本地规模更新为 295（翻译 229 / 原创 66）；工程部 57。
- 第七批完整翻译 LLM 后训练工程师、实时协作工程师、WebAssembly 工程师三个角色，原文同样固定于 `652b269`。本地规模更新为 298（翻译 232 / 原创 66）；工程部 60。

## 后续优先级

### AO 联动验证发现

本批 4 个角色已通过 AO 现有 `dist/cli/install.js` 收集器识别；工程部 Cursor dry-run 返回 47 个且未写入配置。角色库自身计数与 Cursor 转换均为 283 个。

AO 修复已于 2026-10-17 提交到 agency-orchestrator `main`（`efa8839`，尚未发版）：说明文档按完整文件名匹配，跳过隐藏文件与隐藏目录，并新增安全分类与 dry-run 回归用例。7 项安装器测试与测试类型检查通过；修复版扫描本库识别 298 个角色，包含全部 12 个安全角色。

修复前，AO 收集器排除文件的正则是 `/^(README|CONTRIBUTING|LICENSE|SECURITY)/i`，会误伤全部 `security-*` 角色，且未跳过全部隐藏目录。已发布的 App / npm 包在 AO 下次发版前仍是旧行为。README 生态表中 AO 的"276 专家"待 AO 发版后再更新。

| 优先级 | 工作 | 原因与验收条件 |
|--------|------|----------------|
| P2 | 角色库独立脚本的部门、单角色、角色清单筛选与 dry-run | 上游 README 已提供这些入口；本库脚本没有。配套 agency-orchestrator 的 ao install 已有 category 与 dryRun，不应当作 App 缺失能力重复开发。先补角色内容与同步链路，再按独立脚本用户需求安排。 |
| P2 | 检查 Gemini CLI / OpenCode / Hermes 适配 | 本库 Gemini 仍为扩展、Hermes 为 skills；AO 自有 Gemini 安装器已指向 .gemini/agents。OpenCode 的本库实现实际已使用复数 agents，旧的是脚本头部说明；不能据此认定运行路径有缺陷。工具格式仍需按具体实现核查。 |
| P1 | 继续翻译剩余路径候选 | 桌面与 AI 代码安全角色已完成（第三批）；其余候选按开发场景优先，逐个读取固定 commit 的完整正文后翻译与验收。 |
| P1 | 固定上游 commit，建立路径映射与内容哈希清单 | 先建立可复核差异，再更新同步基线；目录存在不代表正文已同步。 |
| P2 | 引入 healthcare / research 部门 | 需同步转换、安装、lint、发布目录与名单；医疗内容需明确适用语境，不能直接替换成中国法规结论。 |
| P2 | 评估 Kimi / Osaurus / Vibe / DeepSeek Harness 适配 | 上游提供入口，本地暂未支持；工具数量更多不代表能力覆盖上游，需按工具逐项对比。 |
| P2 | 评估 divisions.json / tools.json / runbooks.json | 上游已采用元数据与团队清单，本地仍有多份目录硬编码；有利于减少遗漏。 |
| P3 | 并行转换与安装 | 先保证筛选、格式兼容与可回归验证，再优化执行耗时。 |

## 已确认的路径候选

以下路径出现在本次读取的上游 README 中，本地没有同路径文件，且已排除 5 个已知映射。仍需人工检查是否存在其他同义角色；这不是完整上游文件清单。

- `design/design-ui-finish-gate-reviewer.md`
- `engineering/engineering-ats-validator-architect.md`
- `engineering/engineering-data-visualization-engineer.md`
- `engineering/engineering-drupal-performance.md`
- `engineering/engineering-gaussdb-expert.md`
- `engineering/engineering-iot-fleet-engineer.md`
- `engineering/engineering-mobile-release-engineer.md`
- `engineering/engineering-network-engineer.md`
- `engineering/engineering-pdf-engine-architect.md`
- `engineering/engineering-rust-refactoring-specialist.md`
- `engineering/engineering-section-508-specialist.md`
- `engineering/engineering-servicenow-developer-mentor.md`
- `engineering/engineering-universal-document-compiler.md`
- `engineering/engineering-uswds-developer.md`
- `engineering/engineering-video-streaming-engineer.md`
- `engineering/engineering-wordpress-performance.md`
- `healthcare/healthcare-clinical-evidence-agent.md`
- `healthcare/healthcare-innovation-strategist.md`
- `healthcare/healthcare-sovereign-health-systems-agent.md`
- `marketing/marketing-developer-community-builder.md`
- `product/product-dx-engineer.md`
- `research/research-synthesist.md`
