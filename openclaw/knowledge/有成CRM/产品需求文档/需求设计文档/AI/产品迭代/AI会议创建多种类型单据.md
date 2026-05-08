---
title: "AI会议创建多种类型单据"
tags:
  - 有成CRM
  - PRD
  - 需求设计文档-AI-产品�
created: 2026-03-24
source: 钉钉文档
original_url: https://alidocs.dingtalk.com/i/nodes/KGZLxjv9VG3RrkNQT46eePzYV6EDybno?utm_scene=team_space
node_id: KGZLxjv9VG3RrkNQT46eePzYV6EDybno
exported_at: 2026-03-22
---

# AI会议创建多种类型单据

> 🔗 **原文链接**：[AI会议创建多种类型单据 - 钉钉文档](https://alidocs.dingtalk.com/i/nodes/KGZLxjv9VG3RrkNQT46eePzYV6EDybno?utm_scene=team_space)

| 修订时间 | 版本 | 修订人 | 修订说明 |
|-----------------------------------------------------------------------|-----------------------------------------------------------------|--------------------------------------------------------------------|-----------------------------------------------------------------------|
| 2025-7-14 | v1.0 | 黄艺平 | 新建 |
|  |  |  |  |

## 需求详情

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/a2QnV4j2MD6dyO4X/img/6420fc1f-716f-4b9c-a13c-faa6bf690e29.png?Expires=1774165011&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=eNrBvvEs%2F7gXuhvii%2B%2Bkm5NvXOk%3D "")

| 需求 | 描述 |
|-----------------------------------------------------------------|-----------------------------------------------------------------|
| 自动建单 | 1、助理分类改为'AI自动建单'
2、支持新建助理
- 包涵系统预设的助理，最多可有5个建单助理，达到上限【新建助理】按钮隐藏
- 新建助理页面
<li style="margin-left:1em">创建单据对象及模板：可选目前AI可创建的单据类型及对应对象模板
<li style="margin-left:1em">必须创建单据：单选，
<li style="margin-left:1em">创建数据条数：单选，必填，默认‘1条’，可选‘依据AI分析（可多条或0条）’
<li style="margin-left:1em">对象业务描述：多行文本，非必填，未填写时取应用中心模块说明
<li style="margin-left:1em">生成数据额外展示：单选，选填，可选字段参考单据审批流程-摘要字段设置
- 自建的助理，可【编辑】【禁用】【启用】【删除】
3、系统预设的生成跟进助理上线时刷配置
- 助理名：自动生成跟进
- 创建单据对象：跟进记录
- 模板：根据企业目前配置
- 创建数据条数：1条
- 生成数据额外展示：对象类型
4、生成单据：如原型
5、助理中配置了需要自动生成单据的对象，均加上‘录音icon’
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/a2QnV4j2MD6dyO4X/img/3569ff79-b9b0-4be9-b369-be6a0101d3c7.png?Expires=1774165011&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=3kn%2FgVqUs6rM9EC0i4zb3lbHv1A%3D "") |


