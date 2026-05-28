---
title: "项目详情页新增“有成报销”Tab"
nodeId: a9E05BDRVQ6L3R7yHmEB4dkzJ63zgkYA
workspaceId: R2PmK2Q8rxRbeXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/a9E05BDRVQ6L3R7yHmEB4dkzJ63zgkYA?utm_scene=team_space"
exportedAt: 2026-03-31T04:29:08.992Z
source: dingtalk-document-mcp
---
# 项目详情页新增“有成报销”Tab

| **修订时间** | **版本** | **修订人** | **修订说明** |
|----------------|----------|-------------|----------------|
| 2022-08-01 | v1.0 | 瀚海 | 新建 |
| 2022-08-02 | v1.1 | 瀚海 | 新增了根据报销权限，展示单据数据 |
| 2022-08-03 | v1.2 | 瀚海 | 补充了移动端交互 |
| 2022-08-23 | v1.3 | 黄艺平 | 补充了项目未同步的提示说明 |

## 1、需求背景
1. 期望能在项目详情页，查看到所有报销单、借款单、付款单的明细数据。最终实现项目相关的所有单据，都可以在CRM中查看

## 2、业务流程/架构

## 3、功能清单

| **模块** | **功能点** | **备注** |
|----------|-------------|----------|
| 项目详情页，新增“有成报销”Tab | 1\. tab展示规则2\. 展示数据：展示有成报销内，所有关联该项目的报销单、借款单、付款单3\. 新增操作：支持新增报销单，跳转到有成报销页面4\. 查看详情：支持侧边栏打开有成报销详情页 |  |

## 4、需求详情

### 4.1、项目详情页，新增“有成报销”Tab

| **模块** | **说明** |
|----------|----------|
| tab展示规则 | 1\. 在应用中心-有成报销-授权开通之后的企业，才会在项目详情页展示此tab（PC和MB都展示）2\. 项目详情页，新增“有成报销”tab。位置在工单下方 |
| 展示数据 | 1\. 展示有成报销内，所有关联该项目，且“单据类型”为报销单、借款单、付款单的单据2\. 根据当前用户的在有成报销侧权限，展示对应的单据（根据用户权限判断，如果用户是管理员则返回全部单据，如果用户有报销管理\+借款管理\+付款管理 权限则返回全部，否则返回有权限模块的全部数据\+个人数据）3\. 支持筛选单据类型：全部、报销单、借款单、付款单4\. 分别展示汇总数据：\+ 总金额：金额字段之和\+ 报销金额：单据类型为“报销单”的金额之和\+ 借款金额：单据类型为“借款单”的金额之和\+ 付款金额：单据类型为“付款单”的金额之和   备注：报销那侧对于多币种做了处理，我们只要累加“金额”这列之和即可备注：若项目未同步到报销，则按如下展示 |
| 新增操作 | 1\. 点击新增后，根据所在的分组，展示不同的单据类型：   （1）在报销单分组，点击“新增”，则展示有成报销侧单据分类为“报销单”的单据   （2）在借款单分组，点击“新增”，则展示有成报销侧单据分类为“借款单”的单据   （3）在付款单分组，点击“新增”，则展示有成报销侧单据分类为“付款单”的单据2\. 确认后，打开有成报销页面，新建对应单据，并自动关联当前项目 |
| 查看详情 | 1\. 点击详情页，侧边栏打开有成报销的单据详情页 |

![Picture 1](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1X3lE5jd2jx34lJb/img/37300003-08c4-43fe-91cd-0cb96982fd72.png?Expires=1774938553&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=xbb3EVpdodw5iY7iDwcyKMi%2BX3A%3D "")

![Picture 2](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1X3lE5jd2jx34lJb/img/97bdbb7d-a5d6-4d20-9907-29f476c2e060.png?Expires=1774938553&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=Hado1K8mgBitBYODDiV4IGGVZ9I%3D "")

![Picture 3](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1X3lE5jd2jx34lJb/img/2a0cd6dd-6b22-43d8-977e-765746a55aaa.png?Expires=1774938553&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=PaZFkiI2aoyfV%2BPFtb9CcDakLOc%3D "")

![Picture 4](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1X3lE5jd2jx34lJb/img/7d96699e-333a-42b5-8ad0-dd562a74fac8.png?Expires=1774938553&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=H70kUMqrSH5bQ2%2FGvPhqW%2BKZB8k%3D "")

![Picture 5](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1X3lE5jd2jx34lJb/img/c14a939d-826e-40de-8681-ca687cbb1792.png?Expires=1774938553&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=E%2FrVr%2B55wLRcZWj8mWoDEgXwMWw%3D "")
