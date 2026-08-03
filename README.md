# AI 文档智能管理中心-performance center专题

> **版本**: v1.1  
> **更新日期**: 2026-08-03  
> **仓库类型**: AI 辅助文档管理与知识沉淀系统
> **当前文档数**: 7 份 | **最后更新**: 见下方文档列表

---

## 📋 项目概述

Performance Center 是一个基于 **AI 驱动的智能化文档管理系统**，旨在通过结构化的方式组织、管理和优化技术文档、原型设计稿及项目资产。本仓库采用 **Git 版本控制** + **AI 协作工作流**，确保文档的**可追溯性**、**一致性**和**高效迭代**。

---

## 🎯 核心目标

| 目标维度 | 说明 |
|---------|------|
| **文档标准化** | 建立统一的文档规范、命名规则和目录结构 |
| **版本可追溯** | 通过 Git 记录每次修改的完整历史，支持回滚与对比 |
| **AI 协同优化** | 利用 AI 能力辅助文档生成、审查、摘要和多语言转换 |
| **知识资产沉淀** | 将分散的文档集中管理，形成可复用的知识库 |
| **协作效率提升** | 降低团队沟通成本，减少重复性文档工作 |

---

## 📁 目录结构与文档清单

```
Performance-center-
├── README.md                      # 本文件 - 项目说明与使用指南
├── docs/
│   ├── research/                  # 调研/竞品分析
│   │   ├── tableau-pulse-product-researchv3.md    # Tableau Pulse 产品调研 v3 (662行)
│   │   └── research-pc-tableau-benchmark-v1.0.md  # PC 对标 Tableau MECE分析表 v1.0
│   ├── guidelines/                # 开发规范与指导（⭐ 新增）
│   │   ├── git-commit-standard.md                 # Git 提交与文档管理规范 v1.0
│   │   ├── research-template.md                   # 产品调研文档模板
│   │   ├── benchmark-template.md                  # MECE对标分析表模板
│   │   └── priority-example.md                    # 优先级分级表示例
│   ├── priority/                  # 优先级/决策表
│   │   ├── pulse-priority-table.md               # Pulse 功能优先级分级表
│   │   └── pc-task-decision-table.md             # PC 任务决策表（做什么/不做什么）
│   ├── specifications/          # 技术规格说明书（待补充）
│   └── prototypes/              # 原型设计稿（待补充）
└── archives/                     # 历史归档
```

### 📄 文档索引

| 文档 | 类型 | 说明 | 优先级参考 |
|------|------|------|-----------|
| `tableau-pulse-product-researchv3.md` | 调研 | Tableau Pulse 完整产品调研 | 基础参考 |
| `research-pc-tableau-benchmark-v1.0.md` | 对标 | PC vs Tableau MECE功能对比 | P0-P2分级 |
| `pulse-priority-table.md` | 决策 | Pulse 自身能力优先级 | 核心vs辅助 |
| `pc-task-decision-table.md` | 决策 | PC 建设任务做什么/不做什么 | 行动指南 |
| `git-commit-standard.md` | 规范 | **提交前必读**：命名、commit message、检查清单 | 强制执行 |
| `research-template.md` | 模板 | 新调研文档的标准格式 | 复用模板 |
| `benchmark-template.md` | 模板 | MECE对标表的填写规范 | 复用模板 |

> ⚠️ **推送前必读**：`docs/guidelines/git-commit-standard.md`

---

## 🔧 AI 文档管理最佳实践

### 1️⃣ 文档命名规范

采用**语义化命名**，格式：`[类型]-[模块]-[描述]-[版本].[扩展名]`

**示例**：
- `spec-auth-oauth2-flow-v1.2.md` — 认证模块 OAuth2 规格文档 v1.2
- `prototype-dashboard-main-v1.html` — 仪表盘主页原型 v1
- `guide-code-review-standards.md` — 代码审查规范指南

### 2️⃣ Git 提交规范

遵循 [Conventional Commits](https://www.conventionalcommits.org/) 规范：

| 类型 | 说明 | 示例 |
|------|------|------|
| `feat` | 新功能 | `feat: 添加用户认证流程文档` |
| `fix` | 修复错误 | `fix: 修正 API 端点描述错误` |
| `docs` | 文档变更 | `docs: 更新原型设计交互说明` |
| `refactor` | 重构 | `refactor: 重组文档目录结构` |
| `style` | 格式调整 | `style: 统一 Markdown 标题层级` |

### 3️⃣ 文档编写原则

#### ✅ 推荐做法
- **模块化拆分**：单个文档控制在合理篇幅（建议 < 2000 行）
- **结构清晰**：使用一致的标题层级和列表格式
- **图文并茂**：关键流程配合图表说明
- **保持时效**：定期审查和更新过时内容
- **可搜索性**：添加适当的标签和关键词元数据

#### ❌ 避免事项
- 避免在文档中硬编码敏感信息（密码、密钥等）
- 避免过度嵌套的目录结构（建议不超过 3 层）
- 避免使用含糊的表述（如"稍后"、"可能"等）
- 避免同时多人编辑同一文档（防止冲突）

### 4️⃣ AI 协作工作流

```
┌─────────────┐    ┌─────────────┐    ┌─────────────┐
│   人工输入   │ -> │   AI 处理   │ -> │   人工审核   │
│ (需求/草稿) │    │ (生成/优化) │    │ (确认/修正) │
└─────────────┘    └─────────────┘    └─────────────┘
       │                  │                   │
       v                  v                   v
  明确需求          结构化输出          质量把关
  提供上下文        保持一致性          迭代优化
```

**关键环节**：
1. **需求明确化**：向 AI 提供充分的背景信息和期望输出格式
2. **输出审核**：AI 生成内容必须经过人工确认后方可入库
3. **增量迭代**：基于反馈持续优化文档质量
4. **版本标记**：重要变更记录到 CHANGELOG.md

---

## 📊 文档生命周期管理

```
新建草案 -> 审核评审 -> 正式发布 -> 维护更新 -> 归档废弃
   (Draft)   (Review)  (Released)  (Maintained)  (Archived)
```

各阶段标识：
- `[DRAFT]` — 草案阶段，内容可能变动
- `[REVIEW]` — 待评审，请求团队反馈
- `[STABLE]` — 已发布稳定版本
- `[DEPRECATED]` — 已废弃，仅供参考

---

## ⚠️ 使用须知

1. **权限控制**：本仓库为内部项目，请勿公开分享敏感信息
2. **分支策略**：
   - `main` — 主分支，仅合并经过验证的内容
   - `feature/*` — 功能开发分支
   - `docs/*` — 文档专项分支
3. **冲突解决**：修改前务必拉取最新代码，遇到冲突及时沟通
4. **备份机制**：重要文档建议额外备份至本地或其他存储

---

## 🛠️ 工具与技术栈

| 类别 | 推荐工具 |
|------|---------|
| **编辑器** | VS Code / Typora / MarkText |
| **版本控制** | Git + GitHub/GitLab |
| **AI 辅助** | CodeBuddy / Claude / GPT-4 |
| **图示绘制** | Mermaid / Draw.io / Excalidraw |
| **文档格式** | Markdown (.md) / HTML (.html) |

---

## 📞 联系与支持

如有问题或建议，请通过以下方式联系：
- **Issue 提交**：在仓库中创建 Issue
- **讨论交流**：Pull Request 评论区

---

## 📜 许可证

本项目仅供内部使用，未经授权不得外传。

---

*最后更新：2026-08-03 by AI Assistant (v1.1: 新增文档规范与模板)*
