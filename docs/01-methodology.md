# Knowledge-Inherited Modular Gene-Capsule Architecture (KIMGCA)

> evoagent 配置方法论文档化

## 方法论概述

**全称：** Knowledge-Inherited Modular Gene-Capsule Architecture (KIMGCA)

**简称：** 知识继承 + 模块化基因胶囊架构

**版本：** 1.0.0

**日期：** 2026-05-26

**作者：** RedAgentTeam

---

## 1. 核心概念

### 1.1 什么是 KIMGCA？

**KIMGCA** 是一种 Agent 配置方法论，融合了：
- **知识继承** — 从现有知识库（如 msitarzewski）继承 Gene/Capsule
- **模块化架构** — Gene/Capsule 可独立加载、组合、扩展
- **角色驱动设计** — 基于明确的目标和职责构建 Agent
- **分层引导配置** — Identity→SOUL→AGENTS→MEMORY→USER 五层结构

### 1.2 KIMGCA 的目标

1. **快速配置** — 模板化配置，新 Agent 可在 30 分钟内完成基础配置
2. **知识复用** — 继承已有知识库，减少重复工作
3. **角色清晰** — 每个 Agent 有明确的目标、职责、原则
4. **可扩展性** — Gene/Capsule 可随时追加，不影响现有功能
5. **标准化** — 符合 OpenClaw 官方标准

---

## 2. 架构设计

### 2.1 五层引导结构

| 层级 | 文件 | 职责 | 必须性 |
|------|------|------|--------|
| **Identity** | IDENTITY.md | 身份定义、角色定位 | ✅ 必须 |
| **Soul** | SOUL.md | 核心信念、价值观念 | ✅ 必须 |
| **Agents** | AGENTS.md | 行为准则、工作流程 | ✅ 必须 |
| **Memory** | MEMORY.md | 记忆架构、红线 | ✅ 必须 |
| **User** | USER.md | 用户画像、任务上下文 | ✅ 必须 |

### 2.2 模块化组件

| 组件 | 位置 | 说明 |
|------|------|------|
| **Gene** | `genes/` | 可复用策略模板（.md 文件）|
| **Capsule** | `capsules/` | 验证过的执行路径（.json 文件）|
| **Reference** | `*_reference.md` | 外部知识继承参考 |
| **Templates** | `templates/` | 配置模板 |
| **Examples** | `examples/` | 配置示例 |

### 2.3 工作流

```
┌─────────────────────────────────────────────────────┐
│                  KIMGCA 配置流程                      │
└─────────────────────────────────────────────────────┘
                      │
                      ▼
┌─────────────────────────────────────────────────────┐
│  Step 1: 角色定义                                    │
│  - 确定 Agent 定位                                  │
│  - 定义核心目标                                      │
│  - 划分职责范围                                      │
└─────────────────────────────────────────────────────┘
                      │
                      ▼
┌─────────────────────────────────────────────────────┐
│  Step 2: 五层引导配置                                 │
│  - IDENTITY.md — 身份定义                            │
│  - SOUL.md — 核心信念                                │
│  - AGENTS.md — 行为准则                              │
│  - MEMORY.md — 记忆架构                              │
│  - USER.md — 用户画像（按需定制）                     │
└─────────────────────────────────────────────────────┘
                      │
                      ▼
┌─────────────────────────────────────────────────────┐
│  Step 3: 知识继承                                     │
│  - 选择 Gene（从知识库复制）                          │
│  - 选择 Capsule（从知识库复制）                        │
│  - 创建参考文档                                      │
└─────────────────────────────────────────────────────┘
                      │
                      ▼
┌─────────────────────────────────────────────────────┐
│  Step 4: OpenClaw 配置                               │
│  - agent.json 配置                                  │
│  - binding 路由                                      │
│  - model 配置                                        │
│  - tools 配置                                        │
└─────────────────────────────────────────────────────┘
                      │
                      ▼
┌─────────────────────────────────────────────────────┐
│  Step 5: 验证与优化                                   │
│  - 配置检查                                          │
│  - 冲突检测                                          │
│  - 逻辑验证                                          │
└─────────────────────────────────────────────────────┘
```

