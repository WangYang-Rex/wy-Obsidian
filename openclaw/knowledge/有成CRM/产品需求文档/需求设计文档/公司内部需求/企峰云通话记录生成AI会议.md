---
title: "企峰云通话记录生成AI会议"
nodeId: r1R7q3QmWe7M9wKYh6Ewvr7xJxkXOEP2
workspaceId: R2PmK2Q8rxRbeXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/r1R7q3QmWe7M9wKYh6Ewvr7xJxkXOEP2?utm_scene=team_space"
updateTime: 1787628805000
exportedAt: 2026-08-26T04:11:33.538Z
source: dingtalk-document-mcp
---
| 修订时间 | 版本 | 修订人 | 修订说明 |
|-----------------------------------------------------------------------|-----------------------------------------------------------------|--------------------------------------------------------------------|-----------------------------------------------------------------------|
| 2026-8-25 | v1.0 | 黄艺平 | 新建 |
|  |  |  |  |

## 需求背景

目前有成系列中，跟进记录填写的质量较差，销售是否真的拨打电话跟进也未知。

目标：销售通过企峰云拨打/接通电话--\>生成通话记录--\>AI会议--\>跟进记录

## 接口文档

[通话信息同步接口.doc](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/QvjnA3J1MA3zbOXo/att/e8a62fba-287c-4948-b660-f557d96ae378.doc?Expires=1787724694&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=VS6vcv7GU2qEweaFbELbtIPSkgM%3D)

## 需求详情

| 需求 | 描述 |
|-----------------------------------------------------------------|-----------------------------------------------------------------|
| 企峰云通话记录生成AI会议 | 一、有成系列.员工中增加字段企峰云号码：user\_mob\_0归属产品线：user\_select\_0二、获取企峰云通话记录（见接口文档）三、生成AI会议AI会议.模板：=默认模板AI会议.对象类型：=客户AI会议.会议对象：callType=1（已接来电）：查找 客户-电话（custom\_tele）中，包含本次通话的主叫号码（callerNum）的客户callType=2（已拨电话）：查找 客户-电话（custom\_tele）中，包含本次通话的被叫号码（calledNum）的客户备注：若查找到多个，优先依据本次会议的负责人，查看员工中的归属产品线，匹配 客户-产品（custom\_source）相同的客户；以上条件未匹配到，则默认取第一个AI会议.会议方式：=电话沟通AI会议.会议类型：=其他（需要新增枚举值）AI会议.会议开始时间：=企峰云.startTimeAI会议.会议结束时间：=会议开始时间\+会议时长AI会议.会议时长（秒）=企峰云.timeLengthAI会议.负责人callType=1（已接来电）：查找 员工-user\_mob\_0，包含本次通话的被叫号码（calledNum）的员工callType=2（已拨电话）：查找 员工-user\_mob\_0，包含本次通话的被叫号码（callerNum）的员工备注：若查找到多个，则默认取第一个AI会议.音视频文件：=企峰云.recordURLAI会议.创建人：=同负责人AI会议.创建时间：=企峰云.startTimeAI会议.最后修改人：=同负责人AI会议.最后修改时间：=企峰云.startTime |
