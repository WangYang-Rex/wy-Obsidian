---
title: "快麦erp对接有成财务单点登录"
tags:
  - 有成财务
  - 产品管理
  - .
created: 2026-03-24
source: 钉钉文档
original_url: https://alidocs.dingtalk.com/i/nodes/MNDoBb60VLrO7YzkHrM65dX68lemrZQ3?utm_scene=team_space
node_id: MNDoBb60VLrO7YzkHrM65dX68lemrZQ3
exported_at: 2026-03-22
---

# 快麦erp对接有成财务单点登录

> 🔗 **原文链接**：[快麦erp对接有成财务单点登录 - 钉钉文档](https://alidocs.dingtalk.com/i/nodes/MNDoBb60VLrO7YzkHrM65dX68lemrZQ3?utm_scene=team_space)
> 📅 **导出时间**：2026-03-22

| 修订时间 | 版本 | 修订说明 |
|------------|------|------------|
| 20250729 | v1.0 | 新建 |
|  |  |  |

# **1\. 需求背景**

快麦erp需要增加财务模块，单点登录对接有成财务可最快速度补齐这块能力。

# **2\. 业务流程/架构**

单点登录流程

用户在快麦中点击财务模块入口，快麦拼接有成财务单点登录网址\+后台绑定的手机号\+appkey\+入口标记参数source=kmerp，跳转到有成财务；

有成财务前后端通信解析参数，完成用户登录进系统的过程。易企财

# **3\. 功能清单**

| 模块 | 功能点 | 备注 |
|------|---------|------|
| 单点登录 | 单点登录 |  |
|  |  |  |
|  |  |  |

# **4\. 需求详情**

本期仅处理pc

有成财务解析单点登录跳转地址，并按如下逻辑处理：
1. ~~若未传appkey仅传了手机号，~~
    1. ~~没有匹配到已开通企业：您尚未加入企业或企业未开通产品，请联系管理员（正常来说不会有这个情况，兜底一下）~~

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/3BMqYybp1Ev3KqwZ/img/253cd7f7-7602-44f2-b355-bd4d6e1517ed.png?Expires=1774155997&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=qBKnOCYc2RCDl7bETceXBCjfx0o%3D "")
    2. ~~匹配到一个已开通企业：直接进入产品内~~
    3. ~~匹配到多个已开通企业：选择企业中间页~~

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/3BMqYybp1Ev3KqwZ/img/1a588238-11a8-4570-af20-92b2a2d9675d.png?Expires=1774155997&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=hA4hyNVLdmDeX0R9RXqQD%2FLGnl4%3D "")
2. 若appkey和手机号都传了：——快麦本期按照这种模式对接。
    4. 若企业未开通：（正常来说不会有这个情况，兜底一下）企业尚未开通产品，请联系管理员
    5. 若企业已开通，但手机号不在组织架构中：您尚未加入企业，请联系管理员
    6. ~~若企业已开通，但手机号在组织架构中且未激活：您的手机号尚未激活，请联系管理员~~

source参数用于记录流量，方便后续统计。

---

> 📌 **相关链接**
> - [[有成财务报销知识库索引]]
