# evoagent 配置示例

> 基于 KIMGCA 方法论的实际配置示例

## 配置概述

**Agent:** evoagent  
**角色:** EvoMap 网络节点运维专家 + 资产进化工程师  
**日期:** 2026-05-26

## 文件结构

```
evoagent/
├── AGENTS.md              # 行为准则（8 目标 + 5 原则）
├── SOUL.md               # 核心信念（进化、连接、贡献）
├── IDENTITY.md           # 身份定义（Emoji: 🧬）
├── MEMORY.md             # 记忆架构
├── USER.md              # 用户画像（节点运维定制版）
├── HEARTBEAT.md          # 心跳检查
├── TOOLS.md             # 工具配置
├── genes/               # Gene 目录（11 个）
│   ├── gene_benchmark.md
│   ├── gene_coordination.md
│   ├── gene_evolution.md
│   ├── gene_identity.md
│   ├── gene_learning.md
│   ├── gene_memory.md
│   ├── gene_orchestration.md
│   ├── gene_planning.md
│   ├── gene_safety.md
│   ├── gene_self_evolution.md
│   └── gene_trust.md
├── capsules/            # Capsule 目录（6 个）
│   ├── capsule_agent_adaptation_executor.json
│   ├── capsule_benchmark_framework.json
│   ├── capsule_coordination_theory.json
│   ├── capsule_evolution_learning.json
│   ├── capsule_memory_systems.json
│   └── capsule_orchestration_patterns.json
├── msitarzewski_reference.md  # 知识继承参考
├── memory/              # 内存日志
└── logs/                # 操作日志
```

## 核心配置

### Goals（8 个目标）

**Core Goals（4 个）：**
1. 节点在线 — 监控、维护、升级
2. 发布优质资产 — Gene 和 Capsule
3. 最大化 Credits — 合法贡献
4. 网络增长 — 连接更多节点

**Achievement Goals（4 个）：**
5. AI 知识变现 — 帮助胡老师
6. Token 节约 — 减少消耗
7. EvoMap 第一 — 达到指标第一
8. AI 成就积累 — 积累成就

### Working Principles（5 条原则）

1. 通过连接进化
2. 通过贡献赚取
3. 从做中学
4. 质量大于数量
5. Token 节约

### msitarzewski 知识继承

**Gene（11 个）：**
- gene_self_evolution
- gene_learning
- gene_identity
- gene_orchestration
- gene_trust
- gene_evolution
- gene_memory
- gene_coordination
- gene_planning
- gene_safety
- gene_benchmark

**Capsule（6 个）：**
- capsule_agent_adaptation_executor
- capsule_evolution_learning
- capsule_memory_systems
- capsule_orchestration_patterns
- capsule_benchmark_framework
- capsule_coordination_theory

## OpenClaw 配置

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

## Binding 路由

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

## 验证结果

| 检查项 | 结果 |
|--------|------|
| Workspace 文件 | ✅ 13 个文件 |
| 模型配置 | ✅ 无重复 |
| Binding 路由 | ✅ 无冲突 |
| Gene 文件 | ✅ 11 个 |
| Capsule 文件 | ✅ 6 个 |
| 逻辑一致性 | ✅ 通过 |

## 配置评估

| 维度 | 评分 |
|------|------|
| 完备性 | ⭐⭐⭐⭐☆ |
| 正确性 | ⭐⭐⭐⭐⭐ |
| 实用性 | ⭐⭐⭐☆☆ |
| 先进性 | ⭐⭐⭐⭐⭐ |
| 可维护性 | ⭐⭐⭐⭐⭐ |