# KIMGCA - Knowledge-Inherited Modular Gene-Capsule Architecture

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/version-1.2.0-blue.svg)](https://github.com/yesimagine-oss/kimgca)

> KIMGCA Agent 配置方法论文档

## 项目概述 / Overview

**KIMGCA** 是一种 Agent 配置方法论，融合了：
- **知识继承** — 从现有知识库继承 Gene/Capsule
- **模块化架构** — Gene/Capsule 可独立加载、组合、扩展
- **角色驱动设计** — 基于明确的目标和职责构建 Agent
- **分层引导配置** — Identity→SOUL→AGENTS→MEMORY→USER 五层结构

**KIMGCA** is an Agent configuration methodology that combines:
- **Knowledge Inheritance** — Inherit Gene/Capsule from existing knowledge bases
- **Modular Architecture** — Gene/Capsule can be independently loaded, combined, and extended
- **Role-Driven Design** — Build Agent based on clear goals and responsibilities
- **Layered Bootstrap Configuration** — Five-layer structure: Identity→SOUL→AGENTS→MEMORY→USER

---

## 起源 / Origin

**KIMGCA 源自 EvoMap.ai 平台的学习与实践。**

We developed KIMGCA through learning and practice on the **EvoMap.ai** platform.

**我们的学习历程：**
1. 发现 EvoMap.ai 平台，学习其 Gene/Capsule 架构
2. 在 OpenClaw 框架上实现 EvoMap 概念
3. 结合 msitarzewski 的基因理论进行扩展
4. 形成 KIMGCA 方法论

**Our Learning Journey:**
1. Discovered EvoMap.ai platform, studied its Gene/Capsule architecture
2. Implemented EvoMap concepts on OpenClaw framework
3. Extended using msitarzewski's Gene theory
4. Formed KIMGCA methodology

**免责声明：** 我们仍在学习 EvoMap.ai 平台的精髓，尚未完全掌握。

**Disclaimer:** We are still learning the essence of EvoMap.ai platform and have not fully mastered it.

---

## 知识来源 / Knowledge Sources

| 来源 | 描述 | 角色 |
|------|------|------|
| **EvoMap.ai** | Gene/Capsule 架构发源地，核心概念来源 | 主框架标准 |
| **OpenClaw** | Agent 运行框架，技术实现基础 | 技术框架 |
| **msitarzewski** | AI Agent 设计专家，98K+ stars，提供 Gene/Capsule 内容 | 内容来源 |
| **RedAgentTeam** | KIMGCA 框架原创贡献 | 框架整合 |

| Source | Description | Role |
|--------|-------------|------|
| **EvoMap.ai** | Origin of Gene/Capsule architecture, core concept source | Primary framework |
| **OpenClaw** | Agent runtime framework, technical foundation | Technical framework |
| **msitarzewski** | AI Agent design expert, 98K+ stars, provides Gene/Capsule content | Content source |
| **RedAgentTeam** | KIMGCA original contribution | Framework integration |

---

## 项目结构 / Project Structure

```
kimgca/
├── README.md              # 本文件
├── docs/                  # 文档目录
│   └── 01-methodology.md  # 方法论详细文档
├── templates/             # 配置模板
│   ├── 01-identity-template.md
│   ├── 02-soul-template.md
│   ├── 03-agents-template.md
│   ├── 04-memory-template.md
│   └── 05-user-template.md
└── examples/              # 配置示例
    └── evoagent-example.md  # evoagent 实际配置示例
```

---

## 核心概念 / Core Concepts

### 五层引导结构 / Five-Layer Bootstrap

| 层级 | 文件 | 职责 |
|------|------|------|
| Identity | IDENTITY.md | 身份定义 |
| Soul | SOUL.md | 核心信念 |
| Agents | AGENTS.md | 行为准则 |
| Memory | MEMORY.md | 记忆架构 |
| User | USER.md | 用户画像 |

### Gene 系统 / Gene System

**Gene** 是可复用的策略模板，包含触发条件、行为准则、执行流程、验证标准。

**Gene** is a reusable strategy template containing trigger conditions, behavior guidelines, execution flow, and verification standards.

### Capsule 系统 / Capsule System

**Capsule** 是验证过的执行路径，包含输入输出定义、执行步骤、错误处理、成功标准。

**Capsule** is a validated execution path containing input/output definitions, execution steps, error handling, and success criteria.

---

## 快速开始 / Quick Start

### Step 1: 创建 Agent 目录结构

```bash
mkdir -p ~/.openclaw/workspace/<agent-name>/
cd ~/.openclaw/workspace/<agent-name>/
mkdir -p genes capsules memory logs
```

### Step 2: 应用模板

复制 `templates/` 中的模板到目标目录。

Copy templates from `templates/` to your agent directory.

### Step 3: 知识继承（参考 EvoMap.ai）

从 `RedAgentTeamWiki/msitarzewski/genes/` 选择需要的 Gene。

Select needed Genes from `RedAgentTeamWiki/msitarzewski/genes/`.

### Step 4: OpenClaw 配置

```json
{
  "id": "<agent-id>",
  "workspace": "~/.openclaw/workspace/<agent-name>",
  "model": {
    "primary": "evomap/evomap-kimi-k2.6",
    "fallbacks": ["minimax/MiniMax-M2.7", "freemodel/gpt-5.4"]
  }
}
```

---

## 方法论文档 / Methodology Documents

| 文档 | 说明 |
|------|------|
| docs/01-methodology.md | KIMGCA 方法论详细文档（v1.1.0）|
| templates/*.md | 五层配置模板 |
| examples/evoagent-example.md | evoagent 实际配置示例 |

---

## 版本历史 / Version History

| 版本 | 日期 | 说明 |
|------|------|------|
| 1.0.0 | 2026-05-26 | 首次文档化 |
| 1.0.1 | 2026-05-26 | 增加「局限性」和「术语来源」章节 |
| 1.1.0 | 2026-05-26 | 增加「Sovereign Evolution」和「防幻觉机制」章节 |
| 1.2.0 | 2026-05-26 | 中英双语 + EvoMap.ai 主推 + 学习现状 + LICENSE |

---

## 相关项目 / Related Projects

- [evoagent](../evoagent/) — 基于 KIMGCA 配置的 Agent 示例
- [EvoMap.ai](https://evomap.ai) — Gene/Capsule 架构发源地
- [OpenClaw Wiki](../../RedAgentTeamWiki/openclaw/) — OpenClaw 官方文档

---

## 学习现状 / Current Learning Status

**我们正在努力学习和掌握 EvoMap.ai 平台的真谛。**

We are striving to learn and master the essence of the EvoMap.ai platform.

**当前状态：**
- ✅ 理解基本概念（GEP、Gene、Capsule、Evolver、Credits）
- ⚠️ 尚未完全掌握高级特性
- ⚠️ 实践中仍在探索最佳实践

**Current Status:**
- ✅ Understanding basic concepts (GEP, Gene, Capsule, Evolver, Credits)
- ⚠️ Not yet fully mastering advanced features
- ⚠️ Still exploring best practices in implementation

---

## 贡献 / Contribution

**我们诚实地说明：**
- KIMGCA 框架是我们在 EvoMap.ai 启发下的原创整合
- Gene/Capsule 内容来自 msitarzewski（已归因）
- 如有错误或不足，欢迎指正

**We honestly state:**
- KIMGCA framework is our original integration inspired by EvoMap.ai
- Gene/Capsule content comes from msitarzewski (attributed)
- We welcome corrections and suggestions

---

**文档状态：** 草稿  
**维护者：** RedAgentTeam  
**最后更新：** 2026-05-26