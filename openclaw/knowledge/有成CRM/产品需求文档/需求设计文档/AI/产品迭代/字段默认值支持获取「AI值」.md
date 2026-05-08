---
title: "字段默认值支持获取「AI值」"
tags:
  - 有成CRM
  - PRD
  - 需求设计文档-AI-产品�
created: 2026-03-24
source: 钉钉文档
original_url: https://alidocs.dingtalk.com/i/nodes/Qnp9zOoBVBZzNDrmt5EG26NQV1DK0g6l?utm_scene=team_space
node_id: Qnp9zOoBVBZzNDrmt5EG26NQV1DK0g6l
exported_at: 2026-03-22
---

# 字段默认值支持获取「AI值」

> 🔗 **原文链接**：[字段默认值支持获取「AI值」 - 钉钉文档](https://alidocs.dingtalk.com/i/nodes/Qnp9zOoBVBZzNDrmt5EG26NQV1DK0g6l?utm_scene=team_space)

| 修订时间 | 版本 | 修订人 | 修订说明 |
|-----------------------------------------------------------------------|-----------------------------------------------------------------|--------------------------------------------------------------------|-----------------------------------------------------------------------|
| 2025-11-11 | v1.0 | 黄艺平 | 新建 |
|  |  |  |  |

## 需求详情

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/5VLqXLbkr7zQgqX1/img/1e2531dd-8cdf-466a-a83d-cadb974b46d3.png?Expires=1774165012&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=CrUHve7C%2BivF43pY0xbm%2BXrXaDA%3D "")

| 需求 | 描述 |
|-----------------------------------------------------------------|-----------------------------------------------------------------|
| 默认值可配置「AI值」 | 1、可配置的字段类型：限主表单中以下类型控件
单行文本、多行文本、单选、多选、多级单选、网址、手机、电话、整数、小数、传真、邮件、金额、身份证、日期、日期时间、百分比、地址、~~关联单选、关联多选、人员单选、人员多选、部门单选、部门多选~~
2、单对象最多可1个字段设置AI值，达到上限时其余字段默认值设置该选项不可见
3、设置规则
- 规则描述：最多1000字符
- 插入字段
<li style="margin-left:1em">同计算公式设置，但是可插入字段不能是本表单中设置了默认值-计算公式/AI值、统计字段、计算字段的字段
<li style="margin-left:1em">最多可插入10个字段
- 预览调试
<li style="margin-left:1em">可选择该字段所在对象中某条数据~~（不校验数据权限）~~
<li style="margin-left:1em">点击【运行】依据字段类型返回ai分析结果.md
4、新建编辑页面对应字段增加‘AI’标记、分析进度--见设计稿 |
| 版本控制 | ~~仅开通AI销售助理企业才有，~~后台可单独开启
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/5VLqXLbkr7zQgqX1/img/8685e701-d548-4eed-a283-2f6ac4ef38b3.png?Expires=1774165012&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=sNNFQU82Z%2B6HEvJy3zrqzbKxcmQ%3D "") |


