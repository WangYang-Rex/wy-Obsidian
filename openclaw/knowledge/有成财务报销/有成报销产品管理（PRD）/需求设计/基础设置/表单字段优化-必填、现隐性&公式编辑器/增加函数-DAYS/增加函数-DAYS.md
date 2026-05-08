---
title: "增加函数-DAYS"
tags:
  - 有成报销
  - PRD
  - 需求设计-基础设置-表�
created: 2026-03-24
source: 钉钉文档
original_url: https://alidocs.dingtalk.com/i/nodes/KGZLxjv9VG3RrkNQT79AK9jAV6EDybno?utm_scene=team_space
node_id: KGZLxjv9VG3RrkNQT79AK9jAV6EDybno
exported_at: 2026-03-22
---

# 增加函数-DAYS

> 🔗 **原文链接**：[增加函数-DAYS - 钉钉文档](https://alidocs.dingtalk.com/i/nodes/KGZLxjv9VG3RrkNQT79AK9jAV6EDybno?utm_scene=team_space)

# 增加函数-DAYS

| **修订时间** | **版本** | **修订说明** |
|----------------|----------|----------------|
| 20240806 | v1.0 | 新建 |

## 1、需求背景

客户：东艾

需求描述：跨日即需要计算为一天，不考虑时间，目前DAY\_DIFF需要满24小时才计算为一天

## 2、需求详情

[<u>https://gykj.yuque.com/izoyhv/tzh23k/prlqphhhdlh531ye?singleDoc#ciOz</u>](https://gykj.yuque.com/izoyhv/tzh23k/prlqphhhdlh531ye?singleDoc#ciOz) 《编辑器字段、函数库》


![Picture 1](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1wvqrebLm8VbMnak/img/05a9a1ab-9a4f-4636-a207-65a60af04418.png?Expires=1774157048&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=69ayPyr%2FiCDdin4ChiNNO5jzmGY%3D "")

增加函数：DAYS；放在日期函数中：

1、函数在Excel中用于计算两个日期之间的天数差异。它会忽略时间部分，只考虑日期。

2、具体规则与描述见上面表格中；

3、如果是月份范围，需要将月份转换一下，开始月份转换为1号，结束日期转换为当前月份的最后一天：

比如：202407至202408，转换为：2024-07-01至2024-08-31202407至2024-09，转换为：2024-07-01至2024-09-30


实现东艾计算天数的函数示例：

=DAYS(结束日期,开始日期)\+1


![Picture 2](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1wvqrebLm8VbMnak/img/2c2f9b20-4f26-477d-a4f9-cda1b72c8edd.png?Expires=1774157048&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=XwsyhSTKwU%2FACrqURqiIdUqxznk%3D "")
