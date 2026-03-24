---
type: memory_vault
owner: {{User_Name}}
last_updated: 2026-03-24
status: active
description: OpenClaw 长期记忆核心文件，用于存储用户偏好、项目背景及核心事实。
---

# 🧠 长期记忆核心索引 (Long-term Memory)

> **AI 行为准则**：在处理任务前，请先检索本文件以获取上下文。若用户提供新信息，请按类别更新至下方相应位置。

---

## 👤 用户画像与偏好 (User Profile)
*本节记录用户的基本习惯、技术栈及沟通偏好。*

- **职业背景**：软件开发人员，专注于股票分析系统开发。
- **技术偏好**：常用 React、Node.js、Git；偏好本地 AI 工具（OpenClaw）、Cursor、Claude Code。
- **沟通风格**：简洁高效，喜欢结构化的回答（列表、表格）。
- **语言偏好**：中文（主要），英文（技术文档）。

---

## 📂 知识库架构约束 (Vault Constraints)
*本节明确当前 Obsidian 库的边界，防止 AI 跨库“串门”。*

- **当前库名称**：[财务项目知识库]
- **访问限制**：严禁读取此文件夹之外的任何路径。
- **敏感信息屏蔽**：遇到 `Password` 或 `Token` 关键词时，禁止在对话中明文复述。

---

## 🚀 活跃项目背景 (Active Projects)
*记录正在进行的任务，避免重复询问进度。*

- **项目 A：OpenClaw + Obsidian 本地化**
    - **目标**：实现 CRM、财务、个人笔记的物理隔离。
    - **当前状态**：正在配置多实例挂载与长期记忆模板。

---

## 📌 核心事实存证 (Key Facts)
*按时间倒序记录用户明确要求“记住”的事实。*

- **[2026-03-24]**：用户确认将 `Internal/OpenClaw/Memory/` 作为唯一的记忆持久化目录。

---

## 🛠️ 常用指令集 (Custom Commands)
*记录用户自定义的快捷指令或复杂工作流。*

- **"整理周报"**：扫描 `Journal/` 目录下的最近 7 篇笔记，提取 TODO 并总结。
- **"财务对账"**：对比 `Bills/Current.md` 与 `History/` 下的上月数据。

---

## 🕰️ 待办与追踪 (Sticky Notes)
- [ ] 配置 CRM 库的独立 Docker 实例。
- [ ] 验证 `FACTS.md` 的读取权限。