# KIMGCA 工具链 / Tools

> KIMGCA 方法论使用的工具和技术栈

---

## 核心框架 / Core Framework

| 工具 | 说明 | 链接 |
|------|------|------|
| **OpenClaw** | Agent 运行时框架 | [OpenClaw Docs](https://docs.openclaw.ai) |
| **EvoMap.ai** | Gene/Capsule 架构发源地 | [EvoMap](https://evomap.ai) |

---

## 本地工具 / Local Tools

### Gene 系统

| 工具 | 说明 | 位置 |
|------|------|------|
| **Gene Enforcer** | Gene 自检脚本 | `/root/data/disk/GeneLab/scripts/` |
| **Auto Evolution** | 自动化轨迹自诊 | `/root/.openclaw/workspace/scripts/` |
| **RedGuard** | 错误监控扫描 | `/root/.openclaw/workspace/projects/redguard/` |

### 配置管理

| 工具 | 说明 |
|------|------|
| **openclaw config** | OpenClaw 配置管理 |
| **openclaw gateway** | Gateway 服务管理 |
| **openclaw security** | 安全审计 |

---

## 技能 / Skills

| 技能 | 说明 | 用于 |
|------|------|------|
| **github** | GitHub CLI 交互 | 仓库管理 |
| **weather** | 天气查询 | 日常助手 |
| **browser** | 浏览器自动化 | 网页操作 |
| **tavily-search** | 网络搜索 | 信息查询 |
| **tencent-docs** | 腾讯文档 | 文档协作 |

---

## 工作流工具 / Workflow Tools

| 工具 | 说明 |
|------|------|
| **cron** | 定时任务调度 |
| **sessions** | 多会话管理 |
| **message** | 消息通道 |

---

## 开发工具 / Development Tools

| 工具 | 说明 |
|------|------|
| **write** | 文件写入 |
| **read** | 文件读取 |
| **exec** | Shell 命令执行 |
| **browser** | 浏览器控制 |

---

## 推荐的工具链配置 / Recommended Setup

### 1. 安装 OpenClaw

```bash
npm install -g openclaw
```

### 2. 克隆 KIMGCA

```bash
git clone https://github.com/RedAgentTeam/kimgca.git
cd kimgca
```

### 3. 配置 Agent

参考 `templates/` 中的模板文件。

### 4. 安装技能（可选）

```bash
openclaw skills install github weather
```

---

## 版本要求 / Version Requirements

| 组件 | 最低版本 |
|------|----------|
| Node.js | v18+ |
| OpenClaw | 2026.4+ |

---

## 相关项目 / Related Projects

- [OpenClaw](https://github.com/openclaw/openclaw) - Agent 运行时
- [EvoMap.ai](https://evomap.ai) - Gene/Capsule 架构

---

**工具链持续更新中。**