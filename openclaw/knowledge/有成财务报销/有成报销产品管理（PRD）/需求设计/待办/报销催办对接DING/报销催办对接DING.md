---
title: "报销催办对接DING"
nodeId: dQPGYqjpJYg0lZOdIdEX0nQYWakx1Z5N
workspaceId: R2PmK2gngjVnZXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/dQPGYqjpJYg0lZOdIdEX0nQYWakx1Z5N?utm_scene=team_space"
updateTime: 1751427348000
exportedAt: 2026-05-14T12:13:06.806Z
source: dingtalk-document-mcp
---
# 报销催办对接DING

| **修订时间** | **版本** | **修订说明** | **作者** |
|----------------|----------|----------------|----------|
| 20240313 | v1.0 | 新建 | 昭觉 |

## 1、涉及系统

有成报销 PC & MB   钉钉版

## 2、需求背景

客户：广州尚动计算机科技有限公司

## 3、业务流程/架构

如复杂需求，放置相关流程/架构图

## 4、功能清单

根据个人需要补充

:::info接口文档：本次使用 2.0 版本

[<u>https://open.dingtalk.com/document/isvapp/ding-2-0-hair-nail</u>](https://open.dingtalk.com/document/isvapp/ding-2-0-hair-nail)

:::

## 5、需求详情

### 5.1、需求说明

#### PC



![Picture 1](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/vBPlN5jL6V2okOdG/img/7224827f-3f5b-472d-a196-8d2e72c8290d.png?Expires=1778767482&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=mTlo87Sfw6sRMGDs%2Btrwqd%2Blup4%3D "")

单据详情页点击【催办】，展示新建 DING 弹窗：



![Picture 2](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/vBPlN5jL6V2okOdG/img/a36ae1d1-5e97-4171-89bd-517afe630fa9.png?Expires=1778767482&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=rF2GDIysrGwZxKwpXcBUX0mo3O8%3D "")



![Picture 3](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/vBPlN5jL6V2okOdG/img/f6b17ce7-7c89-4589-b8ae-476415090976.png?Expires=1778767482&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=tsTtstXN9R7qU5kIj8X8ZEVADxc%3D "")



![Picture 4](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/vBPlN5jL6V2okOdG/img/5f275a5b-9ade-4c90-8100-9b719290e8e1.png?Expires=1778767482&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=aUCh%2FOxeU3LqwtehdWqAtKNAB%2Fk%3D "")



![Picture 5](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/vBPlN5jL6V2okOdG/img/20c54f22-5d5d-4e44-954d-8dc1ead267a0.png?Expires=1778767482&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=nO2J7g%2FeOMraRgoIIvRJVv9XyQQ%3D "")

#### MB



![Picture 6](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/vBPlN5jL6V2okOdG/img/c5e7e478-c95b-41ae-af40-5c1675d52b32.png?Expires=1778767482&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=eEZZvQf5qgfyf5xgqOGH5B%2Bz0AY%3D "")

![Picture 7](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/vBPlN5jL6V2okOdG/img/f46878fa-0231-4892-802f-e5aa2a38bf67.png?Expires=1778767482&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=aNmFwN0T57fxIFB%2BwtKhrstlbjU%3D "")



![Picture 8](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/vBPlN5jL6V2okOdG/img/57c8a572-0c4f-4d3f-9c64-75e323e51e77.png?Expires=1778767482&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=M5nHJhD%2FoSA9uTryisrwvMi0ITs%3D "")

![Picture 9](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/vBPlN5jL6V2okOdG/img/c5e7e478-c95b-41ae-af40-5c1675d52b32.png?Expires=1778767482&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=eEZZvQf5qgfyf5xgqOGH5B%2Bz0AY%3D "")

#### 字段对应



![Picture 10](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/vBPlN5jL6V2okOdG/img/d794ac80-744c-4974-9d89-6813421f3747.png?Expires=1778767482&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=r2FOzlQcWZXNdmHrwil3tVffmu0%3D "")

| **DING 字段** | **报销字段** | **备注说明** |
|---------------|----------------|----------------|
| users | 当前审批节点匹配到的全部审批人 |  |
| corpld | 企业的 corpld |  |
| type | 链接--审批任务详情页 |  |
| alertType | 根据弹窗选择的参数 |  |
| alertDate | 定时钉发送时间 |  |
| text | \{申请人\}提醒您审批\{单据名称\} |  |
| bizType | 默认：0 |  |
