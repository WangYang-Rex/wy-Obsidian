---
title: "AI"
tags:
  - 有成报销
  - PRD
  - 产品管理-竞品分析-AI
created: 2026-03-24
source: 钉钉文档
original_url: https://alidocs.dingtalk.com/i/nodes/N7dx2rn0JbZ9KxGot5vB2gXvJMGjLRb3?utm_scene=team_space
node_id: N7dx2rn0JbZ9KxGot5vB2gXvJMGjLRb3
exported_at: 2026-03-22
---

# AI

> 🔗 **原文链接**：[AI - 钉钉文档](https://alidocs.dingtalk.com/i/nodes/N7dx2rn0JbZ9KxGot5vB2gXvJMGjLRb3?utm_scene=team_space)

# AI

## 竞品AI能力总结

所有竞品，在目前已上线的与即将上线的能力，基本都是贯穿在业务流程中，都是围绕【降本增效】；

:::color2整体流程关键节点包括：智能推荐（包括行程、采购计划等）、自动提报申请、智能/自动审核、合规管控、自动报销、智能数据分析

:::

✅：表示有

❗：表示功能又透出还未上线，或者有相似功能但未包装成AI能力

| **能力** | **易快报** | **每刻报** | **分贝通** | **汇联易** | **用友** | **金蝶** | **智能财务** |
|----------|-------------|-------------|-------------|-------------|----------|----------|----------------|
| **智能推荐(行程规划)** | ✅ |  | ✅ |  | ✅ | ✅ |  |
| **自动提报申请** | ❗ |  | ✅ |  | ✅ | ✅ | ❗ |
| **智能审核** | ✅ | ✅ | ❗ | ✅ | ✅ | ✅ |  |
| **合规管控(风险预测)** | ✅ |  | ❗ | ✅ | ✅ | ✅ |  |
| **自动报销（自动补贴）** |  |  | ❗ |  | ✅ | ✅ | ❗ |
| **智能数据分析** | ✅ | ✅ | ✅ |  | ✅ | ✅ |  |

## 竞品分析

### 易快报

目前已透出的与AI结合的能力见下表

但【AI行程规划】、【AI采购计划】、【AI审批机器人助理】等未必是真的AI实现的能力，功能其实以前也有。

**未见自动提单的功能**

| **能力** | **角色** | **场景细分** |
|----------|----------|----------------|
| AI行程规划 | 员工 | **行程规划：**当出差申请通过后，根据出行目的及企业的差旅制度，寻找合适的酒店与机票。借助<span style="color: #DF2A3F;">合思商城</span>的聚合消费数据，全网比价，根据个人偏好、企业制度设计出行计划**行程预定：**通过【出行助手】，通过语音方式，直接完成出行中机酒的预定，提升预定体验--基于合思商城 |
| AI采购计划 | 员工 | **采购计划：**行政或 IT 人员在采购时，AI 可基于采购要求、预算等条件进行海量型号比对、信息筛选，帮助企业做出高性价比决策--基于<span style="color: #DF2A3F;">合思商城</span> |
| AI审批 | 员工/主管/老板 | **线下消费：**与<span style="color: #DF2A3F;">合思商城-易商卡</span>结合起来，线下消费时，可以根据实时提交的情况自动审批；以下为引用原文：AI审批环节，我们将易商卡与AI结合起来。易商卡服务的是线下消费，这意味着消费行为可能发生在任何时候——可能是凌晨3点的机场，员工在改签机票，也可能是一场大型活动中临时购买饮料小吃。此时若是消费超标，显然员工是无法及时联系主管或财务的，由此限制易商卡使用的灵活性。而AI就可以很好解决这一问题。 |
| AI审批机器人助理 | 员工/主管/老板 | **财务制度学习：**只需上传一份公司的财务制度，AI就可以自动学习，并基于制度，在单据审批过程中来进行特异化的审批检查，帮助审批人提前发现单据中的各种问题，节省审批者的时间与精力--<span style="color: #DF2A3F;">存疑</span>**辅助决策与审批：**全天24小时在线，根据预置审批规则智能通过、驳回或提出补充资料需求，并帮助审批人提前发现单据中的各种问题（如超标消费），避免审批过程中的反复沟通与修改 |
| AI风控模型 | 主管/老板 | **风险预警：**费用合规性检查与行为异常检测：分析员工的报销行为模式，如报销频率、金额分布等，识别异常报销行为。比如：若某员工平时报销金额较为稳定，突然出现频繁的大额报销，或与以往报销习惯差异较大时，AI 风控模型会将其标记为风险事件，提醒审批人重点关注，防止可能存在的虚报、冒领等欺诈行为**数据异常检测****：**对企业的财务数据进行深度分析，检测数据中的异常波动和趋势变化。例如，通过对费用数据的时间序列分析，发现某个部门或项目的费用突然大幅增长或下降，超出正常波动范围，及时预警可能存在的财务风险，如成本失控、预算超支等。**风险指标量化**：根据海量数据，建立风险评估指标体系，对风险进行量化评估。为每个风险指标设定合理的阈值和权重，通过模型计算得出风险评分，直观地反映企业面临的风险程度。财务人员可以根据风险评分，有针对性地采取风险应对措施，优先处理高风险事项。 |
| AI分析 | 老板/财务 | **智能费用分析**：从企业数据中提炼费用信息，快速形成分析结论，并结合市场信息的挖掘与分析，帮助企业更好地了解费用支出情况，为费用管理决策提供依据，为企业提供更合理的资金管理计划与决策，提高资金使用效率，确保资金的合理规划和使用\*\*\*\* |

\*\*资料：

AI能力发布会：[<span style="color: #0000FF;"><u>https://mp.weixin.qq.com/s/SiUFdpWwIw39l\_Y\_nBaBFw</u></span>](https://mp.weixin.qq.com/s/SiUFdpWwIw39l_Y_nBaBFw)

### 每刻报

每刻报透露出来的AI能力很少，网上几乎看不到，应用中也没有提现；

另外关于易快报包装的AI审批助理、AI风控模型，每刻报也有，但没有包装成AI能力，比如审核校验，在很早之前每刻就做了智能审核

**未见自动提单的功能**

| **能力** | **角色** | **场景细分** |
|----------|----------|----------------|
| AI审批助理 | 员工/主管/老板 | 基于系统内配置的管控制度，在单据审批过程中来进行审批检查，帮助审批人提前发现单据中的各种问题，节省审批者的时间与精力--但可能也不是用的AI能力，因为在很早之前这个能力他们就有，前期包装的一直都是智能审核，现在才加上AI的字眼 |

![Picture 1](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eLbnj1bxmWk8wlaN/img/ceffc5ed-e3f1-4207-85a0-218cda6dd071.png?Expires=1774157706&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=39pPn3X0btbwc0ImnTPs5%2BQEMOQ%3D "")

![Picture 2](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eLbnj1bxmWk8wlaN/img/90367575-6371-4ed9-91df-c653fb73bb75.png?Expires=1774157706&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=XE2RZsL1%2BBdXwPjA1sfE4fDXTLY%3D "")

### 分贝通

[<span style="color: #0000FF;"><u>https://maimai.cn/article/detail?fid=1858548011&efid=z3ZMALOWNfMBAgcjv2ZP2A</u></span>](https://maimai.cn/article/detail?fid=1858548011&amp;efid=z3ZMALOWNfMBAgcjv2ZP2A)

<span style="color: #374151;">AI助手</span>**“小贝”**<span style="color: #374151;">：包含「商旅AI」、「费控AI」和「CBI」三大智能体，进一步为企业提供更加智能化和差异化的差旅服务</span>



![Picture 3](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eLbnj1bxmWk8wlaN/img/a4737788-92bb-42fa-bd88-3abe1785b81c.png?Expires=1774157706&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=dy4FP5kJDxUBS0K28ETWnG%2BCxrs%3D "")

[<span style="color: #0000FF;"><u>此处为语雀卡片，点击链接查看</u></span>](https://www.yuque.com/izoyhv/tzh23k/imh3n0kq5kpek2rh#jrnI3)

| **能力** | **角色** | **场景细分** |
|----------|----------|----------------|
| 商旅AI | 员工 | 1、行程规划与推荐：快速创建行程与差旅申请单，与预定推荐；2、出行服务与支持：对话交互式查询航班、酒店、当地天气等信息，若遇航班延误取消等情况，并协助办理改签等手续 |
| 费控AI | 员工主管财务 | 还未上线主要是快速提交报销单与智能审核，减轻员工提单与审核中的工作量 |
| CBI | 老板财务 | **定位：**精准的智能问数和智能归因，帮助企业及时发现并控制不合理支出，降低企业差旅成本。**关键词：**AI对话式交互，无需掌握复杂的SQL或Python语言，仅凭日常交流的语言，即可清空查询所需数据；合作方：<span style="color: #374151;">数势科技</span>比如：以分贝通某客户的机票支出为例，通过分贝通与数势科技的合作，该客户高管能够在分贝通CBI中通过自然语言文字或语音的方式进行查询。例如，询问“近一年每个月的机票支出是多少，以及同比增长较多的月份归因是什么？”，系统将迅速呈现相关数据，并生成图表及洞察报告 |

### 汇联易

**未见自动提单的功能**



![Picture 4](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eLbnj1bxmWk8wlaN/img/8323cae5-6739-4706-933e-4d17d427bf45.png?Expires=1774157706&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=gUvzlPeUlNYAv3jFlQdH8hnQHn4%3D "")



![Picture 5](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eLbnj1bxmWk8wlaN/img/eb3ecbf9-244f-4877-8c1b-30eaba13c911.png?Expires=1774157706&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=KJlOSsLIfyjS%2FKQyXdbJnf8X6BQ%3D "")



![Picture 6](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eLbnj1bxmWk8wlaN/img/70ebc075-11a3-4521-8be1-d72f47204f73.png?Expires=1774157706&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=NWXzSWOVZpAx3gtsgK3dvXJxd6E%3D "")



![Picture 7](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eLbnj1bxmWk8wlaN/img/77d16d9f-d874-4503-bf68-c9e5b49d47db.png?Expires=1774157706&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=QGTzeKVSXLRtC85BYbQrLeyDkfs%3D "")

![Picture 8](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eLbnj1bxmWk8wlaN/img/a2a6557f-3536-43e8-830d-93ffcd0534e9.png?Expires=1774157706&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=4saT5n1EGXPGvvoFqovokXWApO0%3D "")

![Picture 9](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eLbnj1bxmWk8wlaN/img/0ef6f182-1603-42aa-934b-aaf1d6999114.png?Expires=1774157706&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=35GlLeMejdUdcdBxCU2OsCOZ6Dg%3D "")

| **能力** | **角色** | **场景细分** |
|----------|----------|----------------|
| AI\+智慧审核 | 员工 | **定位：****消灭审核   Copilot**智能审核风险预警与检测 |

### 用友

平台与名称：商旅云-小铁人、用友BIP 智能商旅费控（用友智能财务）形式：采用语音对话式交互，完成行程规划，出行申请单自动创建，商旅预定推荐，单据报销提报，智能自动审核、企业数据分析等流程；

| **能力** | **角色** | **场景细分** |
|----------|----------|----------------|
| 提报填单 | 员工 | <span style="color: #222222;">员工仅需通过对话，就能轻松完成单据的填报和出行费用的预估：</span><span style="color: #222222;">自动行程归集，生成补助，生成报销单</span> |
| 智能出行 | 员工 | <span style="color: #222222;">深度学习用户的行程安排和出行偏好，智能推荐适合的包含出差地点、酒店、机票、火车票等在内的出行方案，节省了员工在选择出行方案上的时间，更通过精准匹配需求，有效降低了企业的差旅成本。</span> |
| 智能审核 | 财务老板主管 | <span style="color: #222222;">预算费控检查与预警：系统还能自动识别异常交易和潜在风险，及时发出预警，帮助企业有效规避财务风险和合规风险</span> |
| 企业数据分析洞察 |  | <span style="color: #222222;">帮助管理者优化决策</span> |

![Picture 10](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eLbnj1bxmWk8wlaN/img/8ec27a1c-c3c1-47d0-a897-5eaaceb18612.png?Expires=1774157706&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=xwneqCfx1bDSqYXZsBCIy3wFeoY%3D "")

![Picture 11](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eLbnj1bxmWk8wlaN/img/09568827-16f9-40c5-9363-8dd7c6624951.png?Expires=1774157706&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=88VztmcQf1YyEFGGaRbzppRUZPg%3D "")

![Picture 12](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eLbnj1bxmWk8wlaN/img/40d30cbb-0e20-4533-8137-818cb28f9b6e.png?Expires=1774157706&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=7aZlZLpLyZBqA0Jf0Ka13DS1Bnw%3D "")

![Picture 13](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eLbnj1bxmWk8wlaN/img/2bdcb557-4f50-4d7d-a3f1-0b0e75a7bec3.png?Expires=1774157706&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=mPAG77umCLP8W0A7HTL2M0jlAaE%3D "")

### 金蝶

版本：金蝶云-星辰、星瀚

基本流程都是一样的：通过语音对话方式，实现智能推荐、合规管控、报销入账的全流程

1、智能填报：通过语音方式自动生成报销单

2、智能审核：AI审单助手进行单据及附件的关键内容审核，自动回归校验（预算费控）

3、数据智能分析

### 钉钉-智能财务

## 有成报销AI应用

**一、总目标：**

依旧围绕【降本增效】展开，将AI能力融合在费控报销流程中，作为辅助工具：

**二、整体呈现：**

现在主要体现在增效，后续逐步深化降本；
- **流程简化**：将现有精心设计和维护的提报流程和审批流程变的简化；
- **数据处理与决策支持**：且能对内部数据和外部数据进行加工，提供更整体广泛的视角与快速数据查询能力，使决策过程变得更加高效和直观

**三、交互方式建议：**语音对话式交互，简单易上手，使用门槛低，员工老板使用都更为便捷

**四、结合有成报销的现状**：无自有商旅平台，但业务流程闭环，以下场景可结合AI进行一定程度的优化

| **能力** | **描述** | **优先级** |
|----------|----------|-------------|
| **自动提报申请** | 通过对话，询问出行方式，去哪里，去几天等信息，自动查询预算费控标准，结合历史预定数据，自动生成推荐行程，进而生成申请单减少员工手工填写时间且确保申请符合标准 | 1 |
| **行程预定** | 1、可自动获取已获批申请，直接提供商旅预定入口，无需员工再去查询商旅预定入口---已开通商旅的企业*2、是否可与商旅平台合作，直接根据行程进行比价推荐订票等功能* | 3 |
| **自动报销** | 1、对话中支持上传票据，同时可获取【我的行程】，对票据上的票面信息与行程进行归类匹配2、自动生成报销数据与自动补贴；3、并自动关联已完成的行程申请，自动提报； | 1 |
| **智能审核** | 1、将现有的校验规则整理归集（预算费控、票据验真查重等）2、提供自动审批规则范畴（比如票据检查，全部校验通过财务审核节点则自动通过）；3、风险数据、历史提报分析数据都可以统一窗口呈现做审批参考 | 2 |
| **智能数据分析** | 1、提供一些数据分析，直接通过对话形式实现简单数据查询比如对应老板：1、直接查询销售部门今年与历年的费用对比情况，能快速呈现相关数据，并对波动数据进行类比归因分析等；比如某季度费用增长是因为今年多举办了线下活动，市场推广费有所增加；2、可直接查询某个部门预算使用情况等；3、后期可接入外部数据，提供同类型企业数据分析作对比，例如行业内同规模企业的费用支出结构，报销审批效率数据等，提供科学的决策支持 | 4 |
| **合规管控**   **(风险预测)** | 1、对个人历史数据以及信用分，对当前提报数据进行评估；2、对部门以及费用等各个维度数据，进行评估，有异常情况给予到风险提示（比如突然间的大额提报） | 5 |
| **智能配置** | 1、历史已有报销流程的，可通过图片等形式，读取所需字段，自动创建表单---涉及业务可能无法一次性搭建好2、批量变动某个配置，比如为所有差旅费的费用类型都添加一个日期字段，不需要每个费用类型去点击编辑再添加； |  |
