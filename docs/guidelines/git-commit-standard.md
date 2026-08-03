# Performance Center 文档管理与 Git 提交规范

> 版本：v1.0  
> 更新日期：2026-08-03  
> 适用范围：Performance Center Git 仓库所有文档提交

---

## 一、Git 提交前检查清单（强制）

推送前**必须**确认以下项目：

| # | 检查项 | 验证方式 | 通过条件 |
|---|--------|----------|----------|
| 1 | 文件命名合规 | 目测检查 | 符合 `[类型]-[模块]-[描述]-[版本].[扩展名]` |
| 2 | Commit Message 规范 | 检查提交信息 | 以 `feat/fix/docs/refactor/style` 开头 |
| 3 | 无敏感信息 | 搜索 password/token/secret/key | 无匹配结果 |
| 4 | 本地已同步远程 | `git fetch && git status` | 无 ahead/behind 或已处理 |
| 5 | 文件放入正确目录 | `ls docs/` | 文档在 `docs/` 下对应子目录 |

---

## 二、Commit Message 格式

```
<type>(<scope>): <subject>
```

### Type 枚举

| Type | 用途 | 示例 |
|------|------|------|
| `docs` | 文档新增/修改 | `docs: 添加 Tableau Pulse 调研 v3` |
| `feat` | 新功能/新能力 | `feat: 添加指标语义中心设计文档` |
| `fix` | 修复错误 | `fix: 修正对标表中优先级标注` |
| `refactor` | 重构文档结构 | `refactor: 按 MECE 原则重组对标表` |
| `style` | 格式调整 | `style: 统一 Markdown 标题层级`

### Scope 建议
- 文档类：省略或用文件名缩写（如 `pulse`, `benchmark`）
- 多文件：省略 scope

---

## 三、文件命名规范

**格式**：`[类型]-[模块]-[描述]-[版本].[扩展名]`

| 类型前缀 | 适用场景 | 示例 |
|----------|---------|------|
| `research` | 调研/竞品分析 | `research-pc-tableau-benchmark-v1.0.md` |
| `spec` | 技术规格 | `spec-metric-definition-v1.0.md` |
| `prototype` | 原型设计 | `prototype-dashboard-main-v1.html` |
| `guide` | 指导/规范 | `guide-doc-naming-convention.md` |
| `priority` | 优先级表 | `priority-pulse-capabilities-v1.0.md` |

**版本号规则**：
- 初始版本：`v1.0`
- 小改：`v1.1`, `v1.2`
- 大改：`v2.0`

---

## 四、目录结构规范

```
Performance-center-
├── README.md                    # 项目说明
├── docs/
│   ├── research/                # 调研/竞品分析 ← 调研文档放这里
│   │   ├── tableau-pulse-product-researchv3.md
│   │   └── research-pc-tableau-benchmark-v1.0.md
│   ├── specifications/          # 技术规格说明书
│   ├── prototypes/              # 原型设计稿
│   ├── guidelines/              # 开发规范与指导 ← 规范模板放这里
│   │   ├── research-template.md         # 调研文档模板
│   │   ├── benchmark-template.md        # MECE对标表模板
│   │   └── priority-example.md          # 优先级分级示例
│   └── priority/                # 优先级/决策表
│       ├── pulse-priority-table.md
│       └── pc-task-decision-table.md
├── assets/                      # 静态资源
└── archives/                    # 历史归档
```

---

## 五、标准推送流程

```bash
# 1. 进入仓库
cd <repo-path>

# 2. 拉取最新（避免冲突）
git pull --rebase origin main

# 3. 放入正确目录并添加
cp <local-file> docs/<category>/<proper-name>.md
git add docs/<category>/<proper-name>.md

# 4. 规范提交
git commit -m "docs: 添加 [简短中文描述]"

# 5. 推送
git push origin main
```

---

## 六、冲突处理

如果遇到推送拒绝：

```bash
# 方案1：rebase（推荐）
git pull --rebase origin main
git push

# 方案2：merge（如果 rebase 复杂）
git pull origin main
git push
```

---

## 七、注意事项

1. **永远不要直接在 README.md 中添加业务内容** — 只更新元信息
2. **敏感信息检查是强制的** — 密码、token、内部 URL 不能入库
3. **大文件（>1MB）应放入 assets/ 而非 docs/**
4. **每次推送前先 pull** — 避免不必要的冲突
5. **commit message 用中文** — 方便团队阅读
6. **版本号只升不降** — v1.0 → v1.1 → v2.0

---

## 八、文档研究工作流速查

### 调研文档必含章节
1. 一句话结论
2. 解决什么问题
3. 核心能力拆解
4. AI 能力详解
5. 对 PC 的借鉴
6. 官方资料链接

### MECE 对标表必填列
| 列名 | 必填 | 说明 |
|------|:----:|------|
| # | ✅ | 序号 |
| 问题域 | ✅ | MECE 分类维度 |
| 功能名称 | ✅ | 具体能力点 |
| 出处 | ✅ | 来源 + 章节 |
| 功能说明+边界 | ✅ | 做什么 + 不做什么 |
| PC 参考落点 | ✅ | 如何落地 |
| 建设分类 | ✅ | 全新/现有升级/PoC |
| 优先级 | ✅ | P0/P1/P2 |

### 优先级定义
- **P0**：核心灵魂，缺一不可（通常 3-5 项）
- **P1**：体验层，有它才好用（通常 4-8 项）
- **P2**：进阶层，锦上添花（数量不限）

---

*详细模板请参考同目录下的 template 文件*
