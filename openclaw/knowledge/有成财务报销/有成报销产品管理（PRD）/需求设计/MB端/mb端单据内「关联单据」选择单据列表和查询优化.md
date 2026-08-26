---
title: "mb端单据内「关联单据」选择单据列表和查询优化"
nodeId: AR4GpnMqJzMLyKbZhkamwOLPVKe0xjE3
workspaceId: R2PmK2gngjVnZXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/AR4GpnMqJzMLyKbZhkamwOLPVKe0xjE3?utm_scene=team_space"
updateTime: 1785114732000
exportedAt: 2026-08-12T04:21:53.991Z
source: dingtalk-document-mcp
---
> **版本**：v1.0 \| **产品**：有成报销v2.0，智能财务 \| **客户**：<span style="color: rgb(50, 51, 52);">内部优化</span>   
> **修订记录**：v1.0(20260610)初始版本   

---

## 一、需求背景

### 需求现状

mb端单据内使用「关联单据」选择单据时，「选择单据」列表内数据量大没做分页查看时很容易卡死

### 客户预期：

优化mb端「关联单据」使用体验

---

## 二、功能清单

| 模块 | 功能点 | 备注 |
|------|---------|------|
| mb端-新建/编辑单据-「关联单据」 | 优化「选择单据」列表显示数据，增加分页 |  |
| mb端-新建/编辑单据-「关联单据」 | 优化「选择单据」查询方式，使用接口查询 |  |

---

## 三、功能需求

### 3.1 「关联单据」优化「选择单据」列表显示数据，增加分页

**功能描述**：
- mb单据中申请单，借款单，报销单，通用合同，应付合同，应收合同新建/编辑时，「关联单据」中「选择单据」中全部/我申请的/我创建的/我审批的/授权给我的显示单据信息以分页显示，单页显示50条信息；「输入单号标题搜索」优化成接口查询，对所属分类下所有有权限查看的单据查询

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/YvenvegLykXQVloy/img/4d5d996f-770d-4305-81b0-02c910048663.png?Expires=1786515661&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=Zrd1%2FuRf1SHwxKU9ejbEKCIS%2Fm4%3D "")
- mb单据中付款单，收款单新建/编辑时，「关联单据」中「选择单据」中单据/合同显示单据信息以分页显示，单页显示50条信息；「输入单号标题搜索」优化成接口查询，对所属分类下所有有权限查看的单据查询

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/YvenvegLykXQVloy/img/9dbe4d08-c989-4a58-987c-514305715013.png?Expires=1786515661&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=mgbSvIY8aZ4SbPy1p3ckjumZZuk%3D "")
