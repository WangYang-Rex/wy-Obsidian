---
title: "有成CRM对接钉钉酷应用"
nodeId: oP0MALyR8k79kzMNhE75rq1b83bzYmDO
workspaceId: R2PmK2Q8rxRbeXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/oP0MALyR8k79kzMNhE75rq1b83bzYmDO?utm_scene=team_space"
exportedAt: 2026-03-31T04:32:10.688Z
source: dingtalk-document-mcp
---
# 有成CRM对接钉钉酷应用

## 1、业务背景
1. 对接钉钉酷应用，用户可在钉钉群内直接开通有成CRM。给有成CRM带来更多流量
2. 本次钉钉酷应用，将区分内部群、外部群。内部群、外部群将会接入不同的功能。本期设计的主要功能，是基于内部群为前提场景。少部分功能是之后内部群、外部群通用的（3.6智能表单链接分享）
3. 钉钉会先给我们开放内部群，外部群也可能会开放
4. 酷应用文档：[<u>https://open.dingtalk.com/document/isv/cool-application-introduction-isv</u>](https://open.dingtalk.com/document/isv/cool-application-introduction-isv)服务端API：[<u>https://open.dingtalk.com/document/isvapp-server/api-operations-for-group-applications-1</u>](https://open.dingtalk.com/document/isvapp-server/api-operations-for-group-applications-1)客户端API：[<u>https://open.dingtalk.com/document/isvapp-client/install-cool-applications-and-add-them-to-the-group</u>](https://open.dingtalk.com/document/isvapp-client/install-cool-applications-and-add-them-to-the-group)

## 2、业务流程图

## 3、需求说明

### 3.1、酷应用开通

| **模块** | **说明** |
|----------|----------|
| 开通酷应用 | 1\. 开通方式：用户在钉钉群内，点击“更多”开通酷应用。开通流程参考下方2\. 开通酷应用的同时，该企业也会同时开通试用有成CRM应用 |
| 开通后-群内 | 1\. 开通后，群内新增群机器人。群机器人名称：有成CRM小助手（头像，后续提供）2\. 开通消息：开通后，在群内推送2个开通消息。   （1）消息一、告知谁开启了应用（钉钉要求）：   点击“查看详情”进入应用详情页   点击“管理群应用”进入群应用管理页面   （2）消息二、告知用户核心能力和使用方法：   点击“快速上手”可跳转钉钉内置浏览器进入帮助页面（帮助页面链接，后续提供）3\. 群捷径新增：业绩PK榜、我的客户4\. 开通应用后，展示群吊顶钉钉卡片配置效果： |
| 开通后-工作台 | 1\. 展示有成CRM的图标 |

![Picture 1](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/J9LnW6jzY290VlvD/img/f334be42-d662-438b-8cc5-35581307fd40.png?Expires=1774938732&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=V%2F0l3Ko%2BrvjKIj0kPy94GtXiUr8%3D "")

![Picture 2](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/J9LnW6jzY290VlvD/img/b3cce805-7d5d-45e3-b7c5-d8ccce3b6816.png?Expires=1774938732&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=TzenYYNEyq9XXgg5nbasu1ZcLAM%3D "")

![Picture 3](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/J9LnW6jzY290VlvD/img/f60c9ea6-c3d6-440f-9d8c-cf7acc9d84ca.png?Expires=1774938732&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=V0vwY5daRvi7joqt4MkP50zAN1Y%3D "")

### 3.2、业绩PK榜推送

| **模块** | **说明** |
|----------|----------|
| 推送机制 | 每日早上9点钟推送业绩PK榜到群中钉钉卡片配置效果： |
| 取数逻辑 | 1\. 业绩PK榜内容为每月的业绩数据排名（取目标PK榜的合同订单数据，时间为当月）2\. 默认为全公司的数据 |
| 点击“查看详情” | 点击“查看详情”，打开MB“目标PK榜”页面，查看详细的排名数据。参考上方原型图 |
| 点击“点赞” | 卡片支持点赞互动：（这个钉钉暂不支持，本期忽略点赞功能）   （1）当前用户未点赞：显示“未点赞”图标   （2）当前用户已点赞：显示“已点赞”图标，并且点赞数\+1 |

![Picture 4](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/J9LnW6jzY290VlvD/img/6990dfde-bcd8-41e0-b618-5e454c7fe24a.png?Expires=1774938732&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=90wpewwEhFWx4F%2FCKXST%2FV4v6wc%3D "")

![Picture 5](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/J9LnW6jzY290VlvD/img/1034870f-fa7f-4b08-952e-58d024a47e15.png?Expires=1774938732&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=jdRbyXIebr4Z9POxacAwWGhQq2g%3D "")

![Picture 6](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/J9LnW6jzY290VlvD/img/8f657951-b30a-4d90-937f-781ffd23fa3a.png?Expires=1774938732&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=73LFiecJVg7%2BEBPbPdxn60rXIb0%3D "")

### 3.3、成交推送

| **模块** | **说明** |
|----------|----------|
| 推送机制 | 1\. 群成员在有成CRM录入合同订单后，推送成交消息到群内（改为架构下的所有人员新建合同并审核通过后，都推送）2\. ~~非群成员，录入合同订单则不推送到该群~~~~背景：如公司有多个销售团队，往往会有不同的销售群。A团队的成交消息就通知到A团队的群，不同通知到B团队的群~~~~需要后端确认钉钉查询群成员的能力~~[<u>@曹书源</u>](undefined/caoshuyuan-g74ed)钉钉卡片配置效果： |
| 点击“查看详情” | 1\. 展示合同详情页。参考上方原型图2\. 如无权限，则提示无权限查看 |
| 点赞 | 卡片支持点赞交互：（和业绩PK榜一致）（这个钉钉暂不支持，本期忽略点赞功能）（1）当前用户未点赞：显示“未点赞”图标   （2）当前用户已点赞：显示“已点赞”图标，并且点赞数\+1 |

![Picture 7](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/J9LnW6jzY290VlvD/img/7fde4317-b4ef-4d9a-b935-687adc7f902e.png?Expires=1774938732&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=7nRLVpuEinH%2BInmFzn77WTgtGLg%3D "")

![Picture 8](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/J9LnW6jzY290VlvD/img/5847704c-6719-4a0a-92f0-c1c876a67ee2.png?Expires=1774938732&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=rJB4KkWDUBWNrVujjC4MJiXQXxg%3D "")

### 3.4、群捷径

| **模块** | **说明** |
|----------|----------|
| 捷径一：业绩PK榜单 | 点击打开“目标PK榜详情页” |
| 捷径二：我的客户 | 点击打开“客户列表”页面 |

![Picture 9](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/J9LnW6jzY290VlvD/img/74432f50-60b5-4afc-bd31-0e966ab0bec7.png?Expires=1774938732&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=r0u%2FEC1UjRb7PFGvEdWlc5uFr4A%3D "")

![Picture 10](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/J9LnW6jzY290VlvD/img/1f366c54-8ad2-496d-ad9f-8843728b4309.png?Expires=1774938732&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=hTjmPPjZWiW8YVBe45l4RFmpLgY%3D "")

备注：
5. 这里涉及到很多页面，前端确认下移动端页面支持PC端打开这块的工作量[<u>@王洋</u>](undefined/u29255)
6. 钉钉是否提供“返回”（如没有，也可以忽略）[<u>@王洋</u>](undefined/u29255)



### 3.5、群吊顶

| **模块** | **说明** |
|----------|----------|
| 目标完成度 | 1\. 吊顶展示目标完成进度2\. 展示当前用户的个人目标、部门目标。不同人展示的数据不同。如用户有多个部门，则展示部门目标合计（和首页逻辑一致）3\. 如未必设置目标，则显示“未设置目标”4\. 支持用户右上角点击“刷新”，更新卡片内的数据钉钉卡片配置效果： |

![Picture 11](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/J9LnW6jzY290VlvD/img/b2d9f817-c07b-42e1-bdca-052729434280.png?Expires=1774938732&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=WEpj4XEH4gFgqNLrjSpiJtGffXQ%3D "")

![Picture 12](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/J9LnW6jzY290VlvD/img/2ae9a8a3-cafc-40d5-af88-9d3890197342.png?Expires=1774938732&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=kpokelqH4LYyOAs4AK88qv%2FC1fg%3D "")

### 3.6、智能表单链接分享

场景：在一些市场活动中，销售可以将表单分享到客户对接群中，高效收集客户的信息
7. 有成CRM-智能表单-分享页面，新增一个“分享链接”入口，点击可快捷将链接分享到钉钉聊天内
8. 分享到钉钉聊天内后，可以转化为交互卡片
9. 发起人视角：展示“分享”按钮，点击分享可继续将链接分享给他人；点击卡片，进入表单填写页面
10. 接收人视角：展示“立即填写”、“分享”按钮。点击“立即填写”，进入表单填写页面，可填写表单
11. 接收人视角（已填写）：展示“再次填写”、“分享”按钮



![Picture 13](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/J9LnW6jzY290VlvD/img/80c00c43-2ba8-4afc-a620-f3bdcc6d2262.png?Expires=1774938732&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=XZvb45C755PQYKiKkwZf%2FnfqaKk%3D "")

### 3.7、消息菜单支持工单（仅MB端）

| **模块** | **说明** |
|----------|----------|
| 消息菜单，新增“新建工单” | 1\. 钉钉消息-快捷操作支持新建工单2\. 如当前用户无工单权限，则提示tosat提示：无此权限3\. 目前钉钉仅支持移动端，PC端暂不支持 |
| 字段带入规则 | 1\. 消息内容，自动带入工单标题字段2\. 不带入图片、附件3\. 字数如超过250字，则工单标题仅展示前250字 |

![Picture 14](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/J9LnW6jzY290VlvD/img/d687feb9-8438-4ddc-b1e3-d9de1366678d.png?Expires=1774938732&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=mdE8UVKB7Q2tvRbtr9qKcVfX7lg%3D "")

### 3.8、应用过期

如果有成CRM到期，则进行以下处理：
12. 停止业绩PK榜推送
13. 停止成交推送
14. 关闭不展示群吊顶卡片
15. 从群捷径“业绩PK榜”、“我的客户”、消息菜单“新建工单”、群内历史消息卡片，进入有成CRM，则提示应用已到期
