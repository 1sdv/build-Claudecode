# 深入 Claude Code 源码：从架构到实践，构建你自己的 AI 编程代理

> 一门面向开发者的系统课程，通过逐层剖析 Claude Code v2.1.88 的真实源码，系统掌握 AI 编程代理的工程实现，并通过三个完整可落地的实战项目把所学应用起来。

---

## 这门课讲什么？

Claude Code 是 Anthropic 推出的旗舰级 AI 编程代理——它不只是聊天机器人，而是一个能读文件、写代码、执行命令、调度多个子代理协作的**完整工程系统**。

本课程通过 **7 大模块、19 个核心章节、3 个实战项目**，带你完整掌握：

- **AI 代理的核心引擎**：Agent 循环、AsyncGenerator 流式架构、StreamingToolExecutor 并发执行
- **工具系统的全貌**：40+ 个内置工具、Tool 接口的 20+ 方法、buildTool 工厂模式
- **上下文与记忆**：三层上下文模型、四种压缩策略、SessionMemory 跨会话记忆、DreamTask
- **权限与安全**：5 种权限模式、3 种处理器、27 个 Hook 事件、Hook 基础设施全解
- **MCP 协议生态**：8 种传输类型、5 大原语、OAuth 与 XAA 认证、官方注册中心
- **多代理协作**：7 种 Task 类型、Swarm 系统、Coordinator 模式、Agent Teams
- **Claude Agent SDK**：双接口模式、装饰器工具注册、V2 Session API

每章都有**真实源码引用 + 文件路径行号**、**配图说明**、**动手练习**、**源码对照表**。

---

## 完整课程目录

### 开篇

| 章节 | 标题 | 核心内容 |
|------|------|---------|
| 开篇 | **课前准备——环境搭建与源码导览** | 获取源码、40+ 目录全景、阅读方法论、学习路径 |

### 模块一：架构与启动

| 章节 | 标题 | 核心内容 |
|------|------|---------|
| Ch01 | **AI 编程代理全景图** | 范式对比、设计哲学、七大子系统架构 |
| Ch02 | **CLI 启动流程：从命令行到 REPL** | Commander.js、四阶段初始化、多环境适配 |
| Ch03 | **Agent 主循环：query() 的 while(true)** | QueryEngine、AsyncGenerator 管道、终止条件、错误恢复 |

### 模块二：工具系统

| 章节 | 标题 | 核心内容 |
|------|------|---------|
| Ch04 | **Tool 抽象与注册机制** | Tool 接口 20+ 方法、ToolUseContext、40+ 工具分类 |
| Ch05 | **核心工具深度剖析** | BashTool、FileEditTool、AgentTool、Grep/Glob、WebFetch |
| Ch06 | **流式执行引擎：StreamingToolExecutor** | 并发安全、串行/并行分区、AbortController 传播 |

### 模块三：上下文与记忆

| 章节 | 标题 | 核心内容 |
|------|------|---------|
| Ch07 | **对话上下文三层架构** | System Prompt 组装、CLAUDE.md 五级加载、AGENTS.md 兼容 |
| Ch08 | **上下文压缩四策略** | Snip / MicroCompact / AutoCompact / SessionMemoryCompact |
| Ch09 | **记忆系统与智能文档** | SessionMemory、MagicDocs、AgentSummary、DreamTask |

### 模块四：权限与安全

| 章节 | 标题 | 核心内容 |
|------|------|---------|
| Ch10 | **权限系统：五模式 + 多路竞赛** | useCanUseTool、3 种处理器、createResolveOnce、通道权限 |
| Ch11 | **Hooks 系统：27 事件 × 5 处理器** | command/http/mcp_tool/prompt/agent、Hook 基础设施 |

### 模块五：扩展与生态

| 章节 | 标题 | 核心内容 |
|------|------|---------|
| Ch12 | **MCP 协议全解：传输层 → 五大原语 → OAuth** | 8 种传输、Tools/Resources/Prompts/Sampling/Elicitation、PKCE、XAA |
| Ch13 | **Skills / Plugins / Commands 扩展体系** | 6 种 Skill 来源、Plugin 生命周期、ToolSearch 延迟加载 |
| Ch14 | **终端 UI 与状态管理（React/Ink）** | Ink 组件树、AppState pub/sub、UI 与 Agent 循环解耦 |

### 模块六：多代理与高级主题

