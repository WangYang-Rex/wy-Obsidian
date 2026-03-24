---
title: "AI应用管理后台优化，报销AI版本上架钉钉甄选对接"
tags:
  - 有成报销
  - PRD
  - 需求设计-管理后台
created: 2026-03-24
source: 钉钉文档
original_url: https://alidocs.dingtalk.com/i/nodes/Obva6QBXJw9lbx7RTRbjK52YWn4qY5Pr?utm_scene=team_space
node_id: Obva6QBXJw9lbx7RTRbjK52YWn4qY5Pr
exported_at: 2026-03-22
---

# AI应用管理后台优化，报销AI版本上架钉钉甄选对接

> 🔗 **原文链接**：[AI应用管理后台优化，报销AI版本上架钉钉甄选对接 - 钉钉文档](https://alidocs.dingtalk.com/i/nodes/Obva6QBXJw9lbx7RTRbjK52YWn4qY5Pr?utm_scene=team_space)

| 修订时间 | 版本 | 修订说明 |
|------------|------|------------|
| 20251029 | v1.0 | 新建 |
|  |  |  |

# **1\. 需求背景**

之前报销上架钉钉甄选的有两个版本，尊享版、旗舰版。

其中尊享版未包含合同、项目、预算相关模块的功能。

报销更新AI能力之后，考虑到老客续费， 需要和原来的版本排列组合出新的AI组合版本，上架钉钉甄选。

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ybEnB5jpRGo53lP1/img/9a7d4091-3c20-408e-90f2-ae127e185213.png?Expires=1774156620&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=fgT%2BSDNKdYdivdvNSyVuJk9meCg%3D "")

尊享版(AI基础版) DT\_GOODS\_881634267259160\_4475003

尊享版(AI专业版) DT\_GOODS\_881634267259160\_4475002

旗舰版(AI基础版) DT\_GOODS\_881634267259160\_4475005

旗舰版(AI专业版) DT\_GOODS\_881634267259160\_4475004

另外，之前我们用白名单控制的AI助理是否显示，鉴于AI报销已经开始售卖，统一放到管理后台控制。

# **2\. 业务流程/架构**

# **3\. 功能清单**

| 模块 | 功能点 | 备注 |
|------|---------|------|
| 管理后台 | 订单列表兼容新版本<br>初始化，钉钉甄选传入订单，根据传入的版本初始化功能 |  |
|  | 企业管理增加操作-AI审批规则上限调整 |  |
|  | 管理后台企业查询新增版本列，支持展示客户最新购买的版本 |  |
| 应用中心 | 增加AI增值卡片 |  |
| 续费升级 | UI图换新增加了AI版本 |  |

# **4\. 需求详情**

## **管理后台-企业查询-操作中增加AI应用相关功能控制**    

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ybEnB5jpRGo53lP1/img/f4c96c9e-a666-4e1b-9253-52a83962094e.png?Expires=1774156620&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=yEwA%2FWBX2Q4%2F9XNirokX%2FDe9bOw%3D "")

~~1、模块开启/关闭-报销-AI应用下新增“AI助理”子开关。~~

~~逻辑关系在AI应用的开关下，和AI分析同级，启用AI应用时默认开启。~~

~~控制AI助理悬浮入口是否显示。~~

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ybEnB5jpRGo53lP1/img/de99c6fd-27b0-4b68-8113-c0cc92f49624.png?Expires=1774156620&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=RhnkOpJciLpQKd1V4OuShqm3zVM%3D "")

~~不再需要保留原白名单控制，功能上线时通知~~@树琳(白砂)~~手工开通下历史白名单企业。~~



2、AI应用下新增功能级控制

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ybEnB5jpRGo53lP1/img/a5ee0c09-a971-4d9c-9f46-67b5c3b3447e.png?Expires=1774156620&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=okaVyLFeGsWQMqi6Cvt4tqsTwvs%3D "")

展示三个子选项：累计消耗token上限、审批规则上限、<span style="color: rgb(23, 24, 28); background-color: rgb(255, 245, 184);">AI助理开关。</span>
- 月累计消耗token上限：700000千token，用户可输入。
    - 值范围：0～999999999。
    - 超出后后台阻断提示“token超限，请联系客服处理”。
    - 下方需要展示企业本月累计已使用token数，输入\+输出。月初自动清空。
- 审批规则上限：单选必选，不限、限制xx条。默认限制40条。
    - 条数值范围0～10000。控制的是这个企业所有审批助手的规则总数。
    - **新增规则时前端提示：当前版本最多支持x条规则，可联系客服升级版本。**
    - 下方需要展示当前企业所有审批助手下已配置的规则总数。
