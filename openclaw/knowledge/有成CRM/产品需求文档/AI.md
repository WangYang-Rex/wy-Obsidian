---
title: "AI"
tags:
  - 有成CRM
  - PRD
  - .
created: 2026-03-24
source: 钉钉文档
original_url: https://alidocs.dingtalk.com/i/nodes/P7QG4Yx2Jp7NZxpnheqy9eY7V9dEq3XD?utm_scene=team_space
node_id: P7QG4Yx2Jp7NZxpnheqy9eY7V9dEq3XD
exported_at: 2026-03-22
---

# AI

> 🔗 **原文链接**：[AI - 钉钉文档](https://alidocs.dingtalk.com/i/nodes/P7QG4Yx2Jp7NZxpnheqy9eY7V9dEq3XD?utm_scene=team_space)

## **Agentic AI**

规划-决策-执行-评估/**感知-决策-执行-进化**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0bmARRkNnw1/img/46140ad1-59e7-4797-b08a-76282709b24d.png?Expires=1774164917&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=oT%2BcNy%2BdymBMuhZdESDnZBMCJdI%3D "")‘

一个Agentic系统，越是由LLM决定其行为方式，就越具有“自主性”。围绕规划、记忆、工具与感知四大核心模块，我们来看看基于LLM的Agentic AI进化关键技术。

**规划模块的关键技术包括：**

分层任务推理：基于LLM进行全局规划，结合思维图谱和强化学习（RL），实现目标的多粒度拆解与动态路径优化。

因果推理增强：结合结构因果关系和经验数据，预判动作的长期影响，避免短视决策。

多Agent实时协作：采用多Agent实时协作、共享记忆、多Agent对抗等技术，实现多Agent任务分配与冲突消解。

**记忆模块的关键技术包括：**

长期记忆压缩：存储关键历史信息，结合自注意力机制实现高效检索与关联。

短期记忆管理：采用缓存保留对话状态与环境上下文，支持多轮交互连贯性。

知识蒸馏与更新：通过持续学习或检索增强（RAG），动态扩展外部知识库，避免模型幻觉。

记忆动态增强：构建动态记忆库存储交互轨迹，利用注意力机制提取关键经验，实现记忆动态增强。

**工具模块的关键技术包括：**

工具自动查找及使用：基于工具描述文本的语义嵌入匹配，自动构建工具调用方式。现实世界是开放、动态的，新的工具、API、数据源层出不穷。对于一个像人类一样使用工具的智能系统，必须具备泛化能力，能够理解新工具的功能描述，并将其纳入自己的能力版图。

安全沙箱验证：在受限环境（如Docker容器）中预执行高风险操作（如网络请求），验证结果可靠性后再反馈至主流程。Agents要基于环境、上下文、执行反馈等进行感知、判断和决策。

**感知模块的关键技术包括：**

多模态信息融合：利用对齐跨模态表达空间，统一处理文本、图像、语音输入，构建环境状态表征。

环境动态建模：通过世界模型（world model）预测环境变化，辅助Agent预判动作影响。

主动感知与注意力控制：基于强化学习优化感知焦点，优先处理高价值信息（如对话中的偏好、习惯等）。



## **AI幻觉**

[我的钉钉脑图]


