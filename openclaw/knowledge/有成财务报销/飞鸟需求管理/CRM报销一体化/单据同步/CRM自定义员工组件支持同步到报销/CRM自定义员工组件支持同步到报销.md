---
title: "CRM自定义员工组件支持同步到报销"
nodeId: qnYMoO1rWxDlYrR6CKMxakraW47Z3je9
workspaceId: R2PmK2gngjVnZXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/qnYMoO1rWxDlYrR6CKMxakraW47Z3je9?utm_scene=team_space"
updateTime: 1751427098000
exportedAt: 2026-05-14T12:13:36.270Z
source: dingtalk-document-mcp
---
# CRM自定义员工组件支持同步到报销

| **修订时间** | **版本** | **修订说明** |
|----------------|----------|----------------|
| 20240903 | v1.0 | 新建 |

## 1、需求背景

客户：智维精准（北京）医疗科技有限公司

目前：

在CRM中，在业务模版中添加了人员组件，在CRM报销一体化中，无法将员工组件配置上，配置后保存将会提示非人员类型字段

![Picture 1](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/NpQlK5jNGRZ0ZqDv/img/88445e7d-45a7-4b7b-9b10-b1c09773c719.png?Expires=1778767524&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=H3ykWrM%2F%2F9lvwB6pwKC%2FjMfZznQ%3D "")



![Picture 2](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/NpQlK5jNGRZ0ZqDv/img/58e51566-f32b-4999-a2d6-dc90e22f52e2.png?Expires=1778767524&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=sXzgMdMQYK7U1n5dCz9fhGO3r00%3D "")

## 2、需求详情

1、同步关系配置时，支持CRM中的“人员单选”，“人员多选”组件参与员工组件的配置；

2、配置后将员工信息同步到报销：
- 人员单选
- 人员多选：当报销中的“员工”组件支持多选时，可同步成功，若未同步成功，记录同步记录
