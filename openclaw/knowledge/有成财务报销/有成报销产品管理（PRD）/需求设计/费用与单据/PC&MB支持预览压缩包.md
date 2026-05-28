---
title: "PC&MB支持预览压缩包"
nodeId: ZgpG2NdyVXrOqRxzHygDeL1N8MwvDqPk
workspaceId: R2PmK2gngjVnZXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/ZgpG2NdyVXrOqRxzHygDeL1N8MwvDqPk?utm_scene=team_space"
exportedAt: 2026-04-01T02:24:40.305Z
source: dingtalk-document-mcp
---
| 修订时间 | 版本 | 修订说明 |
|------------|------|------------|
| 20251104 | v1.0 | 新建 |
|  |  |  |

# **1\. 需求背景**

用户希望在移动端审批单据的时候，预览单据压缩包附件中的内容。

客户：九安医疗

# **2\. 业务流程/架构**

# **3\. 功能清单**

| 模块 | 功能点 | 备注 |
|------|---------|------|
| PC&MB | 支持预览压缩包 |  |
|  |  |  |
|  |  |  |

# **4\. 需求详情**

查看单据、费用、辅助核算、项目上的附件压缩包（本期需要支持格式：rar、7z、zip）时，新页面打开压缩包预览。

PC交互

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4j6OJ5jpLk52Rq3p/img/6a645b2b-a85c-4567-819e-8e5d4d8c2520.png?Expires=1775017480&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=9vr4TmM7u81P64oc0QjZ%2BV4%2FkII%3D "")
- 点击图标默认预览，点击下载图标下载压缩包。
- 新标签页打开预览压缩包里的文件结构，点击文件夹支持打开文件夹里的结构。
    - 点击具体文件时，如果文件本身已经是支持预览的格式，则新标签页打开文件的预览。
    - 如果文件本身不是支持预览的格式，则提示用户“该文件暂不支持预览”。
    - 暂不支持压缩包里预览压缩包。

MB交互

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4j6OJ5jpLk52Rq3p/img/d1b6311c-7536-4af2-bce4-27a7ab154fb9.png?Expires=1775017480&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=dhCWARnXW7CahpbeOOb2DscIOhY%3D "")

移动端交互类似，为了方便移动端用户，预览压缩包内文件时支持下载整个压缩包。
