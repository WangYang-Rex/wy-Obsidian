---
title: "招商CBS升级到CBS8"
tags:
  - 有成报销
  - PRD
  - 需求设计-第三方应用-�
created: 2026-03-24
source: 钉钉文档
original_url: https://alidocs.dingtalk.com/i/nodes/N7dx2rn0JbZ9KxGot5vAgRQ3JMGjLRb3?utm_scene=team_space
node_id: N7dx2rn0JbZ9KxGot5vAgRQ3JMGjLRb3
exported_at: 2026-03-22
---

# 招商CBS升级到CBS8

> 🔗 **原文链接**：[招商CBS升级到CBS8 - 钉钉文档](https://alidocs.dingtalk.com/i/nodes/N7dx2rn0JbZ9KxGot5vAgRQ3JMGjLRb3?utm_scene=team_space)

# 招商CBS升级到CBS8

| **修订时间** | **版本** | **修订说明** |
|----------------|----------|----------------|
| 20241017 | v1.0 | 新建 |

## 1、需求背景

客户：拓烯科技（衢州）

客户使用的是CBS8版本，有成报销对接的版本需要兼容CBS8；

CBS8分为前置机和openapi两种形式，

接口文档：

CBS8业务接口文档-账户管理-20240722.docx (附件: attachments/CBS8业务接口文档-账户管理-20240722\_20250701\_142252.docx)

CBS8业务接口文档-支付管理-20240911.docx (附件: attachments/CBS8业务接口文档-支付管理-20240911\_20250701\_142252.docx)

openapi对接技术指南.docx (附件: attachments/openapi对接技术指南\_20250701\_142253.docx)

CBS7已对接的接口：
- 代发经办
- ERP对接模块支付请求(ERPAYSAV)
- 电子回单查询ERP(ERDRCQRY)
- 批量查询支付状态
- 查询历史交易数据

## 2、需求详情

#### 一、后台管理系统-CBS开通

增加CBS的版本选项：CBS7、CBS8，无默认值，必须勾选：
- 版本默认为CBS7，可配置项为现在的配置不变
- 版本切换为CBS8时，配置项：显示秘钥、平台公钥、企业公钥、企业私钥的配置项，都为必填

---信息为客户开通时，招行线下提供


![Picture 1](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/YdgOk2b1jZQrKq4B/img/fb36146e-3fb6-4be5-97b5-743709ff8ccc.png?Expires=1774156400&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=F6cf3eVN3y5vr0hPpcNZ30ng1B4%3D "")

#### 二、流程中的接口对接

**1、发起支付\+支付状态查询**


![Picture 2](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/YdgOk2b1jZQrKq4B/img/01d3f0f1-0824-49e3-9e6f-6f1e20849a3d.png?Expires=1774156400&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=1JKzUWfaM1tKeOM7XwAB2sxTlaI%3D "")


![Picture 3](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/YdgOk2b1jZQrKq4B/img/7927a2da-e808-4635-8988-534035f7a4b4.png?Expires=1774156400&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=Kfhw8IKocmIz4CqUTFqj38LGxwc%3D "")

1、出纳支付节点，点击支付时，选中的支付账号已授权开通招商CBS，则在支付的时候，可以勾选CBS支付：
- 勾选上之后，若当前企业授权的是CBS8，调用招商CBS8的【批量代发】接口，发起支付将参数传给招商银行，调用成功后单据状态为“支付中”；
- 5分钟调用一次【支付/代发/代扣列表查询】接口，查询支付申请单的支付状态：处理逻辑参照CBS7~~支付成功则单据状态更新为支付成功~~~~支付失败，则单据状态为待支付，可重新发起支付，但记录接口返回的错误原因~~

**2、电子回单获取**

调用【电子回单查询】接口，拿到电子回单，跟单据关联起来，会展示出来的地方有：
- 单据-审批历史
- 财务管理-资金明细：已经关联上的在列表“回单”列展示点击“获取历史回单”，可重新调用回单接口查询回单
- 应用中心-招商CBS-支付明细管理：将获取的支付金额字段同样填在支付明细列表中可查询到


![Picture 4](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/YdgOk2b1jZQrKq4B/img/5132e829-c4b5-4799-94a1-c8dd39c0f776.png?Expires=1774156400&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=9YNEB4VVpw9LZL2o%2FGGgVFs2QvY%3D "")


![Picture 5](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/YdgOk2b1jZQrKq4B/img/a01a9ce4-f803-4711-8316-c43fecb7bbbf.png?Expires=1774156400&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=FIP%2BwqMPVbXdwpkLj396LTStOgg%3D "")

**附：接口对照表：**

**一、【批量代发】**

业务接口文档-支付管理-20240911-3.1.9批量代发

| **入参** | **有成对应字段** | **备注** |
|----------|----------------------|----------|
| referenceNum | 唯一ID | 后续用于支付状态 |
| recordNum | 批量记录序号 |  |
| busType | 传203   --代发 |  |
| amount | 支付金额 |  |
| currency | 默认本位币币种 |  |
| payAccount | 付款账号 |  |
| purpose | 应用中心-招商CBS-管理设置中的用途设置 |  |
| **AttachmentInfoBO-明细** |  |  |
| dtlAmount | 收款账户关联的金额 |  |
| dtlRevAccount | 收款账号 |  |

**二、【支付状态查询】**

业务接口文档-支付管理-20240911-3.1.3 支付/代发/代扣列表查询

| **入参** | **有成对应字段** | **备注** |
|----------|----------------------|----------|
| referenceNum | 唯一ID |  |
| queryDateStart | 开始日期 |  |
| queryDateEnd | 结束日期 |  |

| **出参** | **有成对应字段** | **有成处理逻辑** |
|----------|----------------------|----------------------|
| status | 支付申请状态 | 以下枚举值处理归为支付失败：3-支付失败5-审批撤销6-审批拒绝9-审批退回11-预处理拒绝 |
| payStatus | 支付状态 | 以下枚举值处理归为支付失败：h-支付失败j-退票k-取消支付 |

**三、【电子回单查询】**

业务接口文档-账户管理-20240722-1.1.5 电子回单查询

| **入参** | **有成对应字段** | **备注** |
|----------|----------------------|----------|
| queryDateStart | 开始日期 |  |
| queryDateEnd | 结束日期 |  |
| settleBusinessReferenceCode | ERP业务参考号 | 此字段为支付接口的referenceNum（业务参考号） |

| **出参** | **有成对应字段** | **备注** |
|----------|----------------------|----------|
| bucketFileUrl | 回单文件下载地址 | 下载回单之后，与单据关联起来：1、单据审批历史中可见2、资金明细中可见3、应用中心-招商CBS-支付明细管理 |
