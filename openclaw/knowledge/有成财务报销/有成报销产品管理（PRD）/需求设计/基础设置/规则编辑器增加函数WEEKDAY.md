---
title: "规则编辑器增加函数WEEKDAY"
tags:
  - 有成报销
  - PRD
  - 需求设计-基础设置
created: 2026-03-24
source: 钉钉文档
original_url: https://alidocs.dingtalk.com/i/nodes/Gl6Pm2Db8D3mXMgZTnOYX5pQJxLq0Ee4?utm_scene=team_space
node_id: Gl6Pm2Db8D3mXMgZTnOYX5pQJxLq0Ee4
exported_at: 2026-03-22
---

# 规则编辑器增加函数WEEKDAY

> 🔗 **原文链接**：[规则编辑器增加函数WEEKDAY - 钉钉文档](https://alidocs.dingtalk.com/i/nodes/Gl6Pm2Db8D3mXMgZTnOYX5pQJxLq0Ee4?utm_scene=team_space)

| 修订时间 | 版本 | 修订说明 |
|------------|------|------------|
| 20250923 | v1.0 | 新建 |
|  |  |  |

# **1\. 需求背景**

用户在计算补贴时，用表格组件让员工填写日期、星期，根据星期几有不同补贴规则。

目前的星期是用户手工选择的。

# **2\. 业务流程/架构**

# **3\. 功能清单**

| 模块 | 功能点 | 备注 |
|------|---------|------|
| 基础设置 | 规则编辑器新增日期函数WEEKDAY |  |
|  |  |  |
|  |  |  |

# **4\. 需求详情**

[编辑器字段、函数库](https://alidocs.dingtalk.com/i/nodes/93NwLYZXWygl3x0wIvjwq4xwJkyEqBQm?utm_scene=team_space&iframeQuery=sheet_range%3Ds3_40_2_1_1)


新增一个日期函数，WEEKDAY

简介：返回一个数字，对应于提供的日期所在的星期几。 

结构：WEEKDAY(日期，类型)

日期值：要为其确定星期几的日期。

类型：以数字指示使用哪种编号顺序来表示星期几。默认情况下，计数从星期天（=1）开始。从星期日=1到星期六=7，用1；从星期一=1到星期日=7，用2；从星期一=0到星期日=6时，用3。默认值为1。



保存时校验参数1是否为日期格式，否则报错参数格式错误。
