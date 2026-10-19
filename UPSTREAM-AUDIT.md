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
- 第八批完整翻译视频流媒体工程师、移动端发布工程师、数据可视化工程师三个角色，原文同样固定于 `652b269`。本地规模更新为 301（翻译 235 / 原创 66）；工程部 63。
- 第九批（2026-10-18）完整翻译 IoT 设备群工程师、Rust 重构专家、PDF 引擎架构师三个角色，原文同样固定于 `652b269`。IoT 设备群工程师侧重已上线设备群的运维，与本地原创的 IoT 方案架构师（整体方案设计）分工不同。本地规模更新为 304（翻译 238 / 原创 66）；工程部 66。
- 第十批完整翻译通用文档编译器、ATS 校验架构师、UI 收尾审查员三个角色，原文同样固定于 `652b269`。本地规模更新为 307（翻译 241 / 原创 66）；工程部 68、设计部 11。同时修正 CATALOG 历史遗漏：补齐公司经营部 7 个角色及 3 个原创角色、改正 2 个已迁移的旧路径、金融部计数改为 9，并将 CATALOG 一致性接入计数检查。
- 第十一批完整翻译开发者社区建设专家（营销部）、DX 工程师（产品部）两个角色，原文同样固定于 `652b269`。两者与本地已有的开发者布道师有部分交集，但分别聚焦社区运营与上手摩擦；上游三者并存。本地规模更新为 309（翻译 243 / 原创 66）；营销部 44、产品部 6。通用类候选至此全部完成。
- 第十二批完整翻译网络工程师（Cisco/Juniper/Palo Alto，与本地原创的华为/华三版国内网络工程师互补）、GaussDB 专家、WordPress 性能工程师三个角色，原文同样固定于 `652b269`。本地规模更新为 312（翻译 246 / 原创 66）；工程部 71。
- 第十三批完整翻译 Drupal 性能工程师和研究综合专家，原文同样固定于 `652b269`；新建 `research/` 部门，并同步转换、安装、lint、发布文件列表和 CI 触发范围。同时修正 Windows 版 `install.ps1`、`convert.ps1` 部门列表遗漏 `gis` 与 `security` 的问题（修复前 Windows 安装少 25 个角色）。本地规模更新为 314（翻译 248 / 原创 66），部门 21 个；工程部 72、研究部 1。
- 第十四批完整翻译 healthcare 部门三个角色（临床证据专家、医疗创新战略师、主权卫生体系专家），原文同样固定于 `652b269`；新建 `healthcare/` 部门并同步转换、安装、lint、发布文件列表和 CI 触发范围。三个角色开头注明海外监管语境的适用范围，并指向本地原创的医疗健康营销合规师。本地规模更新为 317（翻译 251 / 原创 66），部门 22 个；医疗健康部 3。
- 第十五批完整翻译 Section 508 无障碍专家、ServiceNow 开发导师、USWDS 开发工程师三个角色，原文同样固定于 `652b269`；两个美国联邦专属角色开头注明适用范围。本地规模更新为 320（翻译 254 / 原创 66）；工程部 75。至此本报告列出的路径候选已全部翻译完成。
- 第十六批完整翻译全量比对新发现的简历定制师、总体规划架构师、代码库考古专家三个角色（前两者是 ATS 校验架构师的协作对象），原文同样固定于 `652b269`。本地规模更新为 323（翻译 257 / 原创 66）；专项部 61。
- 第十七批完整翻译统计学家（学术部）、游戏经济设计师（游戏开发部）、专注音乐架构师（专项部），原文同样固定于 `652b269`。本地规模更新为 326（翻译 260 / 原创 66）；学术部 7、游戏开发部 21、专项部 62。
- 第十八批完整翻译年迈父母照护助手、FedRAMP 与 RMF 合规工程师，原文同样固定于 `652b269`。本地规模更新为 328（翻译 262 / 原创 66）；专项部 64。至此上游 `652b269` 的全部角色路径均已有本地对应。

## 后续优先级

### AO 联动验证发现

本批 4 个角色已通过 AO 现有 `dist/cli/install.js` 收集器识别；工程部 Cursor dry-run 返回 47 个且未写入配置。角色库自身计数与 Cursor 转换均为 283 个。

AO 修复已于 2026-10-17 提交到 agency-orchestrator `main`（`efa8839`，尚未发版）：说明文档按完整文件名匹配，跳过隐藏文件与隐藏目录，并新增安全分类与 dry-run 回归用例。7 项安装器测试与测试类型检查通过；修复版扫描本库识别 328 个角色，包含全部 12 个安全角色。

修复前，AO 收集器排除文件的正则是 `/^(README|CONTRIBUTING|LICENSE|SECURITY)/i`，会误伤全部 `security-*` 角色，且未跳过全部隐藏目录。已发布的 App / npm 包在 AO 下次发版前仍是旧行为。README 生态表中 AO 的"276 专家"待 AO 发版后再更新。