- AI助理开关：
    - <span style="color: rgb(23, 24, 28); background-color: rgb(255, 245, 184);">开通AI应用后，默认开启AI 助理，开启后控制AI助理悬浮入口是否显示。</span>

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ybEnB5jpRGo53lP1/img/de99c6fd-27b0-4b68-8113-c0cc92f49624.png?Expires=1774156620&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=RhnkOpJciLpQKd1V4OuShqm3zVM%3D "")

不再需要保留原白名单控制，功能上线时通知@树琳(白砂)手工开通下历史白名单企业。
    - 开启后，可见boss问数勾选项，默认不勾选。
        - 控制AI助理中意图识别是否对接到问数agent，是否展示BOSS问数卡片。
        - <span style="color: rgb(23, 24, 28); background-color: rgb(255, 245, 184);">本期因为功能还没上线，先上开关，无实际效果。</span>

## **订单传入及企业初始化**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ybEnB5jpRGo53lP1/img/58cbacf9-54f2-4770-ae26-5c55fd4c5820.png?Expires=1774156620&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=wWUhszA4BK7edDLnesE7Nx1Y5co%3D "")

1、管理后台订单列表，订单中传入商品兼容新增的四个版本：
- AI智能报销基础版
- AI智能报销专业版
- AI智能费控基础版
- AI智能费控专业版

2、钉钉甄选传入订单，系统进行企业初始化时，按照不同的版本初始化功能。

各版本功能列表如下（标黄部分需要核对下线上，如果有出入，新企业按照最新版本的控制）：

