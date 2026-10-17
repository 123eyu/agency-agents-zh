# 上游版本追踪

记录本项目对应的上游 [agency-agents](https://github.com/msitarzewski/agency-agents) 版本，方便同步更新。

## 当前状态（2026-10-17 核对）

- **上游仓库**：https://github.com/msitarzewski/agency-agents
- **历史同步基线**：2026-06-16，`3f78a30`；上一次批量同步记录为 2026-06-18。
- **本地实际角色数**：**295**，其中目录标注翻译 **229**、原创 **66**。来源分类以 [AGENT-LIST.md](AGENT-LIST.md) 为准，不等同于当前上游覆盖数。
- **覆盖状态**：**尚未追平当前上游**。上游 README 已出现本地缺少的角色、新部门与安装能力，详见 [本次差异审计](UPSTREAM-AUDIT.md)。历史“全部覆盖”结论只适用于当时基线。
- **核对限制**：本次通过上游公开页面核对，未获取完整 Git tree 与固定 commit，不能据此证明文件内容一致，也不更新历史同步 commit。
- **本次完成**：根据 [issue #97](https://github.com/jnMetaCode/agency-agents-zh/issues/97) 标题补充嵌入式算法、嵌入式应用两个原创角色；同步简繁 README、名单、速查表与包描述，修正部门和来源计数，并将计数检查接入 CI。

## 翻译覆盖

| 本地来源分类 | 数量 |
|-------------|------|
| 翻译 | 229 |
| 原创 | 66 |
| **合计** | **295** |

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

## 2026-10-17 第三至六批完整翻译

逐段完整翻译 12 个上游角色（保留代码示例，注释译为中文；省略本地不使用的 `vibe` 字段）。原文固定于上游 commit [`652b269`](https://github.com/msitarzewski/agency-agents/tree/652b2692f8d8ec2b1f1a38e559073e287dfdc469)，可按此版本复核。

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
