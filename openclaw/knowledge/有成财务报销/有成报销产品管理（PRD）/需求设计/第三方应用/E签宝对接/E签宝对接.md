---
title: "E签宝对接"
nodeId: dQPGYqjpJYg0lZOdIdE4GBxmWakx1Z5N
workspaceId: R2PmK2gngjVnZXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/dQPGYqjpJYg0lZOdIdE4GBxmWakx1Z5N?utm_scene=team_space"
exportedAt: 2026-04-01T02:14:35.670Z
source: dingtalk-document-mcp
---
# E签宝对接

| **修订时间** | **版本** | **编写人** | **修订说明** |
|----------------|----------|-------------|----------------|
| 20230419 | v1.0 | 小乔 | 新建 |

## 1、需求背景

1、e签宝：在完成企业/用户认证的基础上，支持对文件发起线上签署，签署进度可跟踪，并支持合同下载归档

2、我们现在合同签署只能线下进行，无法线上发起签署，并跟踪签署情况，对接E签宝完善线上签署流程

## 2、业务流程/架构

接口文档：[<u>https://www.yuque.com/esign/potnnf/ggggqh#3xchN</u>](https://www.yuque.com/esign/potnnf/ggggqh#3xchN)

对接e签宝，合同线上签署流程：

1）用户在应用中心授权开通、并完成实名认证

2）开通后，联系客户充值购买合同签署份数

3）用户在e签宝后台进行印章管理/人员权限管理

4）合同审批通过后，发起合同线上签署流程

5）跟踪合同签署进度/用章审批情况

6）签署完成，下载归档



![Picture 1](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/KM7qeobgWW5ZPlpj/img/82be6057-4458-412d-91b1-011679281074.png?Expires=1775016876&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=Bz7zGeIggY0t1CtB9PDlO3cz3RI%3D "")

## 3、功能清单

根据个人需要补充

| **模块** | **功能点** | **备注** |
|----------|-------------|----------|
| 应用中心 | 开放“e签宝”开通入口 |  |
| 后台管理 | 支持为企业充值e签宝套餐 |  |
| 合同发起线上签署 | 针对开启了“线上签署”的合同，审核通过后，支持发起线上签署 |  |
| 合同列表 | 合同列表增加签署状态 |  |

## 4、需求详情

### 4.1、系统【有成报销】钉钉版-PC

### 4.2、应用中心

#### 应用中心开放“e签宝”开通入口



![Picture 2](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/KM7qeobgWW5ZPlpj/img/eebfd102-6086-43e6-9045-1f0f206c2f0d.png?Expires=1775016876&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=tBIjExBAHFPXWDgzLNNECMYZyws%3D "")

##### slogan

合法可靠的电子合同电子签名服务

##### 开通流程

点击“开通”，需完成以下步骤

###### 安装e签宝微应用



![Picture 3](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/KM7qeobgWW5ZPlpj/img/acf5df5a-5048-4168-9a98-9f6ff9dfc40e.png?Expires=1775016876&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=g6IeddppgbyDtU8w3xgKib6xe4o%3D "")

1. 页面文案：电子合同服务由e签宝提供，开通服务前请确保已安装e签宝微应用；使用手机钉钉扫码，安装e签宝微应用2. 安装二维码：\后续由e签宝提供安装渠道码\</span\>3. 调用API\<span style="color:#2F8EF4"\>【\</span\>\[获取企业e签宝微应用状态\](https://www.yuque.com/esign/potnnf/ggggqh#8grI5)\<span style="color:#2F8EF4"\>】\</span\>，查询e签宝安装状态1. \*\*未安装\*\*——点击“已扫码安装e签宝”提示：企业还未安装e签宝微应用！



![Picture 4](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/KM7qeobgWW5ZPlpj/img/eb6c6df4-67fb-4841-b721-ba9559a03d9d.png?Expires=1775016876&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=fbZlShcze4UIwamII2dZuCG8jYc%3D "")

2. \*\*已安装\*\*——点击“已扫码安装e签宝”跳到下一步骤

###### 企业授权



![Picture 5](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/KM7qeobgWW5ZPlpj/img/14e93add-5f2d-4196-b0d7-59c0176564d3.png?Expires=1775016876&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=A4UqQ2x3eSDXRpyPrPOW2j5tzbE%3D "")

4. 页面文案：电子合同服务由e签宝提供，使用该功能需将文件授权给e签宝进行电子签章5. 点击“前往e签宝授权”，跳转e签宝授权页——API【\[获取授权的页面地址\](https://www.yuque.com/esign/potnnf/ggggqh#8kPUW)】，同时有成报销页面弹出授权确认弹窗：\*\*此次操作将跳转e签宝页面，是否已完成授权？\*\*



![Picture 6](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/KM7qeobgWW5ZPlpj/img/928b4847-9231-410e-a3e4-22269b5cfa4d.png?Expires=1775016876&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=RpZ88Knr1xI4aUayIdqU%2B3OrUR8%3D "")

6. 查询e签宝授权状态——API【\[获取企业e签宝微应用状态\](https://www.yuque.com/esign/potnnf/ggggqh#8grI5)】1. \*\*未授权\*\*——点击“完成授权”时提示：企业还未完成授权！



![Picture 7](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/KM7qeobgWW5ZPlpj/img/e2287582-2634-4926-aedf-4287d4b5d9d6.png?Expires=1775016876&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=2GQcKp7NYfS5e7kQvuBuQJTMLfQ%3D "")

2. \*\*已授权\*\*——点击“完成授权”时跳到下一步骤

###### 企业实名认证



![Picture 8](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/KM7qeobgWW5ZPlpj/img/b627511a-c8db-4f52-bd3e-bd45cd94f28b.png?Expires=1775016876&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=Ciqs6%2F1gVmFgkDi0sM9QJ2LeoQQ%3D "")

1. 页面文案：电子合同服务由e签宝提供，完成实名认证后才可使用电子签章2. 点击“前往e签宝进行实名认证”，跳转e签宝企业实名认证页面——API【\[获取跳转到企业实名的地址\](https://www.yuque.com/esign/potnnf/ggggqh#PTaZB)】，同时有成报销页面弹出实名认证确认弹窗：此次操作将跳转e签宝页面，是否已完成实名认证？



![Picture 9](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/KM7qeobgWW5ZPlpj/img/aa22f8be-683d-4bdf-b345-7f4f17f457cc.png?Expires=1775016876&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=t3%2FfDEAFnJbcPOGY9xFeKq6HoeI%3D "")

3. 查询企业在e签宝中实名认证状态——API【\[查询企业信息\](https://www.yuque.com/esign/potnnf/ggggqh#QGx2r)】1. \*\*未实名\*\*——点击“完成实名认证”提示：企业还未完成实名认证！



![Picture 10](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/KM7qeobgWW5ZPlpj/img/c735492e-991a-469b-a2ab-e7b8a3d3dd6f.png?Expires=1775016876&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=yaGcDDxCuG6S%2FWsV5yUfSzhEG4k%3D "")

2. \*\*已实名\*\*——点击“完成实名认证”隐藏弹窗，完成开通流程

##### 开通后



![Picture 11](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/KM7qeobgWW5ZPlpj/img/59a7b773-1583-4b91-b1d2-686ca1eaa288.png?Expires=1775016876&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=uHpvF%2B8vYLQWsu5bptIfP4AXvqY%3D "")

1\. \*\*状态：使用中\*\*2\. \*\*剩余可签署合同数\*\*：调用API\<span style="color:#2F8EF4"\>【\</span\>\[查询套餐余量\](https://www.yuque.com/esign/potnnf/ggggqh#Brt0N)\<span style="color:#2F8EF4"\>】\</span\>3\. \*\*联系客服充值\*\*：点击弹出客服电话



![Picture 12](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/KM7qeobgWW5ZPlpj/img/7e756a29-7342-49f3-a350-4e2c88abdeb7.png?Expires=1775016876&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=cM1WddqPDhCPCPmOV2iuP6zPUxs%3D "")

4\. \*\*合同设置\*\*：点击跳转合同设置页面；支持对系统中已维护的所有合同单据进行“是否开启线上签署”的设置（\*\*默认开关为关闭状态\*\*）；\*\*若合同表单模板中未添加“附件”组件，开启线上签署开关时给出弹窗提示\*\*1. 提示文案：该合同表单模板中未添加「附件」组件，无法开启线上签署2. 点击去添加：点击跳转到该合同表单编辑页面



![Picture 13](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/KM7qeobgWW5ZPlpj/img/972d66a1-4663-4dfc-a14c-bab81becb1c8.png?Expires=1775016876&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=4b97JZHxxFsvWyiSnGKl%2B1p852E%3D "")

5\. \*\*管理后台\*\*：点击弹出是否跳转至e签宝后台确认框，点击“确认”跳转至e签宝后台1. API【\[获取企业控制台地址\](https://www.yuque.com/esign/potnnf/ggggqh#0Q2Du)】  2. 确认框文案：e签宝后台可进行企业印章管理、人员权限管理等。是否跳转至e签宝？



![Picture 14](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/KM7qeobgWW5ZPlpj/img/55a4c7a2-0f78-43d4-8f1f-9da65c9806e7.png?Expires=1775016876&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=PO3L1r82rE1qDfnFky0weOqPOaE%3D "")

6\. \*\*解除绑定\*\*：点击弹出是否跳转至e签宝页面确认框，点击“确认”跳转至e签宝解除授权页面1. API【\[取消企业授权\](https://www.yuque.com/esign/potnnf/ggggqh#020839a2)】2. 确认框文案：此操作需前往e签宝页面进行，是否继续？



![Picture 15](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/KM7qeobgWW5ZPlpj/img/2369bf2b-18e3-403c-998f-c123b6dacb12.png?Expires=1775016876&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=KVcF0LezzkvQQywaCoDFQdX5Uho%3D "")

##### 流程图



![Picture 16](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/KM7qeobgWW5ZPlpj/img/198f309d-865b-49cc-8252-b776cbba2235.png?Expires=1775016876&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=UtwZrIeSK2GCBe31eSEvbVgth1c%3D "")

### 4.3、后台管理

**开通e签宝服务后，用户联系客服充值，客服在后台管理-企业管理中，找到企业，完成e签宝合同数充值**
1. 企业管理中-编辑类型选型增加「e签宝充值」
2. 编辑页面显示“用户剩余合同数”-不可编辑；充值合同数填写范围：正整数
3. 点击“确定”，调用API【[<span style="color: #0000FF;"><u>套餐转售2（底价结算模式）</u>](https://www.yuque.com/esign/potnnf/ggggqh#6v0Nz)】，传入本次给该企业下单多少份电子合同，e签宝将会充值合同份数到用户账号上
4. 合同底价后续由双方商务对接确定

### 4.4、合同发起线上签署

**合同发起线上签署前提：**

**1）该合同类型开启了“线上签署”；2）合同审批通过；3）合同单据中上传了附件**

**合同线上签署位置：**

**1）单据详情页，增加“签署详情”tab**

**2）签署详情内容包括：**

| **内容模块** | **具体内容** | **备注** |
|----------------|----------------|----------|
| 基本信息 | 发起人、签署状态 |  |
| 电子合同 | 已下载的电子合同 | 该内容模块仅在合同签署状态为“已完成”时展示 |
| 签署方 | 签署人、签署状态、用章流程 |  |
| 签署流程 | 签署人操作记录 |  |

**注：只有开启了“线上签署”&审批通过的合同类单据才展示该tab页**

#### 场景一：有成报销侧合同未发起线上签署

有成侧合同审批通过后，未发起线上签署，进入合同单据详情-签署详情页



![Picture 17](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/KM7qeobgWW5ZPlpj/img/1cfd1000-68af-4284-8d7b-0f216d6d3882.png?Expires=1775016876&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=N%2BdscX2juSCQoym9EwtYO6lAP9s%3D "")

1\. \*\*发起签署\*\*：点击按钮校验当前合同单据中是否上传附件1. \*\*未上传附件\*\*：点击按钮弹出弹出提示：合同单据中未上传附件，无法发起线上签署2. \*\*已上传附件\*\*：点击按钮跳转e签宝签署发起页面，补充签署方信息。2\. 页面缺省提示：暂未发起线上签署

#### 场景二：有成报销侧合同已发起线上签署

在有成报销侧发起签署后，e签宝中合同签署任务状态包括：

0-草稿 1-签署中 2-完成 3-撤销 4-终止 5-过期 6-删除 7-拒签

##### 合同任务签署：草稿（e签宝侧未发起）

草稿状态：有成侧点击了“发起签署”，跳转到e签宝后，未提交发起



![Picture 18](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/KM7qeobgWW5ZPlpj/img/1c5baa6a-1d68-4e26-9bc0-7707afa17460.png?Expires=1775016876&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=YOehg5XiFlmE%2FGgk2zhOh3fdaRI%3D "")

1. 查看签署：点击跳转e签宝签署发起页面（同上）2. 签署详情内容：调用API【\[获取对应流程任务详情\](https://www.yuque.com/esign/potnnf/ggggqh#3xchN)】查询“基本信息”信息。参数对应如下：

| **有成报销字段** | **e签宝参数** | **取值范围** |
|----------------------|-----------------|----------------|
| 发起人 | initiatorName（发起人姓名） |  |
| 签署状态 | flowStatus（流程状态） | 0-草稿,1-签署中,2-完成,3-撤销,4-终止（由于某些异常情况，无法完成签署),5-过期（签署截至日志到期后触发),7-拒签 |

3. 缺省文案\+ 签署方：暂无签署方信息\+ 签署流程：暂未发起签署

##### 合同任务签署：签署中



![Picture 19](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/KM7qeobgWW5ZPlpj/img/fd9d6950-6744-4292-9fe7-9685c78c3662.png?Expires=1775016876&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=czVmeeEAD%2Fdcwp3SySgIBgIj884%3D "")

4. 签署详情内容：调用API【\[获取对应流程任务详情\](https://www.yuque.com/esign/potnnf/ggggqh#3xchN)】查询“基本信息”、“签署流程”；调用API【\[获取流程签署详细信息\](https://www.yuque.com/esign/potnnf/ggggqh#P1Duj)】“签署方”信息。字段取值如下：

| **签署方-头像** | **（钉钉组织内）钉钉头像/（外部）统一头像** |  |
|--------------------|--------------------------------------------------------------|---|
| 签署方-姓名 | signerName（签署人姓名） |  |
| 签署流程-操作时间 | operateTime（操作时间戳） |  |
| 签署流程-操作人 | operatorAccountName（操作人姓名） |  |
| 签署流程-操作人操作 | logType |  |

5. 查看用章流程：当\签署方为组织架构内\</span\> & \<span style="color:#DF2A3F"\>在e签宝侧发起了用章审批流程 \</span\>，点击“查看用章审批”调用API【\[获取流程任务用印审批列表\](https://www.yuque.com/esign/potnnf/ggggqh#06e340c7)】可查看该签署方的用章审批流程详情

<span style="color: #DF2A3F;">注：审批流程中-审批节点只展示审批完成的节点（状态：审批通过/审批拒绝）

| **审批发起人姓名** | **sponsorAccountName（审批发起人姓名）** |  |
|-------------------------|-------------------------------------------------|---|
| 审批发起时间 | startTime（审批开始时间戳） |  |
| 审批人姓名 | approverName（审批人姓名） |  |
| 审批状态 | status | 只取审批状态为：AGREED 审批通过 /REFUSED 审批拒绝  的节点信息展示 |
| 审批时间 | approvalTime（节点审批时间） | 取该节点最近一次的审批时间 |

##### 合同任务签署：完成

签署完成后，支持下载电子合同；同时签署详情页展示“电子合同”模块

1. \*\*未下载电子合同\*\*

合同完成签署后，显示“下载电子合同”按钮，签署详情页增加“电子合同”模块

未下载电子合同时，显示缺省图，提示：暂未下载电子合同

![Picture 20](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/KM7qeobgWW5ZPlpj/img/016772eb-d4b2-4e65-b9be-27f966d9b48f.png?Expires=1775016876&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=QxwgwTArzVQ4w%2Bmgxd5KtzsrXSw%3D "")

2. \*\*已下载电子合同\*\*

完成合同下载后，已下载合同显示在“电子合同”下方

支持点击查看

![Picture 21](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/KM7qeobgWW5ZPlpj/img/fe5e9ac0-4dfd-42be-8f46-7089cb4af767.png?Expires=1775016876&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=3NfdXv2nH07iFOA15jBt%2B1bnlCM%3D "")

##### 合同任务签署：撤销/终止/过期/拒签

当合同签署任务状态为：撤销/终止/过期/拒签时，支持重新发起签署，点击“重新发起签署”相当于重新创建一个签署任务。签署详情页内容更新为新签署任务内容。



![Picture 22](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/KM7qeobgWW5ZPlpj/img/af40e550-846a-4944-9b9d-75805a743fd7.png?Expires=1775016876&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=dNu1CSP3IGJd%2FnB5oz%2FSh2kMaWI%3D "")

##### 流程图



![Picture 23](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/KM7qeobgWW5ZPlpj/img/96162b68-2c7e-498b-831a-f9558e13d066.png?Expires=1775016876&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=mxomL5x4bdpd7HFt2JYTwg9tDvE%3D "")

### 4.5、合同列表

「我的-单据」「项目与合同-合同管理」，列表中增加“签署状态”字段

字段取值包括：“空”/草稿/签署中/完成/撤销/终止/过期/拒签

#### 我的-单据

我的-单据-全部，单据列表增加字段“签署状态”。当单据取不到签署状态时，显示为空；签署状态取e签宝签署任务状态



![Picture 24](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/KM7qeobgWW5ZPlpj/img/bd4ce793-7aad-4a7d-85e6-c3398ae8403e.png?Expires=1775016876&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=YSoc8BoPKbYrtTlxvPWZPedwGd0%3D "")

#### 项目与合同-合同管理

合同管理-应付合同/应收合同/通用合同，单据列表增加字段“签署状态”。当单据取不到签署状态时，显示为空；签署状态取e签宝签署任务状态

![Picture 25](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/KM7qeobgWW5ZPlpj/img/6e5de00a-e8ef-4d12-97ab-bc519282599e.png?Expires=1775016876&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=et8%2FhIT2FXl6iteH7s%2FTs1Ctzr0%3D "")
