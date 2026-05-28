---
title: "有成CRM项目-有成报销数据查询优化"
nodeId: dQPGYqjpJYg0lZOdIdEQ5b61Wakx1Z5N
workspaceId: R2PmK2gngjVnZXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/dQPGYqjpJYg0lZOdIdEQ5b61Wakx1Z5N?utm_scene=team_space"
updateTime: 1751427098000
exportedAt: 2026-05-14T12:13:33.047Z
source: dingtalk-document-mcp
---
# 有成CRM项目-有成报销数据查询优化

| **修订时间** | **版本** | **修订说明** |
|----------------|----------|----------------|
| 20230612 | v1.0 | 新建 |

## 1、需求背景

目前有成CRM内，项目管理-有成报销TAB点击后可以查询到有成报销中这个项目关联到的单据，但这个项目只能在主表中，如果项目在消费明细或子表单中，无法获取到这类单据信息

## 2、业务流程/架构

## 3、功能清单

## 4、需求详情

需求端：有成CRM

### 4.1、需求说明

**前提：开通了CRM报销一体化，以及开通了老版的有成报销数据同步**

有成CRM-项目管理-点击项目-点击有成报销，查询当前项目在报销中的单据，需要兼容的情况有：

一、项目在主表中--目前支持的情况

二、项目在消费明细组件中

三、项目在子表单中

项目存在以上不同的地方，都能被取到对应的单据



![Picture 1](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0bvDZoBBnw1/img/43f5e9e1-bfb4-4824-b57b-c90f5b052aca.png?Expires=1778767519&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=cFnb8yRetp2%2Bfmx%2BlQrS3w7LbnI%3D "")