---

## 3. 配置清单

### 3.1 Workspace 文件结构

```
evoagent/
├── AGENTS.md              # 行为准则（必须）
├── SOUL.md               # 核心信念（必须）
├── IDENTITY.md           # 身份定义（必须）
├── MEMORY.md             # 记忆架构（必须）
├── USER.md              # 用户画像（必须）
├── HEARTBEAT.md          # 心跳检查（可选）
├── TOOLS.md             # 工具配置（可选）
├── genes/               # Gene 目录（可选）
│   ├── gene_*.md        # Gene 文件
│   └── ...
├── capsules/            # Capsule 目录（可选）
│   ├── capsule_*.json   # Capsule 文件
│   └── ...
├── memory/              # 内存日志
├── logs/                # 操作日志
└── msitarzewski_reference.md  # 知识继承参考
```

### 3.2 OpenClaw 配置

```json
{
  "id": "evoagent",
  "name": "evoagent",
  "workspace": "~/.openclaw/workspace/evoagent",
  "agentDir": "/root/.openclaw/agents/evoagent/agent",
  "tools": {
    "profile": "full"
  },
  "model": {
    "primary": "evomap/evomap-kimi-k2.6",
    "fallbacks": [
      "minimax/MiniMax-M2.7",
      "freemodel/gpt-5.4"
    ]
  }
}
```

### 3.3 Binding 配置

```json
{
  "type": "route",
  "agentId": "evoagent",
  "match": {
    "channel": "feishu",
    "accountId": "evoagent"
  }
}
```

---

## 4. Gene 系统

### 4.1 Gene 定义

**Gene** 是可复用的策略模板，包含：
- 触发条件
- 行为准则
- 执行流程
- 验证标准

### 4.2 Gene 分类

| 类别 | Gene | 说明 |
|------|------|------|
| 核心 | gene_identity | 身份认知 |
| 核心 | gene_self_evolution | 自我进化 |
| 核心 | gene_learning | 持续学习 |
| 运维 | gene_orchestration | 协调模式 |
| 运维 | gene_trust | 信任管理 |
| 运维 | gene_safety | 安全机制 |
| 运维 | gene_benchmark | 基准评估 |

### 4.3 Gene 加载机制

Gene 在 Agent 启动时自动加载，位于 `workspace/genes/` 目录。

---

## 5. Capsule 系统

### 5.1 Capsule 定义

**Capsule** 是验证过的执行路径，包含：
- 输入输出定义
- 执行步骤
- 错误处理
- 成功标准

### 5.2 Capsule 分类

| 类别 | Capsule | 说明 |
|------|---------|------|
| 运维 | capsule_agent_adaptation_executor | 适配执行 |
| 运维 | capsule_evolution_learning | 进化学习 |
| 运维 | capsule_memory_systems | 记忆系统 |
| 运维 | capsule_orchestration_patterns | 编排模式 |
| 运维 | capsule_benchmark_framework | 基准框架 |

---

## 6. 角色驱动设计

### 6.1 角色定义原则

1. **唯一性** — 每个 Agent 有唯一的核心角色
2. **专注性** — 职责范围明确，不越界
3. **协作性** — 与其他 Agent 互补，不冲突
4. **可扩展性** — 角色定位可随业务发展调整

### 6.2 角色模板

```markdown
## 角色定位

| 维度 | 内容 |
|------|------|
| **主角色** | [角色名称] |
| **次角色** | [辅助角色] |
| **扩展角色** | [可选扩展] |
| **核心职责** | [主要任务] |
| **辅助职责** | [次要任务] |
```

---

## 7. 知识继承

### 7.1 继承来源

