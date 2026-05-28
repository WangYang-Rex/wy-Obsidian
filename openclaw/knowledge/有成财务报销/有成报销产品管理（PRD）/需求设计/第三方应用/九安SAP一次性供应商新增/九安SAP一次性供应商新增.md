---
title: "九安SAP一次性供应商新增"
nodeId: o14dA3GK8g5NgQvGF9QyxY0MV9ekBD76
workspaceId: R2PmK2gngjVnZXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/o14dA3GK8g5NgQvGF9QyxY0MV9ekBD76?utm_scene=team_space"
exportedAt: 2026-04-01T02:14:34.123Z
source: dingtalk-document-mcp
---
# 九安SAP一次性供应商新增

| **修订时间** | **版本** | **修订说明** |
|----------------|----------|----------------|
| 20230131 | v1.0 | 新建 |

## 1、背景

目前有成报销的辅助核算供应商从SAP拉取，用户员工在填写单据时发现没有对应的供应商数据，需要先去SAP新增，再回到有成侧提单，客户希望优化流程，员工在有成侧新增即可，新增后数据同步给SAP，跟客户和SAP侧一起会议沟通后，尚未明确实现方案，有以下三种方案，评估对应的工时和报价待客户选择。

## 2、方案

方案一：有成侧作为一次性供应商的数据源，SAP主动获取有成侧数据

\<font style="background-color:#FBDE28;"\>预估工时：0.5d(包含联调)\</font\>改动点：1、有成侧不再主动拉取SAP的一次性供应商数据

2、有成侧辅助核算接口增加筛选条件

方案二：有成侧新增辅助核算后，发送消息通知给SAP来拉取新增数据

预估工时：2d(包含联调)

改动点：有成侧一次性供应商的增删改行为，需要实时通知SAP，默认有成侧新增数据为有效数据

方案三：有成侧支持新增供应商并将数据推送给SAP

\<font style="background-color:#FBDE28;"\>预估工时：5d(3d开发\+1d联调\+1d测试)\</font\>

改动点：辅助核算新增入口【新建单据】、【辅助核算列表】

新增时需要先拉取SAP的数据判断是否已经存在，新增后需要等待SAP返回是否成功