| 优先级 | 工作 | 原因与验收条件 |
|--------|------|----------------|
| P2 | 角色库独立脚本的部门、单角色、角色清单筛选与 dry-run | 上游 README 已提供这些入口；本库脚本没有。配套 agency-orchestrator 的 ao install 已有 category 与 dryRun，不应当作 App 缺失能力重复开发。先补角色内容与同步链路，再按独立脚本用户需求安排。 |
| P2 | 检查 Gemini CLI / OpenCode / Hermes 适配 | 本库 Gemini 仍为扩展、Hermes 为 skills；AO 自有 Gemini 安装器已指向 .gemini/agents。OpenCode 的本库实现实际已使用复数 agents，旧的是脚本头部说明；不能据此认定运行路径有缺陷。工具格式仍需按具体实现核查。 |
| P1 | 处理 3 个上游已不存在的本地翻译角色 | 路径层面的待译角色已全部完成；删除、改标或去重前需确认上游历史。 |
| P1 | 建立内容哈希清单，复核已有同名角色的正文差异 | 已固定 `652b269` 并完成路径级全量比对；目录存在不代表正文已同步，同名角色的正文变化仍需逐项比较。 |
| P2 | 引入 healthcare / research 部门（均已完成） | 需同步转换、安装、lint、发布目录与名单；医疗内容需明确适用语境，不能直接替换成中国法规结论。 |
| P2 | 评估 Kimi / Osaurus / Vibe / DeepSeek Harness 适配 | 上游提供入口，本地暂未支持；工具数量更多不代表能力覆盖上游，需按工具逐项对比。 |
| P2 | 评估 divisions.json / tools.json / runbooks.json | 上游已采用元数据与团队清单，本地仍有多份目录硬编码；有利于减少遗漏。 |
| P3 | 并行转换与安装 | 先保证筛选、格式兼容与可回归验证，再优化执行耗时。 |

## 已确认的路径候选

原 README 摘录的候选已在第三至十五批全部翻译完成。

### 2026-10-19 全量文件树比对（固定 commit `652b269`）

通过 GitHub API 获取上游 `652b269` 的完整文件树（未截断），逐个比对角色路径。上游 282 个角色路径中，本地缺少同路径文件的有 15 个：其中 5 个已在 UPSTREAM.md 记录为路径映射，`specialized/chief-financial-officer.md`、`specialized/specialized-chief-of-staff.md` 已迁移到本地 `company/`。真正缺失的有 8 个（此前的 README 摘录未覆盖到），已在第十六至十八批全部翻译完成。


反向比对：本地标为"翻译"的 254 个角色中，有 3 个在上游 `652b269` 中已找不到同名文件，需确认上游是否已删除或改名，再决定保留、改标原创或去重：

- `engineering/engineering-security-engineer.md`：上游提交 `8237f99`（2026-06-04，新增安全部）将其改名迁移为 `security/security-architect.md` 并重新区分职责；本地两者并存。
- `engineering/engineering-threat-detection-engineer.md`：上游同一提交 `8237f99` 将其改名迁移为 `security/security-threat-detection-engineer.md`；本地两者并存，属迁移后遗留的副本。是否删除待维护者确认。
- ~~`specialized/technical-translator-agent.md`~~：已核实为本仓库 2026-03-26 新增（提交 `729dcda`），上游从无此路径，原先误标为"翻译"，2026-10-19 已改标为"原创"。

### 2026-10-19 同名角色正文同步（`3f78a30` → `652b269`）

用 GitHub 比较接口列出上游从历史同步基线 `3f78a30` 到 `652b269` 之间改过的角色文件（433 次提交）。结果：
- 37 个只有文件属性变化、正文无改动，无需处理。
- 11 个只把标题 "Role Definition" 改为 "Identity & Role Definition"，中文标题本就另行翻译，不同步：`marketing-content-creator`、`marketing-growth-hacker`、`paid-media-*`（7 个）、`product-feedback-synthesizer`、`product-trend-researcher`。
- 30 个有实质改动，需要逐个对照中文版同步。

已同步：
- `engineering-incident-response-commander`、`engineering-technical-writer`：外层 markdown 示例改用四个反引号，避免嵌套代码块提前截断
- `game-development/technical-artist`：LOD 校验补上层级数量检查
- `marketing-private-domain-operator`：首次互动数改为按用户去重计数
- `engineering-solidity-smart-contract-engineer`：链差异列表补上 XDC

待同步（25 个）：`design-inclusive-visuals-specialist`、`design-ux-architect`、`design-whimsy-injector`、`engineering-autonomous-optimization-architect`、`engineering-backend-architect`、`engineering-data-engineer`、`engineering-database-optimizer`、`engineering-devops-automator`、`engineering-email-intelligence-engineer`、`engineering-embedded-firmware-engineer`、`engineering-feishu-integration-developer`、`engineering-git-workflow-master`、`engineering-prompt-engineer`、`engineering-rapid-prototyper`、`engineering-voice-ai-integration-engineer`、`engineering-wechat-mini-program-developer`、`blender-addon-engineer`、`unreal-multiplayer-architect`、`unreal-systems-engineer`、`marketing-agentic-search-optimizer`、`marketing-ai-citation-strategist`、`marketing-carousel-growth-engine`、`marketing-seo-specialist`、`product-behavioral-nudge-engine`、`project-management-jira-workflow-steward`。其中部分本地译文可能晚于上游改动、已包含新内容，需逐个核对后再改。