| 章节 | 标题 | 核心内容 |
|------|------|---------|
| Ch15 | **多代理系统：Tasks / Swarm / Coordinator / Agent Teams** | 7 种 Task、14 个 Swarm 文件、Coordinator 6 段架构 |
| Ch16 | **Feature Flags / Analytics / SDK 入口** | GrowthBook、Agent SDK 双接口、装饰器工具、V2 API |

### 模块七：实战项目

| 章节 | 标题 | 核心内容 |
|------|------|---------|
| Ch17 | **项目一：从零构建 MiniAgent** | 800 行 TypeScript：Agent 循环 + 4 工具 + 权限 + 上下文 |
| Ch18 | **项目二：开发自定义 MCP Server** | 600 行 TypeScript：3 Tools + 2 Resources + 1 Prompt |
| Ch19 | **项目三：构建多代理协作系统** | 1000 行 TypeScript：Coordinator + 3 Workers (Security/Performance/Style) |

### 结束语

| 章节 | 标题 | 核心内容 |
|------|------|---------|
| 结束语 | **回顾与展望** | 8 条贯穿原则、Claude Code 演进趋势、MCP 生态未来、进一步学习路径 |

---

## 学完能做什么？

完成本课程后，你将具备：

- ✅ 理解 Claude Code 全部核心子系统的设计意图与实现细节
- ✅ 独立构建一个功能完备的 AI 编程代理（含 Tool 注册、权限控制、上下文管理、流式执行）
- ✅ 开发自定义 MCP Server 并接入 Claude Code 生态
- ✅ 搭建多代理协作系统（Coordinator + Worker + Task 调度）
- ✅ 将 Claude Agent SDK 集成到自己的产品/CI/CD 流水线
- ✅ 跟上 AI 编程代理领域的快速演进

---

## 三个实战项目预览

| 项目 | 章节 | 规模 | 难度 | 关键技术 |
|------|------|------|------|---------|
| MiniAgent | Ch17 | ~800 行 TypeScript | ⭐⭐ | Agent 循环、Tool 抽象、上下文管理、权限 |
| 自定义 MCP Server | Ch18 | ~600 行 TypeScript | ⭐⭐⭐ | MCP 协议、Tools/Resources/Prompts、stdio + HTTP |
| 多代理协作系统 | Ch19 | ~1000 行 TypeScript | ⭐⭐⭐⭐ | Coordinator、Worker、Task 调度、SendMessage |

每个项目都提供：完整 `package.json`、`tsconfig.json`、所有源文件、运行命令、测试用例、与 Claude Code 源码的对照表。

---

## 适合谁学？

- 有 TypeScript/Node.js 基础的开发者
- 想理解 Claude Code 内部实现原理的用户
- 正在构建或计划构建自己的 AI 编程代理的工程师
- 对 LLM 应用开发（Tool Calling、Agent Loop、MCP）感兴趣的人
- 想把 Claude Agent SDK 用到生产系统的团队

### 前置要求

- TypeScript 基础（能读懂泛型、async/await、装饰器模式）
- 终端基本操作（npm、git、shell）
- 了解 LLM API 基本概念（prompt、completion、tool_use）
- 不要求 React 经验（涉及时会讲解）

---

## 技术栈

课程涉及的核心技术：

| 依赖 | 用途 |
|------|------|
| `@anthropic-ai/sdk` | Anthropic Claude API |
| `@anthropic-ai/claude-agent-sdk` | Claude Agent SDK |
| `@modelcontextprotocol/sdk` | MCP 协议官方 SDK |
| TypeScript 5.x | 主要语言 |
| React + Ink | 终端 UI |
| commander | CLI 解析 |
| zod | Schema 验证 |
| AsyncGenerator | 流式数据管道核心 |

---

## 源码版本

本课程基于网上流传的 **Claude Code v2.1.88** 源码深度分析（约 30,000+ 行教程内容），感谢 linux.do 社区的信息来源。

---

## 课程数据

- **章节总数**：21 个教学单元（开篇 + 19 章 + 结束语）
- **正文规模**：约 30,000+ 行 Markdown
- **配图占位符**：60+ 处（适配 baoyu-infographic / baoyu-image-gen 生成）
- **源码引用**：每章都有真实文件路径与行号
- **实战项目**：3 个完整可落地的工程

---

## 许可

本课程内容采用 CC BY-NC-SA 4.0 许可协议。

---

## 课程作者

jiji262 · jiguofei@msn.com

如有错误或改进建议，欢迎提交 issue 或 PR。
