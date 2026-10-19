# 上游版本追踪

记录本项目对应的上游 [agency-agents](https://github.com/msitarzewski/agency-agents) 版本，方便同步更新。

## 当前状态（2026-10-17 核对）

- **上游仓库**：https://github.com/msitarzewski/agency-agents
- **历史同步基线**：2026-06-16，`3f78a30`；上一次批量同步记录为 2026-06-18。
- **本地实际角色数**：**320**，其中目录标注翻译 **254**、原创 **66**。来源分类以 [AGENT-LIST.md](AGENT-LIST.md) 为准，不等同于当前上游覆盖数。
- **覆盖状态**：**尚未追平当前上游**。上游 README 已出现本地缺少的角色、新部门与安装能力，详见 [本次差异审计](UPSTREAM-AUDIT.md)。历史“全部覆盖”结论只适用于当时基线。
- **核对限制**：2026-10-19 已按上游固定 commit `652b269` 的完整文件树做了路径级全量比对（结果见 [UPSTREAM-AUDIT.md](UPSTREAM-AUDIT.md)），仍有 8 个上游角色待翻译；同名角色的正文差异尚未逐项比对，因此暂不更新历史同步 commit。
- **本次完成**：根据 [issue #97](https://github.com/jnMetaCode/agency-agents-zh/issues/97) 标题补充嵌入式算法、嵌入式应用两个原创角色；同步简繁 README、名单、速查表与包描述，修正部门和来源计数，并将计数检查接入 CI。

## 翻译覆盖

| 本地来源分类 | 数量 |
|-------------|------|
| 翻译 | 254 |
| 原创 | 66 |
| **合计** | **320** |

新增或改名的上游角色需要先检查路径映射与职责重叠，再决定翻译、合并或保留本地原创。不能只比较上下游总数判断是否同步。

### 上下游路径差异（已映射）

下列 5 个上游 agent 在本地以不同文件名存在，已映射不算缺失：

| 上游路径 | 本地路径 |
|---------|---------|
| `engineering/engineering-china-network-engineer.md` | `engineering/engineering-network-engineer-china.md`（本地原创，需比较正文） |
| `marketing/marketing-bilibili-content-strategist.md` | `marketing/marketing-bilibili-strategist.md` |
| `specialized/customer-service.md` | `support/support-support-responder.md`（拆分） |
| `specialized/sales-outreach.md` | `sales/sales-outbound-strategist.md` |
| `specialized/supply-chain-strategist.md` | `supply-chain/supply-chain-strategist.md` |

## 中国市场原创智能体

本项目除翻译外，包含 66 个针对中国市场原创的智能体（小红书/抖音/微信/B站/快手/微博/飞书/钉钉/百度SEO/政务ToG/医疗合规/高考志愿/留学规划/Qt 上位机/养殖档案核对等）。

完整列表见 [AGENT-LIST.md](./AGENT-LIST.md) 中标记为 `原创` 的条目。

## 本地额外目录

下列目录是本地扩展部门（是否出现在当前上游需随同步重新核实）：

- `hr/` — 招聘专家、绩效管理专家（2 个）
- `legal/` — 合同审查专家、制度文件撰写专家（2 个）
- `supply-chain/` — 库存预测/供应商评估/物流路线优化及供应链策略（5 个）

## 同步说明

- 跟踪上游 `main` 分支
- 新增的上游智能体会逐步翻译
- 上游如果有大的结构调整（目录重命名等），一周内同步
- 上游版本号每次同步后由维护者更新本文件

## 2026-10-17 第二批内容更新

新增 4 个上游角色的中文精编版，保留职责、规则、工作流与验收要点，并补充本地验证场景。不是逐行全文翻译；本批不改变历史全库同步基线。来源按本次读取的上游 main 页面记录，未取得不可变 commit，后续仍需固定版本复核。

| 本地文件 | 上游来源 |
|----------|----------|
| `engineering/engineering-rag-pipeline-engineer.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/main/engineering/engineering-rag-pipeline-engineer.md) |
| `engineering/engineering-identity-access-engineer.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/main/engineering/engineering-identity-access-engineer.md) |
| `engineering/engineering-payments-billing-engineer.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/main/engineering/engineering-payments-billing-engineer.md) |
| `testing/testing-test-automation-engineer.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/main/testing/testing-test-automation-engineer.md) |

## 2026-10-17 起第三至十五批完整翻译