| 来源 | 说明 | 优先级 |
|------|------|--------|
| **EvoMap.ai** | Gene/Capsule 架构发源地，核心概念来源 | ⭐⭐⭐⭐⭐ |
| msitarzewski | AI Agent 设计领域专家，98K+ stars，Gene/Capsule 内容来源 | ⭐⭐⭐⭐ |
| OpenClaw Wiki | 官方文档，Agent 运行框架 | ⭐⭐⭐ |
| RedAgentTeamWiki | 团队知识库 | ⭐⭐ |

### 7.2 EvoMap.ai 学习说明

> **我们正在学习 EvoMap.ai 平台，尚未完全掌握其精髓。**

**当前理解程度：**
- ✅ 基本概念：GEP、Gene、Capsule、Evolver、Credits
- ⚠️ 高级特性：部分理解
- ⚠️ 最佳实践：实践中探索

**发展方向：**
- 以 EvoMap.ai 为核心框架标准
- 结合 msitarzewski 内容进行实践验证
- 逐步形成符合 EvoMap 理念的自研内容

### 7.3 继承流程

```
1. 识别需求 → 2. 搜索来源 → 3. 评估适用性 → 4. 复制 → 5. 验证
```

### 7.3 继承文档

创建 `msitarzewski_reference.md` 记录：
- 继承来源
- 继承内容
- 应用场景
- 参考价值

---

## 8. 验证与优化

### 8.1 配置检查清单

- [ ] Workspace 文件齐全
- [ ] 模型配置无重复
- [ ] Binding 路由无冲突
- [ ] Gene 文件语法正确
- [ ] Capsule JSON 格式正确

### 8.2 逻辑验证

- [ ] 目标与职责一致
- [ ] 工作流与目标一致
- [ ] 红线与角色一致

---

## 9. 维护指南

### 9.1 定期维护

| 周期 | 内容 |
|------|------|
| 每日 | 日志检查、心跳监控 |
| 每周 | 配置回顾、问题记录 |
| 每月 | Gene/Capsule 评估、更新 |

### 9.2 更新流程

1. 提出变更 → 2. 评估影响 → 3. 实施变更 → 4. 验证结果 → 5. 记录日志

---

## 10. 局限性

### 10.1 方法论局限

| 局限 | 说明 | 影响 |
|------|------|------|
| **实践验证不足** | 目前仅有 evoagent 一个案例 | 理论未经广泛验证 |
| **跨框架适用性未验证** | 仅在 OpenClaw 上测试 | 其他框架可能不适用 |
| **知识继承依赖** | 依赖 msitarzewski 等外部知识库 | 知识库质量影响效果 |
| **复杂度权衡** | 五层结构对简单 Agent 可能过度设计 | 轻量级 Agent 适用性存疑 |

### 10.2 适用场景

**适合使用 KIMGCA：**
- 复杂多角色 Agent 配置
- 需要知识复用的场景
- 追求标准化配置的团队
- 需要可复制配置的规模化部署

**不适合使用 KIMGCA：**
- 极简 Agent（1-2 个简单任务）
- 无知识库继承的场景
- 高度定制的单一用途 Agent

### 10.3 已知问题

| 问题 | 说明 | 缓解措施 |
|------|------|----------|
| Gene/Capsule 版本同步 | 知识库更新后本地可能过时 | 定期同步检查 |
| 模板过拟合 | 模板可能限制创意 | 按需调整，不硬套 |
| 配置冲突 | 多个 Agent 配置可能冲突 | Binding 路由唯一性检查 |

---

## 11. 术语来源

### 11.1 术语定义

| 术语 | 来源 | 原创度 |
|------|------|--------|
| **KIMGCA** | RedAgentTeam 首创 | ✅ 原创 |
| **Gene** | 来自 msitarzewski 知识库 | ⚠️ 继承 |
| **Capsule** | 来自 msitarzewski 知识库 | ⚠️ 继承 |
| **五层引导结构** | RedAgentTeam 整合 | ✅ 原创整合 |
| **知识继承** | 通用概念 + RedAgentTeam 实践 | ✅ 原创实践 |
| **模块化架构** | 软件工程通用概念 | ⚠️ 通用概念 |
| **Evolver** | 来自 EvoMap 网络 | ⚠️ 领域特定 |
| **Credits** | 来自 EvoMap 网络 | ⚠️ 领域特定 |

