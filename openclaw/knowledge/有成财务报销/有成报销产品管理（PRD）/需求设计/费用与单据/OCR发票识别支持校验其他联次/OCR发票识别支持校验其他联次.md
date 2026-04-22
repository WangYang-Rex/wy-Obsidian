---
title: "OCR发票识别支持校验其他联次"
tags:
  - 有成报销
  - PRD
  - 需求设计-费用与单据-O
created: 2026-03-24
source: 钉钉文档
original_url: https://alidocs.dingtalk.com/i/nodes/YndMj49yWjPvNlg2I0GZNqqBJ3pmz5aA?utm_scene=team_space
node_id: YndMj49yWjPvNlg2I0GZNqqBJ3pmz5aA
exported_at: 2026-03-22
---

# OCR发票识别支持校验其他联次

> 🔗 **原文链接**：[OCR发票识别支持校验其他联次 - 钉钉文档](https://alidocs.dingtalk.com/i/nodes/YndMj49yWjPvNlg2I0GZNqqBJ3pmz5aA?utm_scene=team_space)

# OCR发票识别支持校验其他联次

| **修订时间** | **版本** | **编写人** | **修订说明** |
|----------------|----------|-------------|----------------|
| 20221118 | v1.0 | 张乔艳 | 新建 |

## 1、需求背景

客户：广东空港城航空发展有限公司

背景：因限行税法规定，发票联如果丢失，是可以直接以抵扣联作为记账凭证的，如果抵扣联也丢失，可凭加盖销售方发票专用章的记账联复印件作为抵扣凭证和记账凭证

## 2、业务流程/架构

## 3、功能清单

| **模块** | **功能点** | **备注** |
|----------|-------------|----------|
| 全局设置 | 发票设置中新增开关：是否限制只校验发票联 |  |
| OCR发票识别 | 支持校验其他联次 |  |

## 4、需求详情

### 4.1、需求说明1

**系统：**【有成财务】&【有成报销】

**解决方案**：全局设置-发票设置中新增开关：是否限制只校验发票联
- 默认开启——只允许对发票联进行校验（现有逻辑）
- 关闭时，支持对其他联次进行校验（抵扣联、记账联）
-  注释文案：开启时，只允许上传发票联；关闭时，允许所有联次的发票上传

![Picture 1](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/NpQlK5jN7YxveqDv/img/f7273ec8-9c5b-4aad-9365-51d32ca5c830.png?Expires=1774157317&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=E4nSalQACxhaaoE%2B8DYYJCjeJGk%3D "")


![Picture 2](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/NpQlK5jN7YxveqDv/img/d405257e-dc54-4c74-a33b-905a09b04081.png?Expires=1774157317&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=Zfbgt44lIJGo5k7jXAKJM%2BT3dAQ%3D "")


![Picture 3](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/NpQlK5jN7YxveqDv/img/5f06a72b-c882-4e57-a142-c208bdbdfc5b.png?Expires=1774157317&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=7g7g1UOUvDyAVrREX8eoViaDtd0%3D "")
