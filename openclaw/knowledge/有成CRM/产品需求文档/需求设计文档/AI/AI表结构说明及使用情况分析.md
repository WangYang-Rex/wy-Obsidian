---
title: "AI表结构说明及使用情况分析"
tags:
  - 有成CRM
  - PRD
  - 需求设计文档-AI
created: 2026-03-24
source: 钉钉文档
original_url: https://alidocs.dingtalk.com/i/nodes/dpYLaezmVNLO0RakH46Oa73x8rMqPxX6?utm_scene=team_space
node_id: dpYLaezmVNLO0RakH46Oa73x8rMqPxX6
exported_at: 2026-03-22
---

# AI表结构说明及使用情况分析

> 🔗 **原文链接**：[AI表结构说明及使用情况分析 - 钉钉文档](https://alidocs.dingtalk.com/i/nodes/dpYLaezmVNLO0RakH46Oa73x8rMqPxX6?utm_scene=team_space)

目前表结构：
- 用户新开一个会话，则记录在表1：企业、用户、pc/mb、时间
- 会话中发一条消息，则记录在表2：企业、用户、pc/mb、会话id、时间、消息内容（包含意图类型）
- 系统识别到用户‘新建跟进记录’的意图，并生成一个卡片，则记录在表3：企业、用户、pc/mb、会话id、时间、卡片信息

| 可分析维度 | 指标 |
|---------------------------------------------|------------------------------------|
| 基础使用分析 | - 1. 会话维度（表1）
<li style="margin-left:1em">1. 日均/周均/月均会话量（按企业/用户分组）
<li style="margin-left:1em">1. 会话设备分布（PC/Mobile比例）
- 2. 消息维度（表2）
<li style="margin-left:1em">2. 日均/周均/月均消息量（按企业/用户分组）
<li style="margin-left:1em">3. 消息量级分布（单会话平均消息数）
<li style="margin-left:1em">4. 意图类型分布（查询/创建/咨询等数量及占比） |
| 活跃度分析 | - 1. 企业活跃度（表1，所在平台/企业规模/行业信息需要联表查有成系列中企业信息表）
<li style="margin-left:1em">1. 统计日均会话量\>=3 or 月均会话量\>=60 的企业数（计为活跃企业）
<li style="margin-left:1em">2. 统计活跃企业/未到期企业占比
<li style="margin-left:1em">3. 统计活跃企业，所在平台、企业规模、行业的分组情况
<li style="margin-left:2em">1. 所在平台：架构名 ding74d88e04ad655ab435c2f4657eb6378f ，表名customer ，字段名customer\_select\_15
<li style="margin-left:2em">2. 企业规模：架构名 ding74d88e04ad655ab435c2f4657eb6378f ，表名customer ，字段名customer\_integer\_0（分组：6人以下、6-50人，50-100，100-500，500-2000，大于2000）
<li style="margin-left:2em">3. 行业：架构名 ding74d88e04ad655ab435c2f4657eb6378f ，表名customer ，字段名customer\_input\_4
<li style="margin-left:1em">4. 统计活跃企业意图类型分组情况
- 2. 用户活跃度（表1，所在平台/企业规模/行业信息需要联表查有成系列中企业信息表）
<li style="margin-left:1em">5. 统计日均会话量\>=1 or 月均会话量\>=20 的用户数（计为活跃用户）
<li style="margin-left:1em">6. 统计活跃用户/未到期企业用户总数占比
<li style="margin-left:1em">7. 统计活跃用户，所在所在平台、企业规模、行业、~~用户角色~~分组情况
<li style="margin-left:2em">4. 所在平台、企业规模、行业同企业活跃度
<li style="margin-left:2em">5. ~~角色分组：查用户所在企业，角色表（一个用户有多个角色，按角色名称进行分组）~~
<li style="margin-left:1em">8. 统计活跃用户意图类型分组情况
<li style="margin-left:1em">9. 新用户的首周活跃率（第一次使用的用户，7天内再次使用则算首周活跃，除以AI使用总用户数，得出首周活跃率） |
| 异常使用分析 | - 1. ~~无效会话~~~~（表1\+表2）~~
<li style="margin-left:1em">1. ~~统计仅包含1条消息的会话数（提示可能为无效会话）~~
<li style="margin-left:1em">2. ~~统计无效会话/总会话占比~~
- 2. 重复意图请求（表1\+表2）
<li style="margin-left:1em">3. 统计相同意图类型\>=2的会话数（提示可能AI未准确识别）
<li style="margin-left:1em">4. 统计重复意图请求会话数/总会话数占比 |
| 跟进记录分析 | - 1. 字段填充完整率（AI填充的字段/模板中总字段，得出完整率）（表3）
- 2. 统计单次会话中，新建跟进记录意图\>=2的会话数，及其除以包含新建跟进记录意图会话总数的占比（提示可能AI字段填充可能不精准）（表2） |
```java
@TableId(type = IdType.AUTO)
@Schema(description = "主键ID")
private Long id;

@Schema(description = "应用ID")
private String appId;

@Schema(description = "企业ID")
private String corpId;

@Schema(description = "用户ID")
private String userId;

@Schema(description = "来源 PC/MB/PC_AI助手/MB_AI助手")
private String chatSource;

@Schema(description = "对话token")
private String chatToken;

@Schema(description = "钉钉AI助手token,用于调用钉钉api接口")
private String dingAiConversationToken;

@TableField(fill = FieldFill.INSERT)
@Schema(description = "创建时间")
private Date created;

@TableField(fill = FieldFill.INSERT_UPDATE)
@Schema(description = "最后修改时间")
private Date modified;
```
```java
@TableId(type = IdType.AUTO)
@Schema(description = "主键ID")
private Long id;

@Schema(description = "应用ID")
private String appId;

@Schema(description = "企业ID")
private String corpId;

@Schema(description = "用户ID")
private String userId;

@Schema(description = "来源 PC/MB/PC_AI助手/MB_AI助手")
private String chatSource;

@Schema(description = "对话token")
private String chatToken;

@Schema(description = "对话消息内容")--JSON结构见下，包含识别到的意图类型，如查询客户、新建跟进...
private String chatMessage;

@Schema(description = "对话消息内容(原)")
private String chatContext;

@Schema(description = "对话消息文件")
private String chatFile;

@TableField(fill = FieldFill.INSERT)
@Schema(description = "创建时间")
private Date created;

@TableField(fill = FieldFill.INSERT_UPDATE)
@Schema(description = "最后修改时间")
private Date modified;
```
```json
{
    "messageType": "mark_down",
    "intention": "OTHER",
    "role": "assistant",
    "content": "{\"errorStatus\":\"\",\"errorMessage\":\"\",\"parseText\":\"根据您的要求，以下是查询公司信息的通用方法及示例模板。由于您未提供具体公司名称，我以示例形式说明如何整理这类信息：\\n\\n---\\n\\n### **查询方法说明**  \\n1. **官方渠道**：公司官网（\\\"About Us/投资者关系\\\"板块）、年报、招股书  \\n2. **第三方平台**：天眼查/企查查（国内）、Crunchbase/LinkedIn（海外）、行业分析报告  \\n3. **新闻资讯**：财经媒体（如36氪、财新、彭博社等）的深度报道  \\n\\n---\\n\\n### **示例模板**  \\n#### **1. 腾讯控股（Tencent Holdings）**  \\n- **行业**：互联网科技（社交、游戏、云计算）  \\n- **规模**：  \\n  - 全球员工约11.4万人（2023年数据）  \\n  - 市值3.2万亿港元（截至2023年）  \\n- **主营业务**：微信/QQ生态、游戏（《王者荣耀》）、广告、金融科技、云服务  \\n\\n#### **2. 宁德时代（CATL）**  \\n- **行业**：新能源动力电池  \\n- **规模**：  \\n  - 国内市场份额超50%（2023年）  \\n  - 全球员工约10万人  \\n- **主营业务**：锂离子电池研发制造，客户包括特斯拉、宝马等  \\n\\n#### **3. 联合利华（Unilever）**  \\n- **行业**：快消品（FMCG）  \\n- **规模**：  \\n  - 全球覆盖190个国家  \\n  - 年营收约600亿欧元（2023年）  \\n- **主营业务**：日化（ Dove、Lipton）、食品饮料、个人护理  \\n\\n---\\n\\n### **特殊类型企业提示**  \\n- **初创公司**：重点查看融资历史（如红杉资本投资）和技术方向  \\n- **非上市公司**：需通过工商注册信息（如注册资本、股东构成）推断规模  \\n\\n如需查询具体公司，请提供名称，我将协助整理最新数据。\",\"intention\":\"OTHER\",\"action\":\"MARK_DOWN\"}"
}
```
```java
@TableId(type = IdType.AUTO)
@Schema(description = "主键ID")
private Long id;

@Schema(description = "应用ID")
private String appId;

@Schema(description = "企业ID")
private String corpId;

@Schema(description = "用户ID")
private String userId;

@Schema(description = "来源 PC/MB/PC_AI助手/MB_AI助手")
private String chatSource;

@Schema(description = "对话token")
private String chatToken;

@Schema(description = "卡片数据")--数据结构见下，包含对象、模板、数据、字段
private String chatCard;

@TableField(fill = FieldFill.INSERT)
@Schema(description = "创建时间")
private Date created;

@TableField(fill = FieldFill.INSERT_UPDATE)
@Schema(description = "最后修改时间")
private Date modified;
```
```json
{
    "convertData": {
        "keep_record_select_8": "买卖",
        "keep_record_select_8_value": "7198e5971bc04cceaf9fe510ce3e154c",
        "keep_type": "钉钉-代理商拜访",
        "keep_content": "2025年07月01日 11时58分36秒创建笔筒基本信息（远程环境），填写跟进记录，查询光云科技基本信息",
        "keep_record_status_value": "on_keep",
        "created": "2025/07/01 11:58:36",
        "deploy_id_value": "customer",
        "keep_type_value": "d38d4a1c874543ea8dcbdbab998d6285",
        "keep_record_status": "要货",
        "deploy_id": "客户"
    },
    "templateName": "跟进记录",
    "convertMessageList": [
        "keep_record关联对象[光云科技]不存在",
        "keep_record关联对象[石盐]不存在",
        "keep_record关联对象[金钰投资,有成服务部,乘风破浪战队（酷应用演示专用）]不存在",
        "keep_record模板选择选项不存在"
    ],
    "templateId": "default_template",
    "deployId": "keep_record",
    "deployName": "跟进记录",
    "convertFieldList": [
        {
            "fieldName": "deploy_id",
            "fieldTitle": "对象类型",
            "fieldDomType": "SELECT"
        },
        {
            "fieldName": "keep_content",
            "fieldTitle": "跟进内容",
            "fieldDomType": "TEXTAREA"
        },
        {
            "fieldName": "keep_record_select_8",
            "fieldTitle": "带看类型",
            "fieldDomType": "SELECT"
        },
        {
            "fieldName": "keep_type",
            "fieldTitle": "跟进类型",
            "fieldDomType": "SELECT"
        },
        {
            "fieldName": "keep_record_status",
            "fieldTitle": "跟进状态",
            "fieldDomType": "SELECT"
        },
        {
            "fieldName": "created",
            "fieldTitle": "跟进时间",
            "fieldDomType": "DATETIME"
        }
    ]
}
```


