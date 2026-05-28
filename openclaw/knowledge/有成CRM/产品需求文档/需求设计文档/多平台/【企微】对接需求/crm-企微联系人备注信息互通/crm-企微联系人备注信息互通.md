---
title: "crm-企微联系人备注信息互通"
nodeId: EpGBa2Lm8azv1ZANHZ94mm5xWgN7R35y
workspaceId: R2PmK2Q8rxRbeXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/EpGBa2Lm8azv1ZANHZ94mm5xWgN7R35y?utm_scene=team_space"
exportedAt: 2026-03-31T04:30:49.758Z
source: dingtalk-document-mcp
---
# crm-企微联系人备注信息互通

| **修订时间** | **版本** | **修订人** | **修订说明** |
|----------------|----------|-------------|----------------|
| 2023-5-31 | v1.0 | 黄艺平 | 新建 |
|  |  |  |  |

## 1、需求背景

历史做了企微-crm联系人自动同步，需要做企业员工对该联系人的备注信息的双向同步。（客户付费）

相关接口：[<u>https://developer.work.weixin.qq.com/document/path/92265</u>](https://developer.work.weixin.qq.com/document/path/92265)



![Picture 1](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ybEnB5j984rKBlP1/img/c3d5a0e0-66f5-43e4-ba49-a04e5400cd08.png?Expires=1774938651&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=NqkZooYClqmykq7Wdsue1xojT9A%3D "")

## 2、需求详情

| **需求** | **描述** |
|----------|----------|
| 联系人备注信息互通 | 说明：联系人的匹配企微----\>crm：同查重条件crm----\>企微：外部联系人userid总体需求：crm.联系人.爱好（系统字段）\<------\>企微.联系人.企业crm侧企微侧1、crm联系人‘爱好’字段历史数据处理：根据crm联系人的负责人，获取该负责人在企微对该联系人的‘企业’维护（未添加为联系人 则为null）；\+ 只给力辰科仪（crmwpR4g7DAAA36-QaYnaUS3AMupkDJd38Q）处理2、crm侧操作2.1 直接修改‘爱好’信息：更新该联系人的负责人，在企微对该联系人的‘企业’维护；\+ ‘爱好’字段值改为空，不会更新企微侧‘企业’数据2.2 变更负责人（包括直接变更联系人的负责人\+联系人关联的客户从公海分配/领取\+联系人关联的客户变更负责人）and ‘企业’值不为空：更新crm中联系人‘爱好’，取新的负责人在企微对该联系人的‘企业’维护（企微中‘企业’有值时才更新）；\+ 目前合并客户/客户覆盖导入可以变更客户负责人，但是不会同步变更联系人的负责人\+ 客户/联系人负责人=null，此时只操作变更联系人的负责人，不会重新取企微侧数据；备注：企微中‘企业’字段字符限制20，crm侧单行文本字符限制\>20，故在同步时，有多余部分直接截断。3、企微操作3.1 该联系人的负责人 在企微更新‘企业’ 信息：更新crm中该联系人的‘爱好’信息 |

![Picture 2](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ybEnB5j984rKBlP1/img/c28498c8-4034-491f-8cb7-a8b7ba03875f.png?Expires=1774938651&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=t042WnqWf2jBp6fxpgcx0RrLMuw%3D "")

![Picture 3](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ybEnB5j984rKBlP1/img/ff7c9717-fda9-4de5-8e4e-90a654d7c2dd.png?Expires=1774938651&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=MNHqW%2FfIxrSQ1Oq4jHcxg2ecJwo%3D "")

![Picture 4](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ybEnB5j984rKBlP1/img/c3d5a0e0-66f5-43e4-ba49-a04e5400cd08.png?Expires=1774938651&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=NqkZooYClqmykq7Wdsue1xojT9A%3D "")
