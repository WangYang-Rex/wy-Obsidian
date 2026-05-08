---
title: "开票申请+电票YJ"
tags:
  - 有成报销
  - PRD
  - 需求设计-项目与合同-�
created: 2026-03-24
source: 钉钉文档
original_url: https://alidocs.dingtalk.com/i/nodes/QG53mjyd80Rjq0QOCdpn1k2kV6zbX04v?utm_scene=team_space
node_id: QG53mjyd80Rjq0QOCdpn1k2kV6zbX04v
exported_at: 2026-03-22
---

# 开票申请+电票YJ

> 🔗 **原文链接**：[开票申请+电票YJ - 钉钉文档](https://alidocs.dingtalk.com/i/nodes/QG53mjyd80Rjq0QOCdpn1k2kV6zbX04v?utm_scene=team_space)

# 开票申请\+电票YJ

| **修订时间** | **版本** | **修订说明** | **作者** |
|----------------|----------|----------------|----------|
| 20240329 | v1.0 | 新建 | 昭觉 |

## 1、涉及系统

有成报销 PC

## 2、需求背景

## 3、业务流程/架构

如复杂需求，放置相关流程/架构图

## 4、功能清单

根据个人需要补充

## 5、需求详情

### 5.1、需求说明

#### 新建申请单


![Picture 1](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eYVOL5jZg4WN4lpz/img/3ff933d8-891e-4eb6-9f20-85b7e07f6130.png?Expires=1774157544&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=zwCjC0m2xcNpTXWx47vKR0SYDTg%3D "")


![Picture 2](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eYVOL5jZg4WN4lpz/img/36574b02-6e52-4fda-8e3f-bff04d2aec43.png?Expires=1774157544&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=Ip0p%2BEznvhz%2BUnwzQCA%2Fh7Rx0x8%3D "")

##### 填写说明：

| **字段名称** | **字段说明** | **备注** |
|----------------|----------------|----------|
| 开票类型 | 下拉单选，选项值为：普票、专票无默认值 | 1、 必填2、 一张单据中支持多个发票类型、多个开票方和多个购买方3、当申请单同步给电票系统时，按照每一条数据拆分 |
| 购方信息 | 下拉单选，数据源为【往来单位】无默认值按照可见范围展示 |  |
| 开票方信息 | 下拉单选，数据源为【发票抬头】无默认值 |  |
| 商品名称 | 下拉单选，数据源为【商品管理】无默认值 |  |
| 税编简称 | 根据商品名称带出，不可编辑切换商品时随之切换 | 必填 |
| 税收分类编码 |  |  |
| 规格型号 | 根据商品名称带出，可编辑切换商品时随之切换 | 非必填 |
| 单位 |  |  |
| 单价（含税） |  |  |
| 数量 | 手动输入 | 非必填 |
| 税率 | 根据商品名称带出，不可编辑切换商品时随之切换 | 必填 |
| 含税金额 | 手动输入1、当填写了单价、数量时，自定计算，含税金额=单价\*数量，保留小数点后 2 位2、当填写了含税金额和单价或者数量时，自动计算另一个值 | 必填 |
| 税额 | 根据税率和含税金额自动计算计算公式=含税金额/（1\+税率） |  |
| 开票状态 | 新建和编辑单据时不可操作审批完成后单据详情页可操作 |  |
| 关联单号 | 点击，弹窗展示单据列表1、 仅展示收款单和应收合同，审批中是否允许被关联根据单据模板的配置2、单据仅支持单选3、选中后，子表单中仅展示单据号4、关联的单据即使包含了商品、开票方信息等会相关数据，此处也不做带入处理【统一做数据联动】对于合同来说，可用金额，默认等于合同金额，关联了开票申请后，可用金额=合同金额-开票金额对于收款单，如果没有开票场景组件，则可用金额默认等于收款单的收款金额，关联了开票申请后，可用金额=收款金额-开票金额如果收款单有收款场景组件，则可用金额=未开票金额，关联了开票申请后，可用金额=未开票金额-开票金额 | 非必填开票成功后发票回传，需要根据开票申请和单据的关联关系，核销发票 |
| 备注 | 文本字段 | 非必填 |

![Picture 3](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eYVOL5jZg4WN4lpz/img/dd4ed423-5432-4bb3-812f-9d408300e1c3.png?Expires=1774157544&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=iS9Q3lmpXn78%2BMRhoYgiPKSqa4Q%3D "")

##### 开票申请组件支持导入


![Picture 4](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eYVOL5jZg4WN4lpz/img/4958677e-2ee1-4062-8af8-e64806051cd8.png?Expires=1774157544&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=cVenhXJ4OcjsMr%2Bm2G79GpVcRBc%3D "")

开票申请导入模板.xlsx (附件: attachments/开票申请导入模板\_20250701\_144621.xlsx)

###### 导入时：

1、逐条判断必填信息，报错后提示

2、导入后开票方信息和系统中的发票抬头进行匹配，匹配失败则报错：当前税号的发票抬头不存在

3、导入后购买方信息和系统中的往来单位进行匹配，匹配失败则报错：当前购买方信息不存在

4、导入后商品信息和系统中的商品管理进行匹配，匹配失败则报错：当前商品不存在

5、导入后税编、税率根据商品名称带出，不允许编辑

6、导入后规格型号、单位支持编辑

7、单价、金额、税额、折扣金额导入时不支持公式计算

8、导入的关联单据号在系统中不存在或者非收款单与应收合同，则报错：单号不存在或者不符合要求

9、导入的关联单号，需要判断单据的可用金额与该行商品的开票金额，如果单据的可用金额小于开票金额，则报错：\{单据号\}可用金额小于开票金额

9、对表格中的每一条数据无需做重复性判断：

即允许同一个发票类型、开票方、购买方、商品一致

###### 导入失败：

1、导入失败时支持下载导入失败文件【去应用中心下载】，导入失败的数据在最后新增一列错误原因

2、支持导入失败的数据重新导入，过滤掉失败原因

#### 提交单据

1、 子表单必填项校验

2、开票申请组件的含税金额汇总 必须等于 申请单的申请金额

#### 单据详情页

审批中：


![Picture 5](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eYVOL5jZg4WN4lpz/img/cc0c23c7-d015-4935-8ccc-37c599b2faab.png?Expires=1774157544&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=kkmVbuN7CCc1LpL4HLWBqLzHy2g%3D "")

审批完成后：


![Picture 6](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eYVOL5jZg4WN4lpz/img/6fdc7256-3d20-4752-bbb3-036e8e2d2764.png?Expires=1774157544&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=qOmCdOlbPCWKIKEdPRX%2FbZRi6fw%3D "")

##### 发票来源：

###### 手动上传

1、支持手动上传发票【逻辑同合同发票上传】，不支持从电票系统获取

对于手动上传的发票需要校验发票开票方信息和购买方信息是否和开票申请明细的数据匹配

如果不匹配，则提示：购买方信息/销售方信息不一致，请重新选择发票后上传
- 单次发票上传时：


![Picture 7](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eYVOL5jZg4WN4lpz/img/1cfcb970-b9c2-4bea-86d6-2f42e4dc2dc9.png?Expires=1774157544&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=MgnGjHNzNnRio9HnvwMe%2FN4Kmmo%3D "")
- 合并开票上传时：


![Picture 8](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eYVOL5jZg4WN4lpz/img/7266f37e-cc9d-47eb-89b6-0996bef5062e.png?Expires=1774157544&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=lyAuGEHk5Epoe4gwmU%2FQ6QI4wS0%3D "")

###### 三方系统回传


![Picture 9](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eYVOL5jZg4WN4lpz/img/c68037b6-a145-471b-a346-5ff29c5b4cf7.png?Expires=1774157544&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=yC29Lu5TuNIfALU6ULOR0Ua0mD4%3D "")
- 三方系统回传的发票，更新在开票申请明细中，开票状态更新为【已开：XX】--展示样式同【 合同发票】
- 审批流增加一条发票上传记录


![Picture 10](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eYVOL5jZg4WN4lpz/img/4ca4bbed-e42a-4783-83e5-18887a7a3c04.png?Expires=1774157544&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=p80izgHy9fm85Zuz9qYOScedq6c%3D "")
- 点击【已开】，展示同步和手动上传的发票：


![Picture 11](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eYVOL5jZg4WN4lpz/img/ea2f9f2e-e702-4074-adf4-b3690a96d0f0.png?Expires=1774157544&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=c4lEnjgqdyMq%2Fe%2FwndWMDKKnSfA%3D "")

当发票冲红、作废后，展示逻辑同【合同发票】现有逻辑

##### 发票和关联单据的匹配关系

当发票回传后，按照开票申请中关联的单据建立关联关系

###### 对于收款单

在审批历史新增一条发票记录


![Picture 12](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eYVOL5jZg4WN4lpz/img/4ca4bbed-e42a-4783-83e5-18887a7a3c04.png?Expires=1774157544&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=p80izgHy9fm85Zuz9qYOScedq6c%3D "")

更新收款单列表的已开票金额、待开发票金额

更新待开发票的已开票金额、待开发票金额

如果该收款单关联了应收合同，则发票需要回传到对应收款合同的计划中

###### 对于应收合同

发票回传后，根据对应关系，展示的合同计划中

按照从上往下的方式核销开票金额【逻辑同合并开票】


![Picture 13](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eYVOL5jZg4WN4lpz/img/ee22b9b8-f147-43d1-8d8d-e993f92e7ec9.png?Expires=1774157544&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=KzsIS8dkpM4YavgISRlFkJB7FK0%3D "")

查看已开发票逻辑同现有

合同管理列表已开票金额、未开票金额更新

财务管理--应收应付管理列表已开票金额、未开票金额更新

#### 发票管理&我的发票

回传的发票归属根据申请单的申请人归属

#### 附件管理

开票系统同步的发票需要归类到附件管理，且展示数据源为【有成电票】

#### 报表

1、项目报表--合同应收款--单据列表：已开票金额&未开票金额更新

2、自定义报表明细表--数据源为单据时，已开票金额&未开票金额更新

3、自定义报表--明细表--数据源为子表单时，支持开票申请子表单统计

#### 单据列表搜索

1、全局搜索 不支持开票申请子表单的搜索

2、快捷筛选不支持开票申请子表单的搜索

#### 单据列表导出

导出子表单时，支持开票申请数据的导出

#### 打印

新老版打印支持开票申请组件的打印

#### 凭证日记账

本期不做处理

#### 系统日志


![Picture 14](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eYVOL5jZg4WN4lpz/img/fd389307-2314-49f1-aaec-c12d9cdfede4.png?Expires=1774157544&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=h5F7Rbos61%2BsXIepzYUz02qvQX0%3D "")

增加对接有成电票的系统日志

#### 电票系统

##### 同步节点

开票申请单审批完成后，由报销系统推送到电票系统

开票申请单推送到电票系统后，未开票时，申请单在报销系统中被删除，则同步删除有成电票系统中对应的单据

如果已经部分开票或者全部开票，则不允许删除

##### 发票类型匹配

有成电票系统内，根据可开票种，默认匹配到第一个发票类型

专票--增值税专用发票、增值税电子专用发票、全电发票（专用发票）中匹配第一个

普票--增值税普通发票、增值税电子普通发票、全电发票（普通发票）中匹配第一个

##### 发票回传

开票后将开具的发票回传到报销系统，并跟对应的单据关联

##### 发票状态更新

发票被冲红、作废后，需要更新报销系统中对应的发票状态

##### 销方匹配

根据开票申请中开票方信息和电票系统维护的企业信息按照税号匹配

##### 购买方处理

按照明细传给电票系统，报销侧不做合并处理