| <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">有成报销产品报价</span> |  |  |  |  |  |  |  |  |  |
|-------------------------------------------------------------------------------------------------------------|---|---|---|---|---|---|---|---|---|
| <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">功能详情</span> |  | <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">所属平台：钉钉、企业微信、飞书</span> |  |  |  |  |  | <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">**独立版**</span> |  |
|  |  | <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">尊享版</span> | <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">旗舰版</span> | <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">AI智能报销基础版</span><br><span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">（尊享版\+AI基础版）</span> | <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">AI智能报销专业版</span><br><span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">（尊享版\+AI专业版）</span> | <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">AI智能费控基础版</span><br><span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">（旗舰版\+AI基础版）</span> | <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">AI智能费控专业版</span><br><span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">（旗舰版\+AI专业版）</span> | <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">**尊享版**</span> | <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">**旗舰版**</span> |
|  |  | <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">168元/人/年</span> | <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">258元/人/年</span> | <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">708元/人/年</span> | <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">1188元/人/年</span> | <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">816元/人/年</span> | <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">1296元/人/年</span> | <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">**168元/人/年**</span> | <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">**258元/人/年**</span> |
| <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">**员工报销**</span> | 费用申请 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 行程预定 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 随手记 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 里程补贴 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 行程导航/轨迹报销 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 费用报销 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 借款核销 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 单据打印 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 单据签收 | √ | √ | √ | √ | √ | √ | √ | √ |
| <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">**智能拍票**</span><br><span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">**OCR**</span> | OCR拍照识票 | <span style="color: rgb(255, 0, 0);">—</span> | √ | <span style="color: rgb(255, 0, 0);">—</span> | <span style="color: rgb(255, 0, 0);">—</span> | √ | √ | <span style="color: rgb(255, 0, 0);">—</span> | √ |
|  | 企业/个人发票夹 | √ | √ | √ | √ | √ | √ | √ | √ |
| <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">**对公业务**</span> | 往来单位管理 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 采购申请 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | <span style="background-color: rgb(254, 255, 0);">采购合同</span> | <span style="color: rgb(255, 0, 0); background-color: rgb(254, 255, 0);">—</span> | √ | <span style="color: rgb(255, 0, 0); background-color: rgb(254, 255, 0);">—</span> | <span style="color: rgb(255, 0, 0); background-color: rgb(254, 255, 0);">—</span> | √ | √ | <span style="color: rgb(255, 0, 0);">—</span> | √ |
|  | 对公付款 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 分期付款/提醒 | <span style="color: rgb(255, 0, 0);">—</span> | √ | <span style="color: rgb(255, 0, 0);">—</span> | <span style="color: rgb(255, 0, 0);">—</span> | √ | √ | <span style="color: rgb(255, 0, 0);">—</span> | √ |
|  | 预付到票/到票核销 | <span style="color: rgb(255, 0, 0);">—</span> | √ | <span style="color: rgb(255, 0, 0);">—</span> | <span style="color: rgb(255, 0, 0);">—</span> | √ | √ | <span style="color: rgb(255, 0, 0);">—</span> | √ |
|  | 销售合同 | <span style="color: rgb(255, 0, 0); background-color: rgb(254, 255, 0);">—</span> | √ | <span style="color: rgb(255, 0, 0); background-color: rgb(254, 255, 0);">—</span> | <span style="color: rgb(255, 0, 0); background-color: rgb(254, 255, 0);">—</span> | √ | √ | <span style="color: rgb(255, 0, 0);">—</span> | √ |
|  | 回款计划/催收 | <span style="color: rgb(255, 0, 0); background-color: rgb(254, 255, 0);">—</span> | √ | <span style="color: rgb(255, 0, 0); background-color: rgb(254, 255, 0);">—</span> | <span style="color: rgb(255, 0, 0); background-color: rgb(254, 255, 0);">—</span> | √ | √ | <span style="color: rgb(255, 0, 0);">—</span> | √ |
|  | 收款单 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 开票申请 | <span style="color: rgb(255, 0, 0);">—</span> | √ | <span style="color: rgb(255, 0, 0);">—</span> | <span style="color: rgb(255, 0, 0);">—</span> | √ | √ | <span style="color: rgb(255, 0, 0);">—</span> | √ |
|  | 合同台账 | <span style="color: rgb(255, 0, 0);">—</span> | √ | <span style="color: rgb(255, 0, 0);">—</span> | <span style="color: rgb(255, 0, 0);">—</span> | √ | √ | <span style="color: rgb(255, 0, 0);">—</span> | √ |
| <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">**项目管理**</span> | 项目申请 | <span style="color: rgb(255, 0, 0);">—</span> | √ | <span style="color: rgb(255, 0, 0);">—</span> | <span style="color: rgb(255, 0, 0);">—</span> | √ | √ | <span style="color: rgb(255, 0, 0);">—</span> | √ |
|  | 项目立项 | <span style="color: rgb(255, 0, 0);">—</span> | √ | <span style="color: rgb(255, 0, 0);">—</span> | <span style="color: rgb(255, 0, 0);">—</span> | √ | √ | <span style="color: rgb(255, 0, 0);">—</span> | √ |
|  | 项目预算 | <span style="color: rgb(255, 0, 0);">—</span> | √ | <span style="color: rgb(255, 0, 0);">—</span> | <span style="color: rgb(255, 0, 0);">—</span> | √ | √ | <span style="color: rgb(255, 0, 0);">—</span> | √ |
|  | 关联单据 | <span style="color: rgb(255, 0, 0);">—</span> | √ | <span style="color: rgb(255, 0, 0);">—</span> | <span style="color: rgb(255, 0, 0);">—</span> | √ | √ | <span style="color: rgb(255, 0, 0);">—</span> | √ |
|  | 项目报表 | <span style="color: rgb(255, 0, 0);">—</span> | √ | <span style="color: rgb(255, 0, 0);">—</span> | <span style="color: rgb(255, 0, 0);">—</span> | √ | √ | <span style="color: rgb(255, 0, 0);">—</span> | √ |
| <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">**费用标准**</span> | 费用标准 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 淡旺季/节假日差标 | √ | √ | √ | √ | √ | √ | <span style="color: rgb(255, 0, 0);">—</span> | √ |
|  | 城市级别 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 费用分摊 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 超标预警提示 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 补助自动计算 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 外币 | √ | √ | √ | √ | √ | √ | √ | √ |
| <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">**预算费控**</span> | 预算编制 | <span style="color: rgb(255, 0, 0);">—</span> | √ | <span style="color: rgb(255, 0, 0);">—</span> | <span style="color: rgb(255, 0, 0);">—</span> | √ | √ | <span style="color: rgb(255, 0, 0);">—</span> | √ |
|  | 自定义预算周期 | <span style="color: rgb(255, 0, 0);">—</span> | √ | <span style="color: rgb(255, 0, 0);">—</span> | <span style="color: rgb(255, 0, 0);">—</span> | √ | √ | <span style="color: rgb(255, 0, 0);">—</span> | √ |
|  | 自定义预算维度 | <span style="color: rgb(255, 0, 0);">—</span> | √ | <span style="color: rgb(255, 0, 0);">—</span> | <span style="color: rgb(255, 0, 0);">—</span> | √ | √ | <span style="color: rgb(255, 0, 0);">—</span> | √ |
|  | 滚动预算（预算结转） | <span style="color: rgb(255, 0, 0);">—</span> | √ | <span style="color: rgb(255, 0, 0);">—</span> | <span style="color: rgb(255, 0, 0);">—</span> | √ | √ | <span style="color: rgb(255, 0, 0);">—</span> | √ |
|  | 动态预算 | <span style="color: rgb(255, 0, 0);">—</span> | √ | <span style="color: rgb(255, 0, 0);">—</span> | <span style="color: rgb(255, 0, 0);">—</span> | √ | √ | <span style="color: rgb(255, 0, 0);">—</span> | √ |
|  | 预算执行进度预警 | <span style="color: rgb(255, 0, 0);">—</span> | √ | <span style="color: rgb(255, 0, 0);">—</span> | <span style="color: rgb(255, 0, 0);">—</span> | √ | √ | <span style="color: rgb(255, 0, 0);">—</span> | √ |
|  | 预算报表 | <span style="color: rgb(255, 0, 0);">—</span> | √ | <span style="color: rgb(255, 0, 0);">—</span> | <span style="color: rgb(255, 0, 0);">—</span> | √ | √ | <span style="color: rgb(255, 0, 0);">—</span> | √ |
|  | 预算控制规则 | <span style="color: rgb(255, 0, 0);">—</span> | √ | <span style="color: rgb(255, 0, 0);">—</span> | <span style="color: rgb(255, 0, 0);">—</span> | √ | √ | <span style="color: rgb(255, 0, 0);">—</span> | √ |
| <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">**财务管理**</span> | 收付款管理 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 借还款管理 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 资金管理 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 发票管理 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 映射生成会计凭证 | √ | √ | √ | √ | √ | √ | √ | √ |
| <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">**单据管理**</span><br><span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">**（台账）**</span> | 申请单管理 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 借款单管理 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 报销单管理 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 付款单管理 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 收款单管理 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 合同单管理 | <span style="color: rgb(255, 0, 0);">—</span> | √ | <span style="color: rgb(255, 0, 0);">—</span> | <span style="color: rgb(255, 0, 0);">—</span> | √ | √ | <span style="color: rgb(255, 0, 0);">—</span> |  |
| <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">**智能报表**</span> | 个人费用报表 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 企业费用报表 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 报表数据导出 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 自定义报表 | <span style="color: rgb(255, 0, 0);">—</span> | √ | <span style="color: rgb(255, 0, 0);">—</span> | <span style="color: rgb(255, 0, 0);">—</span> | √ | √ | <span style="color: rgb(255, 0, 0);">—</span> | √ |
|  | 流程效率报表 | √ | √ | √ | √ | √ | √ | √ | √ |
| <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">**有成BI分析平台**</span> | 可视化 | 增值付费 | 增值付费 | 增值付费 | 增值付费 | 增值付费 | 增值付费 |  |  |
|  | 自定义 | 增值付费 | 增值付费 | 增值付费 | 增值付费 | 增值付费 | 增值付费 |  |  |
|  | 数据大屏 | 增值付费 | 增值付费 | 增值付费 | 增值付费 | 增值付费 | 增值付费 |  |  |
|  | 高版本ETL数据中心、实施 | 增值付费 | 增值付费 | 增值付费 | 增值付费 | 增值付费 | 增值付费 |  |  |
| <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">**AI应用**</span> | AI报销助手（含OCR） | <span style="color: rgb(255, 0, 0);">**—**</span> | <span style="color: rgb(255, 0, 0);">**—**</span> | ✅ 自动生成报销单 | ✅ 自动生成报销单 | ✅ 自动生成报销单 | ✅ 自动生成报销单 |  |  |
|  | 费用标准助手 | <span style="color: rgb(255, 0, 0);">**—**</span> | <span style="color: rgb(255, 0, 0);">**—**</span> | ✅ 费用标准查询 | ✅ 费用标准查询 | ✅ 费用标准查询 | ✅ 费用标准查询 |  |  |
|  | 智能客服助手 | <span style="color: rgb(255, 0, 0);">**—**</span> | <span style="color: rgb(255, 0, 0);">**—**</span> | ✅ 报销知识问答 | ✅ 报销知识问答 | ✅ 报销知识问答 | ✅ 报销知识问答 |  |  |
|  | AI审批助手（单据识别、合规校验） | <span style="color: rgb(255, 0, 0);">**—**</span> | <span style="color: rgb(255, 0, 0);">**—**</span> | **✅ 自动审批基础规则（40条）** | **✅ 自动审批高级规则\+风险提示（不限制规则数）** | **✅ 自动审批基础规则（40条）** | **✅ 自动审批高级规则\+风险提示（不限制规则数）** |  |  |
|  | AI数据分析与报告（费用/预算/现金流/经营分析） | <span style="color: rgb(255, 0, 0);">**—**</span> | <span style="color: rgb(255, 0, 0);">**—**</span> | <span style="color: rgb(255, 0, 0);">**—**</span> | **✅固定分析报告** | <span style="color: rgb(255, 0, 0);">**—**</span> | **✅固定分析报告** |  |  |
|  | AI异常监控看板 | <span style="color: rgb(255, 0, 0);">**—**</span> | <span style="color: rgb(255, 0, 0);">**—**</span> | <span style="color: rgb(255, 0, 0);">**—**</span> | ✅ 实时费用异常监控 | <span style="color: rgb(255, 0, 0);">**—**</span> | ✅ 实时费用异常监控 |  |  |
|  | BOSS问数 | <span style="color: rgb(255, 0, 0);">**—**</span> | <span style="color: rgb(255, 0, 0);">**—**</span> | <span style="color: rgb(255, 0, 0);">**—**</span> | **✅固定报表语音问数** | <span style="color: rgb(255, 0, 0);">**—**</span> | **✅固定报表语音问数** |  |  |
|  | AI运行报告 | <span style="color: rgb(255, 0, 0);">**—**</span> | <span style="color: rgb(255, 0, 0);">**—**</span> | **✅AI运行报告** | **✅AI运行报告（含风险拦截报告）** | **✅AI运行报告** | **✅AI运行报告（含风险拦截报告）** |  |  |
|  | 系统对接与深度定制化开发 | <span style="color: rgb(255, 0, 0);">**—**</span> | <span style="color: rgb(255, 0, 0);">**—**</span> | <span style="color: rgb(255, 0, 0);">**—**</span> | <span style="color: rgb(255, 0, 0);">**—**</span> | <span style="color: rgb(255, 0, 0);">**—**</span> | <span style="color: rgb(255, 0, 0);">**—**</span> |  |  |
| <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">**灵活自定义**</span> | 自定义单据类型模板 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 自定义多级费用类型 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 自定义单据审批流程 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 自定义角色/权限 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 自定义费用核算维度 | √ | √ | √ | √ | √ | √ | √ | √ |
| <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">**数据互联**</span> | 与ERP、OA、CRM等数据集成 | 增值付费 | 增值付费 | 增值付费 | 增值付费 | 增值付费 | 增值付费 | 增值付费 | 增值付费 |
| <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">**银联支付**</span> | 银企直联/CBS | 增值付费 | 增值付费 | 增值付费 | 增值付费 | 增值付费 | 增值付费 | 增值付费 | 增值付费 |
| <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">**智能记账平台**</span> | 总账凭证/会计科目费用类型映射 | 增值付费 | 增值付费 | 增值付费 | 增值付费 | 增值付费 | 增值付费 | 增值付费 | 增值付费 |
| <span style="color: rgb(255, 255, 255); background-color: rgb(41, 127, 245);">**钉钉/企业微信/多平台**</span> | 钉钉通讯录同步 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 审批代办、工作通知对接 | √ | √ | √ | √ | √ | √ | √ | √ |
|  | 钉钉考勤数据同步 | √ | √ | √ | √ | √ | √ | √ | √ |

