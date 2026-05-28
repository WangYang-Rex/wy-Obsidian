---
title: "上架WPS"
nodeId: YndMj49yWjPvNlg2I0GPde1ZJ3pmz5aA
workspaceId: R2PmK2Q8rxRbeXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/YndMj49yWjPvNlg2I0GPde1ZJ3pmz5aA?utm_scene=team_space"
exportedAt: 2026-03-31T04:29:56.060Z
source: dingtalk-document-mcp
---
# 上架WPS

| **修订时间** | **版本** | **修订说明** |
|----------------|----------|----------------|
| 2023-12-4 | v1.0 | 新建 |
|  |  |  |

## 1、需求背景

上架WPS，获取更多流量，从而提升业绩

开发文档：[<u>https://open-xz.wps.cn/pages/server/file/upload-auth/</u>](https://open-xz.wps.cn/pages/server/file/upload-auth/)

平台规范：[<u>https://kdocs.cn/l/cbqQtjrkUdo4</u>](https://kdocs.cn/l/cbqQtjrkUdo4)

## 2、功能清单

| **序号** | **模块** | **备注** |
|----------|----------|----------|
| 1 | WPS订单对接（对接中台） |  |
| 2 | WPS组织架构对接（对接中台） |  |
| 3 | WPS消息推送对接（对接中台） |  |
| 4 | 其他功能调整 |  |
| 5 | 钉钉、企业微信二维码替换为WPS二维码 |  |
| 6 | 运营后台企业列表、订单列表调整 |  |
| 7 | 其他 |  |

## 3、需求详情

### 3.1 WPS订单对接（对接中台）

售卖流程，参考企业微信对接有成中台：[<u>https://gykj.yuque.com/vhho51/bvmmvu/nsq2nu/edit#gurKZ</u>](https://gykj.yuque.com/vhho51/bvmmvu/nsq2nu/edit#gurKZ)

### 3.2 WPS组织架构对接（对接中台）
1. 对接有成中台
2. 支持自定义组织架构

### 3.3 WPS消息推送对接（对接中台）
3. MB端消息处理：和现有一致
4. PC端消息处理：

（1）审批消息：支持PC端打开PC应用

（2）业务对象消息和其他系统消息：本期可以仅显示二维码，提示在移动端打开

### 3.3 其他功能调整

| **模块** | **功能** | **飞书端处理办法** |
|----------|----------|-------------------------|
| 企业微信相关 | 企业微信绑定自建应用 | 不支持 |
|  | 企业微信通讯录组件 | 不支持 |
| 钉钉相关 | 钉钉PaaS（原钉钉高级CRM与本系统对接部分功能） | 不支持 |
|  | 钉钉连接器 | 不支持 |
|  | 智能办公电话 | 1\. PC端应用开关不展示此开关2\. WPS用户可以直接在MB线索、客户、联系人列表打电话 |
| 第三方对接 | 对接有成财务 | 1\. 不支持2\. PC端应用开关不展示3\. PC端左侧菜单不展示 |
|  | 对接有成报销 | 1\. 不支持2\. PC端应用开关不展示 |
|  | e签宝 | 1\. 不支持2\. PC端应用开关不展示 |
| 运营后台 | 模拟用户打开 | 支持 |
|  | 钉钉待办 | 不支持 |
|  | 消息推送 | 不支持 |
|  | 卡片消息查询 | 不支持 |
|  | Actioncard | 不支持 |
| 其他应用内调整 | PC端应用开关-更多应用 | 不展示此Tab |
|  | PC端顶部导航“续费升级”按钮 | 不展示此按钮 |
|  | 去掉“钉钉”、“企业微信”相关文案 | 1\. PC端-设置-部门员工-“同步钉钉员工”文案改为“同步员工”2\. 角色未授权时，进入CRM的提示页面3\. 前端整理有“钉钉”文案的页面（如有遗漏，前端可继续补充）https://gykj.yuque.com/docs/share/0d88661d-ba29-4ac3-9dd2-b3e4193af0c8?# |
|  | 钉钉、企业微信二维码替换为WPS二维码 | 参考后面的原型图 |
|  | MB端顶部按钮调整 | 和企业微信保持一致即可 |
|  | 前端使用钉钉、企业微信JS-API | 参考之前的文档，前端可以补充到最后一列“WPS支持情况”：[<u>https://gykj.yuque.com/docs/share/52bc04f3-3af6-4d3e-acf5-31884dfce0a4?#</u>](https://gykj.yuque.com/docs/share/52bc04f3-3af6-4d3e-acf5-31884dfce0a4?#) |

### 3.4 以下几处二维码替换为WPS二维码/去掉联系电话---待wps提供



![Picture 1](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eYVOL5jZdvMQRlpz/img/a1bd4a00-ced0-430e-b6ce-d8888c8afc23.png?Expires=1774938597&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=oDeX644MiMUOFiaGcdwNesKellg%3D "")



![Picture 2](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eYVOL5jZdvMQRlpz/img/e7025067-e0da-4659-a869-7428c94b5d8a.png?Expires=1774938597&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=e2Uts3Lm8CAaGef6XSDa8NN0TUc%3D "")



![Picture 3](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eYVOL5jZdvMQRlpz/img/f01a89bf-09a4-4391-a854-97946bd809e1.png?Expires=1774938597&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=J5gGcwkJLZQYg3uvtLTeVpWyKUM%3D "")



![Picture 4](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eYVOL5jZdvMQRlpz/img/cb3a709c-1933-4b7e-b580-7878e35c4633.png?Expires=1774938597&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=UWBhqEiV8hsh4%2Fqqz%2Bbgc5AXdkI%3D "")

### 3.5 运营后台企业列表、订单列表调整
5. 运营后台-企业报表、运营后台-订单管理，新增字段“开通平台”。展示开通平台：飞书、钉钉、企业微信、羚羊、WPS
6. 运营后台-企业报表、运营后台-订单管理新增筛选字段“开通平台”。可筛选：全部、钉钉、企业微信、羚羊、WPS



![Picture 5](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eYVOL5jZdvMQRlpz/img/73181e6e-07c3-45ff-8fcc-d3cd77e49abd.png?Expires=1774938597&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=wqxT%2FZ%2BTDQotbbmsO70dphjDY%2Fk%3D "")

### 3.6 其他需要改造的点

为满足wps平台规范，需要按照下文，进行安装授权、活跃监控接入

[<u>https://kdocs.cn/l/cbqQtjrkUdo4</u>](https://kdocs.cn/l/cbqQtjrkUdo4)

### 3.7 企业到期提醒：区分新平台



![Picture 6](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eYVOL5jZdvMQRlpz/img/def8fd6f-3637-40d8-b2d8-2860a8f59720.png?Expires=1774938597&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=71KXRTV5CNxb5yMpnPf3rWA8rcE%3D "")