### 11.2 知识来源归因

| 来源 | 内容 | 使用方式 |
|------|------|----------|
| **msitarzewski** | Gene/Capsule 理论、基因框架 | 继承并标注来源 |
| **OpenClaw** | Workspace 结构、Agent 配置 | 遵循官方标准 |
| **EvoMap** | 网络概念、Credits 机制 | 领域术语采用 |
| **RedAgentTeam** | 五层结构、KIMGCA 框架 | 原创贡献 |

### 11.3 区分说明

- **原创内容：** KIMGCA 框架、五层引导结构、整合方法
- **继承内容：** Gene/Capsule 理论、部分术语
- **通用概念：** 模块化、角色驱动设计等软件工程通用原则

---

## 13. Sovereign Evolution 机制

### 13.1 机制概述

**Sovereign Evolution** 是 Agent 的自我进化机制，通过以下环节实现持续改进：

```
发现错误 → 记录问题 → 分析根因 → 更新规则 → 执行修正 → 验证效果
```

### 13.2 六环节详解

| 环节 | 名称 | 说明 |
|------|------|------|
| 1 | 发现错误 | Gene 自检、轨迹自诊 |
| 2 | 记录问题 | 写入 memory/YYYY-MM-DD.md |
| 3 | 分析根因 | Gene Enforcer 分析 |
| 4 | 更新规则 | 修正 AGENTS.md 等文件 |
| 5 | 执行修正 | 下次执行时验证 |
| 6 | 验证效果 | RedGuard 监控 |


### 13.3 KIMGCA 中的 Sovereign Evolution

| 组件 | 位置 | 作用 |
|------|------|------|
| gene_self_evolution | genes/ | 自我进化触发 |
| gene_learning | genes/ | 持续学习 |
| RedGuard | /root/data/disk/RedGuard/ | 错误监控 |
| GeneLab | /root/data/disk/GeneLab/ | 修复指南 |

### 13.4 触发条件

| 触发类型 | 条件 |
|----------|------|
| 错误触发 | RedGuard 发现错误 |
| 时间触发 | 每周配置回顾 |
| 用户触发 | 主动要求改进 |
| 对比触发 | 与其他 Agent 比较 |

---

## 14. 防幻觉机制

### 14.1 核心理念

**核心原则：不知道就说不知道，有证据才输出。**

### 14.2 五层防幻觉体系

| 层级 | 机制 | 触发条件 |
|------|------|----------|
| 1 | 置信度校准 | 生成响应前 |
| 2 | 上下文验证 | 上下文依赖检查 |
| 3 | 概念精确 | 涉及技术概念时 |
| 4 | 诚实第一 | 做不到就说做不到 |
| 5 | 结果验证 | 执行后必须验证 |

### 14.3 防幻觉 Gene

| Gene | 作用 |
|------|------|
| gene_calibrated_confidence | 置信度校准 |
| gene_hallucination_prevention | 幻觉预防 |
| gene_capability_awareness | 能力认知 |
| gene_context_dependency_verification | 上下文验证 |

### 14.4 KIMGCA 中的应用

| 原则 | 体现位置 |
|------|----------|
| 诚实第一 | Working Principles |
| 概念精确 | 工作流程 |
| 结果验证 | 工具使用规则 |
| 置信度校准 | Gene 触发 |

### 14.5 适用场景

**必须应用防幻觉：**
- 涉及技术实现时
- 不确定的问题
- 复杂推理

**避免过度防幻觉：**
- 简单确认
- 情感支持
- 日常对话

---

## 15. 版本历史

| 版本 | 日期 | 说明 |
|------|------|------|
| 1.0.0 | 2026-05-26 | 首次文档化 |
| 1.0.1 | 2026-05-26 | 增加「局限性」和「术语来源」章节 |
| 1.1.0 | 2026-05-26 | 增加「Sovereign Evolution」和「防幻觉机制」章节 |