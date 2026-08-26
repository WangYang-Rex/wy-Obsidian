---
title: "增加函数-DAYS"
nodeId: KGZLxjv9VG3RrkNQT79AK9jAV6EDybno
workspaceId: R2PmK2gngjVnZXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/KGZLxjv9VG3RrkNQT79AK9jAV6EDybno?utm_scene=team_space"
updateTime: 1751427317000
exportedAt: 2026-08-05T04:26:24.710Z
source: dingtalk-document-mcp
---
# 增加函数-DAYS

| **修订时间** | **版本** | **修订说明** |
|----------------|----------|----------------|
| 20240806 | v1.0 | 新建 |

## 1、需求背景

客户：东艾

需求描述：跨日即需要计算为一天，不考虑时间，目前DAY\_DIFF需要满24小时才计算为一天

## 2、需求详情

[<span style="color: #0000FF;"><u>https://gykj.yuque.com/izoyhv/tzh23k/prlqphhhdlh531ye?singleDoc#ciOz</u></span>](https://gykj.yuque.com/izoyhv/tzh23k/prlqphhhdlh531ye?singleDoc#ciOz) 《编辑器字段、函数库》



![Picture 1](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1wvqrebLm8VbMnak/img/05a9a1ab-9a4f-4636-a207-65a60af04418.png?Expires=1785910966&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=hLX3rpLpckuYBf3ut28u7CK8LD0%3D "")

增加函数：DAYS；放在日期函数中：

<span style="color: #2C2C36;">1、函数在Excel中用于计算两个日期之间的天数差异。它会忽略时间部分，只考虑日期。</span>

<span style="color: #2C2C36;">2、具体规则与描述见上面表格中；</span>

<span style="color: #2C2C36;">3、如果是月份范围，需要将月份转换一下，开始月份转换为1号，结束日期转换为当前月份的最后一天：</span>

<span style="color: #2C2C36;">比如：202407至202408，转换为：2024-07-01至2024-08-31</span><span style="color: #2C2C36;">202407至2024-09，转换为：2024-07-01至2024-09-30</span>



<span style="color: #2C2C36;">实现东艾计算天数的函数示例：</span>

<span style="color: #2C2C36;">=DAYS(结束日期,开始日期)\+1</span>



![Picture 2](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1wvqrebLm8VbMnak/img/2c2f9b20-4f26-477d-a4f9-cda1b72c8edd.png?Expires=1785910966&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=lRKYoLF7vx19YPW0imKcc8RQEP4%3D "")
