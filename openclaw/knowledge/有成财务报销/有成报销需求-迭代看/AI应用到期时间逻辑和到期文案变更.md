---
title: "AI应用到期时间逻辑和到期文案变更"
nodeId: amweZ92PV6vZeDLpIKEagKMbVxEKBD6p
workspaceId: R2PmK2gngjVnZXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/amweZ92PV6vZeDLpIKEagKMbVxEKBD6p?utm_scene=team_space"
updateTime: 1779071321000
exportedAt: 2026-05-28T11:32:54.991Z
source: dingtalk-document-mcp
---
> **版本**：v1.0 \| **产品**：有成报销v2.0 \| **客户**：北京智源人工智能研究院 \| **需求类型**：平台适配 **修订记录**：v1.0(20260511)初始版本   

---

# **需求背景**

对产研团队增加了AI付费客户数和AI使用活跃率考核，为提高ai功能使用率，先将ai功能默认全部放开，未来按使用量和订阅付费

# **功能清单**

##### **AI应用到期时间逻辑变更；****补充ai审批规则上限**

# **需求详情**

| 模块 | 功能点 | 备注 |  |
|------|---------|------|---|
| 1、存量报销老客户未付费ai的 | 报销的付费未到期客户且未付费ai的客户（无ai订单），把ai应用的到期时间刷成报销产品到期时间一致，剔除ai的付费客户名单（名单在下面） | 刷数据 | 湖南立羽文化发展有限公司 |
| 2、新开通和新下单的报销的客户 | 默认开通ai应用和ai助理悬浮窗，且ai的到期时间为报销软件到期时间 | 开通下单逻辑 |  |
| 3、文案修改 | <ul><li>新文案：【公告：限时赠送1万点AI额度使用，额度用尽后如需继续使用，欢迎联系客服】</li><br><li>上面已付费AI应用客户的公告不显示</li></ul> |  |  |

刷数据初始化：

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/oJGq75k7mV8NylAK/img/677e1fdb-117c-4a2d-8c29-b1136cf3cd14.png?Expires=1779975175&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=nIT%2BAdGXn5oP5B3vdS8v3HVCJP8%3D "")



已经付费名单如下：

| 湖南立羽文化发展有限公司 | yccwding6f1c92bd726e3e1435c2f4657eb6378f |
|------------------------------------|----------------------------------------|
| 广州蜻蜓出行科技有限公司 | yccwding35bac1b99e3e267f4ac5d6980864d335 |
| 浙江同心母婴 | yiqbding9852233b49e34ffc |
| 浙江铂科电子股份有限公司 | yiqbding5bd40dd8511df7214ac5d6980864d335 |
| 赛旺检验检测认证有限公司 | yiqbding203787fdd480622e4ac5d6980864d335 |
| 吉林省太羽科技制造有限公司 | yiqbding80d7868a7afc502cf2c783f7214b6d69 |

## 到期文案变更

![画布 28.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/oJGq75k7mV8NylAK/img/cb7b89a2-e62f-45ef-b095-4b7f083e9857.png?Expires=1779975175&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=15nRPYSBjPVvW6xm9ewe8m5kFrY%3D "")

**功能描述：**
- 新文案：【公告：限时赠送1万点AI额度使用，额度用尽后如需继续使用，欢迎联系客服】
- 上面已付费AI应用客户的公告不显示


