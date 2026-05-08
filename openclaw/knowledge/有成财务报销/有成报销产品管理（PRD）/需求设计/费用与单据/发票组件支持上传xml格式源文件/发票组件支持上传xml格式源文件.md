---
title: "发票组件支持上传xml格式源文件"
tags:
  - 有成报销
  - PRD
  - 需求设计-费用与单据-�
created: 2026-03-24
source: 钉钉文档
original_url: https://alidocs.dingtalk.com/i/nodes/gwva2dxOW4KpAvQ3tdqZMMjN8bkz3BRL?utm_scene=team_space
node_id: gwva2dxOW4KpAvQ3tdqZMMjN8bkz3BRL
exported_at: 2026-03-22
---

# 发票组件支持上传xml格式源文件

> 🔗 **原文链接**：[发票组件支持上传xml格式源文件 - 钉钉文档](https://alidocs.dingtalk.com/i/nodes/gwva2dxOW4KpAvQ3tdqZMMjN8bkz3BRL?utm_scene=team_space)

# 发票组件支持上传xml格式源文件

| **修订时间** | **版本** | **修订说明** | **作者** |
|----------------|----------|----------------|----------|
| 20240307 | v1.0 | 新建 | 昭觉 |

## 1、涉及系统

有成报销 PC & MB

## 2、需求背景

随着数电票的普及，档案存档要求存储发票 xml 格式的文件，因此报销系统中需要支持 xml 格式的源文件上传，针对票种：电子发票（普通发票）、电子发票（增值税专用发票）

电子发票查验方式包括验签、扫二维码、国家税务总局查验平台和第三方软件。

## 3、业务流程/架构

## 4、功能清单

根据个人需要补充

| **模块** | **功能点** | **备注** |
|----------|-------------|----------|
| 新建单据&新增费用 | 1、发票组件、发票核销组件、合同发票组件支持上传 xml 格式文件2、支持 xml 格式文件的验真、查重、开票日期等发票的相关校验 |  |
| 电票系统提供板式文件获取接口 | 提供给电子档案系统 |  |

## 5、需求详情

### 5.1、需求说明

#### 发票上传时支持 xml 格式【PC&MB】

1、 新增和编辑 费用&单据 时，发票组件、合同发票组件、发票核销组件支持 xml 格式文件

2、发票上传后，发票展示：


![Picture 1](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/54Lq35oy9NPQXl7E/img/6839d99c-1fb3-4837-8471-5401e4ba24b8.png?Expires=1774157409&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=dkWBBgGYB8uvuNZPdZmHUgAovSc%3D "")

3、查看单据详情


![Picture 2](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/54Lq35oy9NPQXl7E/img/1d63630b-a49b-409d-81f9-9a94e0a368b3.png?Expires=1774157409&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=Q7rGcCi5a4Qu5JWr2Y5x3O5pbdY%3D "")

4、 查看发票详情：同系统现有逻辑，图片展示 xml 文件标识


![Picture 3](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/54Lq35oy9NPQXl7E/img/9d4a1733-e6ed-4c57-b48d-9910f632184a.png?Expires=1774157409&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=qhjJ9aGWXxklu10ReB4SIhOdSec%3D "")

点击图片，跳转到 xml 文件在线预览页面：


![Picture 4](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/54Lq35oy9NPQXl7E/img/2671634b-a068-41ee-9a78-963e319ee8c0.png?Expires=1774157409&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=a%2FnAGI6z3KvxMZdk2iCfs9WkWVQ%3D "")

附件管理逻辑相同，浏览器打开 xml 文件预览。

#### 发票识别

1、 根据 xml 文件解析发票信息，无需进行 ocr 识别，根据解析出来的发票类型、发票号码、发票日期、价税合计做验真

#### 发票比对

1、发票验真失败，则不展示验真标记，发票明细填充 xml 文件中的数据；发票生成费用时费用金额、税率税额等从 xml 文件中填充；

2、发票验真成功， 根据发票查验后接口返回的数据，与 xml 文件内的数据进行比对，如果上传的 xml 文件数据与税局不一致，则提示：发票文件不是原文件，请重新上传。如果上传的 xml 文件数据与税局完全一致，则不提示。

附件1：《电子凭证会计数据标准——全面数字化的电子发票（试行版）》指南.docx (附件: attachments/附件1：《电子凭证会计数据标准——全面数字化的电子发票（试行版）》指南\_20250701\_144412.docx)

关于验签：

[<u>https://zhuanlan.zhihu.com/p/388299815</u>](https://zhuanlan.zhihu.com/p/388299815)


![Picture 5](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/54Lq35oy9NPQXl7E/img/8156d2de-9797-40f3-8ae0-09c32995bc36.png?Expires=1774157409&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=WOv3VHaBTYQI%2FfhR4drGwA5Q9Ps%3D "")

#### 发票校验

1、 发票验真、查重、发票抬头、银行地址、串号、连号、地区、金额、税率、上传时间的校验同现有的发票逻辑，跟随全局设置中的配置

2、发票格式转换：xml 格式的文件不参与格式转换功能

#### 智能签收

1、 如果上传的文件为 xml，纸质单据里提交了 pdf 或者图片的样式，则智能签收逻辑按照当前逻辑；如果打印的是 xml 的打印文件，则不参与比对

2、智能签收的发票影像为 xml

#### 邮箱获取发票：

1、邮箱获取发票时需要支持 xml 格式的文件

#### 发票计算

1、 对于发票金额、税率税额同步，逻辑同现有发票的带入逻辑，跟随开关配置

2、发票拆分逻辑同现有

#### 发票导出&下载

##### 导出

我的发票&发票管理列表：逻辑保持不变

##### 下载

我的发票&发票管理&附件管理列表：如果上传的发票为 xml 格式，则下载后依然为 xml 格式的文件

#### 发票列表：

包含我的发票、发票管理

列表展示逻辑不变，查看发票详情时，图片展示为 xml 标记，点击图片，打开 xml 文件预览


![Picture 6](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/54Lq35oy9NPQXl7E/img/2e67466d-61b9-445c-b536-3103a6eead65.png?Expires=1774157409&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=ERF8ZUjCRBZFkknw0eJ2Y%2B4Ib1o%3D "")

#### 附件管理：

列表展示内容不变，点击查看附件详情时，打开 xml 源文件。

#### 打印


![Picture 7](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/54Lq35oy9NPQXl7E/img/37a02ceb-44f9-43e9-ad65-92f2cfa76fbd.png?Expires=1774157409&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=SrS85m7kzsV%2FLJYULN%2BVLwebZIA%3D "")

当勾选了电子发票打印时，不支持 xml 文件的打印。

#### 电票系统获取版式文件接口

进项发票提供获取全电票版式文件的接口
