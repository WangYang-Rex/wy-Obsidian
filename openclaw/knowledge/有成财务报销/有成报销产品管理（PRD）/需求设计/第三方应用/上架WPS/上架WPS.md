---
title: "上架WPS"
tags:
  - 有成报销
  - PRD
  - 需求设计-第三方应用-�
created: 2026-03-24
source: 钉钉文档
original_url: https://alidocs.dingtalk.com/i/nodes/KGZLxjv9VG3RrkNQT79AraN2V6EDybno?utm_scene=team_space
node_id: KGZLxjv9VG3RrkNQT79AraN2V6EDybno
exported_at: 2026-03-22
---

# 上架WPS

> 🔗 **原文链接**：[上架WPS - 钉钉文档](https://alidocs.dingtalk.com/i/nodes/KGZLxjv9VG3RrkNQT79AraN2V6EDybno?utm_scene=team_space)

# 上架WPS

| **修订时间** | **版本** | **修订说明** |
|----------------|----------|----------------|
| 2025-01-02 | v1.0 | 新建 |

## 1、需求背景

上架WPS，获取更多流量，从而提升业绩

开发文档：[<u>https://open-xz.wps.cn/pages/server/file/upload-auth/</u>](https://open-xz.wps.cn/pages/server/file/upload-auth/)

平台规范：[<u>https://kdocs.cn/l/cokEEw9rdf3S</u>](https://kdocs.cn/l/cokEEw9rdf3S)

测试后，将这个文档填写好，需要提交给WPS验收，验收文档：[<u>https://365.kdocs.cn/l/cvCcGJftyiEG</u>](https://365.kdocs.cn/l/cvCcGJftyiEG)

## 2、功能清单

| **序号** | **模块** | **备注** |
|----------|----------|----------|
| 1 | WPS订单对接（对接中台） |  |
| 2 | WPS组织架构对接（对接中台） |  |
| 3 | WPS消息推送对接（对接中台） |  |
| 4 | 接入上传文件、摄像头接口 |  |
| 5 | 其他功能调整：应用中心隐藏、客服联系方式更换为二维码 |  |
| 6 | 接入创建桌面快捷方式 |  |
| 7 | 其他：活跃监控接入 |  |

## 3、需求详情

### 3.1 WPS订单对接

1、开通下单购买流程，参考企业微信、钉钉等对接有成中台

2、有成财务管理后台：支持查询到WPS的订单和客户信息
- 企业管理-企业查询-订单来源字段增加：WPS
- 订单管理-订单列表-订单来源字段增加：WPS


![Picture 1](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4maOgXbMZdogvlWN/img/3e730c8c-b900-4a79-b62b-796fa8c25a07.png?Expires=1774156469&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=b%2F%2BW78mwOJIA4FSL%2F5IxAPYvV64%3D "")


![Picture 2](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4maOgXbMZdogvlWN/img/acf7c091-4bed-4b8b-b2c2-b57a2c625a20.png?Expires=1774156469&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=AJdhOFmp6XM2pNZOHzIoF8ov2Kk%3D "")

### 3.2 WPS组织架构对接

[<u>https://open-xz.wps.cn/pages/server/contacts/depts/get-depts-info/</u>](https://open-xz.wps.cn/pages/server/contacts/depts/get-depts-info/)
1. 将组织架构对接同步到有成报销中；组织架构同钉钉，不支持新增删除

### 3.3 WPS消息推送对接

[<u>https://open-xz.wps.cn/pages/server/msg-and-group/sendmsgV2/</u>](https://open-xz.wps.cn/pages/server/msg-and-group/sendmsgV2/)
2. 待办消息推送：
3. 待办消息推送给指定的用户：
4. 日期相关的消息提醒：
5. 日期组件中设定的提醒；
6. 发票-催票提醒
7. 合同管理-应收应付：逾期提醒计划付款、计划收款提醒
8. 其他系统提醒：到期提醒、导出失败消息（待确认）

### 3.4 发票、图片、附件组件接入拍照、选取文件接口
9. 摄像头拍照或相册选照片：[<u>https://open-xz.wps.cn/pages/client/web-apps/JSAPI/video/#1195d36b</u>](https://open-xz.wps.cn/pages/client/web-apps/JSAPI/video/#1195d36b)
10. 选文件：[<u>https://open-xz.wps.cn/pages/client/web-apps/JSAPI/file/</u>](https://open-xz.wps.cn/pages/client/web-apps/JSAPI/file/)

### 3.5 应用内改造点：应用中心卡片隐藏

| **模块** | **功能** | **飞书端处理办法** |
|----------|----------|-------------------------|
| 应用中心 | 日常管理-钉钉考勤 | 1\. 不支持2\. PC端、MB端应用中心隐藏这个模块 |
|  | 系统互联-报销财务一体化 | 1\. 不支持2\. PC端、MB端应用中心隐藏这个模块 |

### 3.6 应用内改造点：客服联系方式二维码替换：

二维码待WPS提供


![Picture 3](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4maOgXbMZdogvlWN/img/836a1e73-8733-40a3-9c7a-c0555f4406a9.png?Expires=1774156469&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=HuXaIhPczFQIKXBM3kbBi%2FrbIzw%3D "")

**一、首页**


![Picture 4](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4maOgXbMZdogvlWN/img/d31cf3a4-1c1f-4105-8db6-bdb7f11fe4c3.png?Expires=1774156469&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=3XpVdNIkBojl6qFI%2FKQVgaw1pqg%3D "")

**二、应用中心需要联系客服的地方，点击弹窗需要打开二维码扫码的弹框：**


![Picture 5](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4maOgXbMZdogvlWN/img/e6e79ea2-617e-4875-9ec6-4d5366828211.png?Expires=1774156469&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=dvWpkflQevjPLXWacWWuKzYtbwY%3D "")

三、手机端：点击联系客服给二维码弹框，右侧的图为示例


![Picture 6](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4maOgXbMZdogvlWN/img/1d97bf0f-39ab-4687-8cf1-ab657cde3b23.png?Expires=1774156469&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=ezfixJGKJOt%2F502tdWp4jB9L%2Bjw%3D "")

![Picture 7](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4maOgXbMZdogvlWN/img/e52de44b-84b6-4aa0-bf0b-d4c4a0c3daae.png?Expires=1774156469&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=A%2ByJ%2B1Hcw8qa9scLwCrmvVb%2FHEc%3D "")

### 3.7 WPS进入应用显示创建桌面快捷方式入口、

[<u>https://365.kdocs.cn/l/cooGvDqdEkVB?openfrom=docs</u>](https://365.kdocs.cn/l/cooGvDqdEkVB?openfrom=docs)


![Picture 8](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4maOgXbMZdogvlWN/img/a81ca828-ac68-4592-b7ad-c7860a5cd395.png?Expires=1774156469&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=iZqwUsGEuwbUIQI4xbppn82zU%2BQ%3D "")

1、首次进入应用，关闭应用时，给二次弹框提示，询问是否创建桌面快捷方式，点击确认即关闭应用同时调用创建快捷方式接口，创建桌面快捷方式

2、WPS入口进入应用，应用中心左侧增加入口：创建桌面快捷方式，UI参照应用中心，不用放ICON，点击后调用WPS创建桌面快捷方式能力，创建成功则直接提示创建桌面快捷方式成功；

再次进入应用，当前用户已经创建了桌面快捷方式的（看能否识别到？），不再展示这个入口。


![Picture 9](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4maOgXbMZdogvlWN/img/277c5f1e-4216-4723-ad2d-a2327af62058.png?Expires=1774156469&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=tL8Bf2UbCn9qE0imbqWXtlia66k%3D "")


![Picture 10](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4maOgXbMZdogvlWN/img/aa04e0a3-31a6-4ddc-acc1-f0157b03c3e1.png?Expires=1774156469&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=KFooeHt7l3MNRAvxMFhtV2wMBJo%3D "")

### 3.8 其他需要改造的点

1、为满足wps平台规范，需要按照下文，进行安装授权、活跃监控接入

[<u>https://www.kdocs.cn/l/cokEEw9rdf3S</u>](https://www.kdocs.cn/l/cokEEw9rdf3S)


![Picture 11](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4maOgXbMZdogvlWN/img/bb95a2fd-688b-43ef-a0f2-0f08e51ff0e1.png?Expires=1774156469&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=xYH9%2BrPrFwCzEiYR0w1g3S2R310%3D "")

2、WPS企业到期提醒：应用内、消息通知
