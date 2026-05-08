---
title: "CRM报销一体化交接-杏子"
tags:
  - 有成报销
  - PRD
  - 产品管理-交接文档-CRM�
created: 2026-03-24
source: 钉钉文档
original_url: https://alidocs.dingtalk.com/i/nodes/Obva6QBXJw9lbx7RTlgKLkOwWn4qY5Pr?utm_scene=team_space
node_id: Obva6QBXJw9lbx7RTlgKLkOwWn4qY5Pr
exported_at: 2026-03-22
---

# CRM报销一体化交接-杏子

> 🔗 **原文链接**：[CRM报销一体化交接-杏子 - 钉钉文档](https://alidocs.dingtalk.com/i/nodes/Obva6QBXJw9lbx7RTlgKLkOwWn4qY5Pr?utm_scene=team_space)

# CRM报销一体化交接-杏子

**销售链路和采购链路中的合同、计划、收付款有做特殊的单据关联核销逻辑，其他的单据同步都是单个单据同步，没有关联核销逻辑**


![Picture 1](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4EZlweZX11MZBqxA/img/ae2dd24c-f431-49bf-8a98-ba0c10b0d3b9.png?Expires=1774157692&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=hYeuUTs%2BxXR3c7%2F1S9xH6bQ89Pg%3D "")


![Picture 2](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4EZlweZX11MZBqxA/img/6a299506-f24d-48c5-8ce9-f1b4f34cfb2a.png?Expires=1774157692&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=ck880EJnRt1gt2SIq9dDhoJO9sE%3D "")

#### 一、单据对接

**1****、已实现：**

已实现所有业务对象的配置对接，包括自定义业务对象

**2、待优化点：部分组件两边还不兼容，**
- 关联单据组件
- 收款场景、付款场景组件

#### 二、辅助核算对接

**1、已实现：**

已实现所有业务对象的配置对接，包括自定义业务对象

**2、待优化点：**
- 之前报销中辅助核算只有单据和编码，因此前期可配置的内容只会同步编码和辅助名称，现在报销中已经升级为表单配置（跟自定义单据）类似了，但对接配置中还未改，目前没有客户提出需要同步更多字段需求

#### 四、历史需求链接

[<u>https://gykj.yuque.com/izoyhv/mlbhnb/bzu0g2bol6qetbz9?singleDoc#</u>](https://gykj.yuque.com/izoyhv/mlbhnb/bzu0g2bol6qetbz9?singleDoc#) 《辅助核算与表单同步映射》


![Picture 3](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4EZlweZX11MZBqxA/img/bddfc553-94f1-41ca-9a28-a80713531628.png?Expires=1774157692&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=M%2F9odTF0oYlGp%2BC9W%2FUaW3iU0Rg%3D "")

#### 五、每周待办

**每周五，在飞鸟项目组群内同步飞鸟相关进度：目前重点进度与使用情况是在飞鸟报表上**

#### 六、人员分布

| **模块** | **人员** |
|----------|----------|
| 后端 | 金梧 |
| 前端 | 张杰 |
| 测试 | 向雅芳 |

#### 七、待规划的需求

| **阶段** | **优先级** | **需求** |
|----------|-------------|----------|
| 第一阶段（业务流） |  | 暂无 |
| 第二阶段   （资金流） | 4 | 退款业务：CRM负数场景需要转换为报销的退款业务---报销侧的退款流程刚开始测试，预计11月上线 |
| 第三阶段   （发票流）    | 1 | 收款链路开票申请以及自动开票（打通电票）---报销侧先做，预计四季度做完 |
|  | 2 | CRM开票申请同步报销，实现开票--报销中收款单与开票之间的链接是通过收款场景组件来实现的，对应了未开票等场景，CRM同步的时候，若需要实现金额核销，需要考虑这个组件 |
|  | 5 | 飞鸟对接：采购收票链路打通 |
| 第四阶段   （经营分析） | 3 | crm搭建预设飞鸟报表 |
|  | 4 | crm报表能力公共化&报销接入CRMBI |
|  | 6 | 报表BI分析能力升级迭代 |
|  | 7 | Bi可视化数据大屏 |
| 其他 |  | 1、有成报销授权后，详情中有成报销TAB下，之前写死了报销单、付款单类型，需要放开所有类型---中懿文澜紧急需求2、项目概览图中的数据，没有做数据过滤，客户需要根据项目负责人设置数据范围--前海立方--可以直接将概览图改版一下3、CRM报销一体化-辅助核算映射，支持按表单同步4、CRM报销一体化-同步记录中，增加同步人的信息 |

**进行中的需求：**

| **需求** | **需求链接** | **状态** |
|----------|----------------|----------|
| 飞鸟报表 |  | 进行中 |
| 报销审批状态同步 | [<u>https://tb.raycloud.com/task/66f6171c27b92a001d6653bc</u>](https://tb.raycloud.com/task/66f6171c27b92a001d6653bc) | 待提测 |
| 部门组件支持同步 | [<u>https://tb.raycloud.com/task/66da674bf5425f001d80fad2</u>](https://tb.raycloud.com/task/66da674bf5425f001d80fad2) | 测试中 |
| 员工组件支持同步 | [<u>https://tb.raycloud.com/task/66d7cfdd27b92a001d165abf</u>](https://tb.raycloud.com/task/66d7cfdd27b92a001d165abf) | 待提测 |
