---
title: "OCR识票后，能对发票自动进行费用类型匹配归类"
nodeId: kDnRL6jAJM3ARLZPTDkpnXLYWyMoPYe1
workspaceId: R2PmK2gngjVnZXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/kDnRL6jAJM3ARLZPTDkpnXLYWyMoPYe1?utm_scene=team_space"
updateTime: 1751427320000
exportedAt: 2026-05-14T12:10:27.842Z
source: dingtalk-document-mcp
---
# OCR识票后，能对发票自动进行费用类型匹配归类

| **修订时间** | **版本** | **编写人** | **修订说明** |
|----------------|----------|-------------|----------------|
| 20221201 | v1.0 | 张乔艳 | 新建 |
| 20221205 | v2.0 | 张乔艳 | 1、将自定义费用中“发票类目”设置统一放到【全局设置】；2、【全局设置】页面结构调整；3、MB端交互调整 |

## 1、需求背景

客户：武汉美和易思数字科技有限公司

背景：为了简化员工系统操作流程，希望在上传发票时能同时对发票进行费用类型归类

## 2、业务流程/架构

## 3、功能清单

| **模块** | **功能点** | **备注** |
|----------|-------------|----------|
| 全局设置 | 1、页面排版调整；增加「费用设置」tab页2、费用设置：支持批量维护“发票类目-费用类型映射关系”；支持针对费用设置发票类目限制 |  |
| 自定义费用 | 去掉“发票类目”设置，增加用户引导 |  |
| 发票 | MB端，上传发票后，支持自动匹配消费类型 |  |

## 4、需求详情

### 4.1、需求说明1

**系统：**【有成报销】

**一、全局设置**

**1、页面结构调整；增加「费用设置」tab页（图1）**

设置模块分tab页展示

增加「费用设置」tab页



![Picture 1](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4maOgXbM4zBWjlWN/img/549d3fef-5800-4fab-be50-bfa8cff85d11.png?Expires=1778767249&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=x9lel7Dc2Go4wY1pZqAcM6D7pj8%3D "")

图1

**2、费用设置-支持批量维护“费用类型-发票类目映射关系”；支持设置发票类目限制（图2）**

1）支持批量维护费用类型-发票类目映射关系
- 当配置列表只有一行时，不允许删除

2）支持设置发票类目限制
- 注释：开启后，系统将根据设置的“发票类目”与“费用类型”的映射关系表，对已选择的费用类型进行发票类目校验及发票上传限制

![Picture 2](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4maOgXbM4zBWjlWN/img/ede51dd6-b80d-421f-89cf-262f4b4aa011.png?Expires=1778767249&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=ie4d2VgkqNxQoySFO4m%2BBxKDeUI%3D "")

注：用户原来设置的数据需要同步



![Picture 3](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4maOgXbM4zBWjlWN/img/4b30e9ae-e2b0-4ac9-9561-3019aaf87d3f.png?Expires=1778767249&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=b7%2Bayv6PhQNewjmmDYtosgTFT%2F0%3D "")

图2

**二、自定义费用**

1、删除「发票类目」项

2、自定义费用页给出提示及引导（图3）
- 点击“去设置”跳转 全局设置—费用设置



![Picture 4](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4maOgXbM4zBWjlWN/img/d06ad59d-105b-422c-8ae3-125b8c278f74.png?Expires=1778767249&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=IAg00qCC4ve6OcYHQA3cAdGJ0Mc%3D "")

图3

**三、MB端——发票**

**1、费用归类校验逻辑**

【发票类目】与发票中【商品名称】进行校验，【商品名称】包含其中一个【发票类目】即算命中

**2、前端展示（暂时只做MB端调整）**
- **OCR识票后，有三种情况：匹配到一个消费类型、未匹配到消费类型、匹配到多个消费类型**匹配到一个消费类型，如（图8）未匹配到消费类型，不做页面提示匹配到多个费用类型，如（图9）



![Picture 5](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4maOgXbM4zBWjlWN/img/4d9693d9-2907-4ab9-ba02-0ca53fdd3f04.png?Expires=1778767249&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=wRh1dC1FrE5CQ77bpSdgp1yxu7Y%3D "")

![Picture 6](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4maOgXbM4zBWjlWN/img/2fa4020d-8418-44d6-9e8d-e0f14ea99a00.png?Expires=1778767249&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=4QMYREV4um0I67cb4muEcR7AO6o%3D "")

\<font style="background-color:#FBDE28;"\>图8\</font\>                                                                 \<font style="background-color:#FBDE28;"\>图9\</font\>
- **逐条生成消费**场景一：勾选的所有发票都已匹配到费用类型按已匹配到的费用类型逐条生成消费场景二：勾选发票中，部分未匹配到费用类型已匹配到发票按匹配到的费用类型生成消费，其他需手动选择费用类型后生成消费（图10）提示：发票：「住宿服务住宿费」「XX商品名称」未匹配到费用类型，无法生成消费。是否继续对其他发票生成消费？场景三：勾选的所有发票未匹配到费用类型展示“费用类型选择浮窗”，选择费用类型后，生成消费（和当前逻辑一样）



![Picture 7](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4maOgXbM4zBWjlWN/img/3e0c228e-3b76-4eaf-9b46-bed66eb8d0a9.png?Expires=1778767249&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=TZecMAm8mb4V%2BI2anGvPonHoDBg%3D "")

图10
- **合并生成消费**场景一：勾选发票都匹配到了费用类型，并且匹配到费用类型相同按已匹配到的费用类型合并生成消费场景二：勾选发票匹配到费用类型不同（包括部分匹配到，部分未匹配到的情况）展示“费用类型选择浮窗”，选择费用类型后，合并生成消费（和当前逻辑一样）场景三：勾选发票都未匹配到费用类型展示“费用类型选择浮窗”，选择费用类型后，合并生成消费（和当前逻辑一样）
