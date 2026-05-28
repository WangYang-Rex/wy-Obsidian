---
title: "我的-发票列表增加选中数据小计显示，mb发票、消费交互优化"
nodeId: a9E05BDRVQ6L3R7yHqMj3rGxJ63zgkYA
workspaceId: R2PmK2gngjVnZXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/a9E05BDRVQ6L3R7yHqMj3rGxJ63zgkYA?utm_scene=team_space"
updateTime: 1756864613000
exportedAt: 2026-05-14T12:10:23.583Z
source: dingtalk-document-mcp
---
| 修订时间 | 版本 | 修订说明 |
|------------|------|------------|
| 20250813 | v1.0 | 新建 |
| 20250826 | v1.1 | mb发票、消费交互优化 |

# **1\. 需求背景**

产品规划

用户希望能够在pc端也清晰知道，已经选中了多少张发票、金额多少，方便大量报销情况下核对金额。

另外我们MB选择发票和选择消费的交互方案没有统一，这次也一并优化掉。

# **2\. 业务流程/架构**

# **3\. 功能清单**

| 模块 | 功能点 | 备注 |
|------|---------|------|
| 我的-发票 | 我的-发票列表增加选中数据小计显示 |  |
|  | 移动端交互优化 |  |
|  |  |  |

# **4\. 需求详情**

PC：我的-发票页面，发票总额格式优化为千分位两位小数。右边增加“已选x张发票，金额小计：xxx,xxx.xx”实时统计用户选择的发票数量、金额。~~支持跨页统计。~~

MB：交互修改见图。

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/J9LnW6jWpWQbQlvD/img/42364977-28a5-4af7-9c78-147a671ab9d0.png?Expires=1778767242&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=sQHF%2B%2B%2BivQJT3wTmVIlhu6k7yqM%3D "")