3、通过订单传入的AI应用，需要为企业对应开通模块/功能，

1）AI智能报销基础版（尊享版\+AI基础版）、AI智能费控基础版（旗舰版\+AI基础版）

AI应用：开启
    - 本月累计消耗token上限：初始化默认值
    - 审批规则上限：限制40条
    - AI助理具体功能：不勾选boss问数。

模块开启/关闭：
- AI应用-开
    - AI分析-关
    - AI异常监控-关
    - AI审批-开
    - AI运行看板-开
    - AI助理-开

2）AI智能费控专业版（旗舰版\+AI专业版）、AI智能报销专业版（尊享版\+AI专业版）

AI应用：开启
    - 本月累计消耗token上限：初始化默认值
    - 审批规则上限：不限制
    - AI助理具体功能：勾选boss问数。

模块开启/关闭：
- AI应用-开
    - AI分析-开
    - AI异常监控-开
    - AI审批-开
    - AI运行看板-开
    - AI助理-开

## **管理后台-企业查询-应用=有成报销，增加一列已购买版本**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ybEnB5jpRGo53lP1/img/eb056a19-618d-4298-9d00-c3d39f8cf439.png?Expires=1774156620&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=pCg4yDVY%2FjHStEyb%2F5TWKIexlFQ%3D "")

展示客户最新购买的版本，版本有：
- 尊享版
- 畅享版
- AI智能报销基础版
- AI智能报销专业版
- AI智能费控基础版
- AI智能费控专业版

上方筛选器中增加版本下拉筛选框。



## **其他关联影响**

线上用户续费增购入口需要增加新的版本，注意wps渠道单独的图需要替换。

-等待设计出图












