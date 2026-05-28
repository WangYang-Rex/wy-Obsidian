---
title: "crm在钉钉上与报销不同版本打通"
nodeId: QG53mjyd80Rjq0QOCdpkYxbAV6zbX04v
workspaceId: R2PmK2Q8rxRbeXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/QG53mjyd80Rjq0QOCdpkYxbAV6zbX04v?utm_scene=team_space"
exportedAt: 2026-03-31T04:27:53.240Z
source: dingtalk-document-mcp
---
# crm在钉钉上与报销不同版本打通

| **修订时间** | **版本** | **修订人** | **修订说明** |
|----------------|----------|-------------|----------------|
| 20221009 | v1.0 | 黄艺平 | 新建 |
|  |  |  |  |

## 1、需求背景

报销在钉钉上有多个版本：

1）有成财务V1：黄色财务\+黄色报销（新企业已经无法开通到该版本了）

2）有成财务V2：黄色财务\+蓝色报销（有授权码）

3）有成报销：蓝色独立版报销（有授权码）

在有成CRM中快捷新建报销单据时，目前系统中，是通过以下逻辑判断打开的是什么界面：

1、未绑定授权码：打开有成财务V1中黄色报销；

2、绑定授权码：打开有成财务V2中蓝色报销。

存在的问题：

1）如果客户购买的是蓝色独立版报销的情况，此时就会出现新建时报错的情况，如下截图所示：

2）存在客户应用切换的情况，如最开始购买的是有成财务V2中的报销，后续改为蓝色独立版报销，目前系统中一旦绑定了授权码就没有入口再允许用户更改了。



![Picture 1](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/oJGq75kaEAM06lAK/img/3efa3347-d302-472b-8f52-f815a9249c97.png?Expires=1774938476&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=e9lxJjwRtypjn%2BVrrg5nuK%2Fqllg%3D "")

解决方案：1）在绑定授权码时，支持用户选择要绑定的应用（不考虑用户同时开通有成财务、有成报销的情况）；2）支持用户更改绑定信息。

## 2、需求详情

| **需求** | **描述** |
|----------|----------|
| 应用中心 | 一、绑定授权码1、新增字段【绑定应用】：单选，必填，枚举值‘有成财务（报销模块）、有成报销’；2、历史绑定了授权码的客户，该新增字段值统一刷成‘有成财务（报销模块）’；二、新增‘变更授权码绑定’按钮及弹窗1、判断条件：\{授权码\}不为空的客户，该入口出现2、点击该按钮，出现‘变更授权码绑定’弹窗，并默认带出目前该企业授权绑定设置。三、点击有成报销-前往应用1、\{绑定应用\}为空，进入有成财务V1应用中的报销模块；2、\{绑定应用\}=‘有成财务（报销模块）’  & 授权码，进入有成财务V2应用中的报销模块；3、\{绑定应用\}=‘有成报销’ & 授权码，进入有成报销应用。 |
| 其他相关模块 | 在有成crm快捷新建报销单时：根据\{绑定应用\}& 授权码的值（具体见上），进入不同的应用/模块。 |

![Picture 2](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/oJGq75kaEAM06lAK/img/4b802df4-7260-420d-8a7c-2ed28022bd98.png?Expires=1774938476&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=%2BbHsAxVgVX9gAt8m6itzyPqk40k%3D "")

![Picture 3](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/oJGq75kaEAM06lAK/img/1b58c706-d201-4121-b51b-2d39c57505e5.png?Expires=1774938476&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=O8qMvHdJgasyKzzjgsCG%2FCDPNrk%3D "")
