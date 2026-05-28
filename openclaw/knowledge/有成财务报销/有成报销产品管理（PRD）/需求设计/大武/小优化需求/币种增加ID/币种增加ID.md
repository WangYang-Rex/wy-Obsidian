---
title: "币种增加ID"
nodeId: jb9Y4gmKWr7lmxrahaKOR0REVGXn6lpz
workspaceId: R2PmK2gngjVnZXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/jb9Y4gmKWr7lmxrahaKOR0REVGXn6lpz?utm_scene=team_space"
updateTime: 1751427293000
exportedAt: 2026-05-14T12:07:20.254Z
source: dingtalk-document-mcp
---
# 币种增加ID

| **修订时间** | **版本** | **作者** | **修订说明** |
|----------------|----------|----------|----------------|
| 20230207 | v1.0 | 大武 | 新建 |

## 1、需求背景

对接外部财务系统时，外部财务系统接口仅支持使用ID进行币种的映射，导致目前的凭证无法对接外币，增加币种ID的维护；

## 2、业务流程/架构

## 3、功能清单

根据个人需要补充

| **模块** | **功能点** | **备注** |
|----------|-------------|----------|
| 基础设置-币种设置 | 币种增加ID的维护功能 |  |
|  |  |  |
|  |  |  |

## 4、需求详情
1. 基础设置-币种设置增加ID的展示和维护；
2. 新增或者修改币种：增加ID，文字输入框，最大100个字符；非必填；不允许重复；保存时做唯一性校验；



![Picture 1](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/mxPOG5zrvko3KnKa/img/1377723f-bd87-4afd-a82c-a6bb12e7675f.png?Expires=1778766711&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=mlMtTnuzwVEh4IysNMHE1X0CbHs%3D "")
3. 列表展示增加ID的展示，没有填写则默认为空；
4. 接口对接时，如果没有编码则使用ID进行币种的传输；
