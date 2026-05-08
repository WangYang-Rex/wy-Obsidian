---
title: "接入oa审批"
tags:
  - 有成CRM
  - PRD
  - 需求设计文档-多平台-�
created: 2026-03-24
source: 钉钉文档
original_url: https://alidocs.dingtalk.com/i/nodes/6LeBq413JAzGj9vYHnQk5B2K8DOnGvpb?utm_scene=team_space
node_id: 6LeBq413JAzGj9vYHnQk5B2K8DOnGvpb
exported_at: 2026-03-22
---

# 接入oa审批

> 🔗 **原文链接**：[接入oa审批 - 钉钉文档](https://alidocs.dingtalk.com/i/nodes/6LeBq413JAzGj9vYHnQk5B2K8DOnGvpb?utm_scene=team_space)

# 接入oa审批

| **修订时间** | **版本** | **修订人** | **修订说明** |
|----------------|----------|-------------|----------------|
| 20221116 | v1.0 | 黄艺平 | 新建 |
|  |  |  |  |

## 1、需求背景

开发文档：[<u>https://alidocs.dingtalk.com/i/p/Y7kmbokZW9RYGLq2/docs/qXomz1wAyjKVXOl94wjAW3Y9pRBx5OrE#</u>](https://alidocs.dingtalk.com/i/p/Y7kmbokZW9RYGLq2/docs/qXomz1wAyjKVXOl94wjAW3Y9pRBx5OrE#)

## 2、需求详情


![Picture 1](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4EZlweZXV3zmWqxA/img/c5260e3b-9d06-4b95-abb3-f78bbbf34e22.png?Expires=1774165592&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=UEjLxUGfbGwy7XyMIjj1CuCSQ8U%3D "")

| **需求** | **描述** |
|----------|----------|
| 套件信息 | 一、套件名称：有成CRM拜访签到二、套件包含控件：1）关联客户：必填，根据企业id\+用户id取应用内‘客户’列表数据，数据返回时展示'客户名称'2）关联项目：不必填，根据企业id\+用户id取应用内‘项目’列表数据，数据返回时展示'项目名称'3）签到时间：不必填4）签退时间：不必填5）签到地址：不必填6）关联拜访签到：不必填三、套件介绍信息关联客户/项目：可选择应用中客户/项目资料签到时间/签退时间/签到地址/关联拜访签到：到达客户现场，可快捷新建拜访签，且签到数据将回传至审批单中（建议这些字段设置成在发起审批页隐藏） |
| 发起审批 | 跳转至应用内、选择数据，校验企业是否有开通应用、是否进行应用内授权的逻辑同目前应用市场： |
| 审批单据详情 | 一、去签到1、oa审批单审批已通过 且 \{关联拜访签到\}为空 且为移动端：此按钮展示2、新建拜访签到时：自动带入审批单中填写的‘关联客户’‘关联项目’3、新增拜访签到：将签到的‘签到时间’‘签退时间’‘签到地址’‘id’写入oa审批单据（无论该单据中目前字段中是否有值）二、查看签到信息1、\{关联拜访签到\}不为空时：此按钮展示2、拜访签到编辑/删除：修改/清空oa审批单据中‘签到时间’‘签退时间’‘签到地址’‘id’ |

![Picture 2](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4EZlweZXV3zmWqxA/img/0990c3ac-f700-4ce5-9083-4e37cac055e6.png?Expires=1774165592&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=MMMdX%2BWRSU5Z%2B1JAHBEAQvDq%2Fpg%3D "")

![Picture 3](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4EZlweZXV3zmWqxA/img/2c136a31-0998-4ded-8eef-883348dea25e.png?Expires=1774165592&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=JWyGuwxBGaantKteUG8iyB4161Y%3D "")