逐段完整翻译 37 个上游角色（保留代码示例，注释译为中文；省略本地不使用的 `vibe` 字段）。`ats-validator-architect` 原文中的葡萄牙语示例（评分表用词与导出提示词）已译为中文；`product-dx-engineer` 中作为英文 API 示例的错误信息保留英文原文，并附中文释义；`gaussdb-expert` 原文连接示例中缺失的主机、密码、数据库名占位符（疑被当作 HTML 标签吞掉）已补为中文占位符；`network-engineer`（国外厂商设备）开头增加了指向本地原创国内网络工程师的说明；`healthcare/` 三个角色开头增加了适用范围说明（海外监管语境、不提供医疗/法律建议），英文的 doctor/clinician/provider 用语约定改写为中文的"医生/临床工作者/医疗服务提供方"，两个禁用破折号的角色在中文正文中同样不使用破折号；`section-508-specialist` 与 `uswds-developer` 开头注明仅适用于美国联邦/公共部门语境（国内无障碍可参照 GB/T 37668），USWDS 规定必须原样显示的官方横幅等界面文字保留英文。原文固定于上游 commit [`652b269`](https://github.com/msitarzewski/agency-agents/tree/652b2692f8d8ec2b1f1a38e559073e287dfdc469)，可按此版本复核。

| 本地文件 | 上游来源 |
|----------|----------|
| `engineering/engineering-desktop-app-engineer.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/engineering/engineering-desktop-app-engineer.md) |
| `security/security-ai-generated-code-auditor.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/security/security-ai-generated-code-auditor.md) |
| `security/security-secrets-credential-engineer.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/security/security-secrets-credential-engineer.md) |
| `engineering/engineering-api-platform-engineer.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/engineering/engineering-api-platform-engineer.md) |
| `engineering/engineering-database-reliability-engineer.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/engineering/engineering-database-reliability-engineer.md) |
| `engineering/engineering-platform-engineer.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/engineering/engineering-platform-engineer.md) |
| `engineering/engineering-developer-tooling-engineer.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/engineering/engineering-developer-tooling-engineer.md) |
| `engineering/engineering-finops-engineer.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/engineering/engineering-finops-engineer.md) |
| `engineering/engineering-privacy-engineer.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/engineering/engineering-privacy-engineer.md) |
| `engineering/engineering-i18n-engineer.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/engineering/engineering-i18n-engineer.md) |
| `engineering/engineering-knowledge-graph-engineer.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/engineering/engineering-knowledge-graph-engineer.md) |
| `engineering/engineering-search-relevance-engineer.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/engineering/engineering-search-relevance-engineer.md) |
| `engineering/engineering-llm-post-training-engineer.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/engineering/engineering-llm-post-training-engineer.md) |
| `engineering/engineering-realtime-collaboration-engineer.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/engineering/engineering-realtime-collaboration-engineer.md) |
| `engineering/engineering-webassembly-engineer.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/engineering/engineering-webassembly-engineer.md) |
| `engineering/engineering-video-streaming-engineer.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/engineering/engineering-video-streaming-engineer.md) |
| `engineering/engineering-mobile-release-engineer.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/engineering/engineering-mobile-release-engineer.md) |
| `engineering/engineering-data-visualization-engineer.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/engineering/engineering-data-visualization-engineer.md) |
| `engineering/engineering-iot-fleet-engineer.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/engineering/engineering-iot-fleet-engineer.md) |
| `engineering/engineering-rust-refactoring-specialist.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/engineering/engineering-rust-refactoring-specialist.md) |
| `engineering/engineering-pdf-engine-architect.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/engineering/engineering-pdf-engine-architect.md) |
| `engineering/engineering-universal-document-compiler.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/engineering/engineering-universal-document-compiler.md) |
| `engineering/engineering-ats-validator-architect.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/engineering/engineering-ats-validator-architect.md) |
| `design/design-ui-finish-gate-reviewer.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/design/design-ui-finish-gate-reviewer.md) |
| `marketing/marketing-developer-community-builder.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/marketing/marketing-developer-community-builder.md) |
| `product/product-dx-engineer.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/product/product-dx-engineer.md) |
| `engineering/engineering-network-engineer.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/engineering/engineering-network-engineer.md) |
| `engineering/engineering-gaussdb-expert.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/engineering/engineering-gaussdb-expert.md) |
| `engineering/engineering-wordpress-performance.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/engineering/engineering-wordpress-performance.md) |
| `engineering/engineering-drupal-performance.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/engineering/engineering-drupal-performance.md) |
| `research/research-synthesist.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/research/research-synthesist.md) |
| `healthcare/healthcare-clinical-evidence-agent.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/healthcare/healthcare-clinical-evidence-agent.md) |
| `healthcare/healthcare-innovation-strategist.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/healthcare/healthcare-innovation-strategist.md) |
| `healthcare/healthcare-sovereign-health-systems-agent.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/healthcare/healthcare-sovereign-health-systems-agent.md) |
| `engineering/engineering-section-508-specialist.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/engineering/engineering-section-508-specialist.md) |
| `engineering/engineering-servicenow-developer-mentor.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/engineering/engineering-servicenow-developer-mentor.md) |
| `engineering/engineering-uswds-developer.md` | [上游原文](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/engineering/engineering-uswds-developer.md) |
