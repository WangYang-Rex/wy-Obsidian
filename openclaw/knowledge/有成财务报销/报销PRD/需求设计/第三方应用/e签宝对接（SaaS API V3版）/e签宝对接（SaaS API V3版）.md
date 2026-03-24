---
title: "e签宝对接（SaaS API V3版）"
tags:
  - 有成报销
  - PRD
  - 需求设计-第三方应用-e
created: 2026-03-24
source: 钉钉文档
original_url: https://alidocs.dingtalk.com/i/nodes/N7dx2rn0JbZ9KxGot5vAK9Z3JMGjLRb3?utm_scene=team_space
node_id: N7dx2rn0JbZ9KxGot5vAK9Z3JMGjLRb3
exported_at: 2026-03-22
---

# e签宝对接（SaaS API V3版）

> 🔗 **原文链接**：[e签宝对接（SaaS API V3版） - 钉钉文档](https://alidocs.dingtalk.com/i/nodes/N7dx2rn0JbZ9KxGot5vAK9Z3JMGjLRb3?utm_scene=team_space)

# e签宝对接（SaaS API V3版）

| **修订时间** | **版本** | **编写人** | **修订说明** |
|----------------|----------|-------------|----------------|
| 20231115 | v1.0 | 小乔 | 新建 |

## 1、需求背景

**背景：**

我们现在合同签署只能线下进行，无法线上发起签署，并跟踪签署情况，对接E签宝完善线上签署流程

前期先实现上传本地合同文件发起签署；后期考虑对接合同模板，支持创建模板，并通过模板制作合同发起签署

**满足场景：**

合同完成审批后，针对合同文件（单据-“附件”组件中上传的附件）发起签署，支持查看签署详情、撤销签署（未完结前）、支持下载已签署合同

## 2、业务流程/架构

接口文档：[<span style="color: #0000FF;"><u>https://open.esign.cn/doc/opendoc/apiv3-guide/tfb6gn</u></span>](https://open.esign.cn/doc/opendoc/apiv3-guide/tfb6gn)

**对接e签宝，合同线上签署流程如下：**

1、企业开通e签宝服务，联系客服充值合同份数

2、企业用户在e签宝后台进行印章管理/人员权限管理

3、拟定合同 发起审批，合同审批通过后，发起合同线上签署流程（签署完结前支持撤销签署）

4、通知签署方进行合同签署（短信通知）

4、跟踪合同签署进度

5、签署完成，下载归档

**合同签署流程图：**



![Picture 1](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/2M9qP5jzyE0oDO01/img/8cf484ec-643d-431d-978b-eced28242b81.png?Expires=1774156467&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=ZFWkOUFITTXzuvYiHZKshlPNT%2Bs%3D "")

## 3、涉及系统

**有成报销 （易企报 & 钉钉 & 飞书 & 企微）**



## 4、功能清单

根据个人需要补充

| **模块** | **功能点** | **备注** |
|----------|-------------|----------|
| 应用中心 | 新增“e签宝”应用 |  |
| 管理后台 | 支持开通&充值e签宝 |  |
| 合同单据 | 支持发起线上签署 |  |
| 合同列表 | 增加“签署状态”字段 |  |

## 5、需求详情

### 5.1、应用中心-新增“e签宝”应用

##### 管理后台-消息推送-配置管理 ：新增“e签宝”应用

平台：全平台（易企报 & 钉钉 & 飞书 & 企微）

应用分类：系统互联

应用名称：e签宝

应用ID：ESignTreasure

##### 应用中心：展示“e签宝”应用



![Picture 2](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/2M9qP5jzyE0oDO01/img/86af71ee-5823-4fad-a0fc-bf66b9bbb468.png?Expires=1774156467&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=D3tlB2heoShrzP6qWEuo2NXEiqk%3D "")

###### 开通

默认为未开通状态；

开通应用：由客服在管理后台为企业用户开通；开通后，应用名称旁展示“使用中”标签

###### 剩余可签署合同数

根据后台充值的数量以及使用的合同数计算

**剩余可签署合同数**=充值数量-合同签署数量（<span style="color: #DF2A3F;">签署状态为：签署中、已完成的合同数</span>）

<span style="color: #DF2A3F;">需向e签宝确认：合同签署数量的定义？？？已经发起的，但被拒签/过期/撤销的 算不算份数？？？</span>

###### 联系客服充值

点击弹出客服电话

###### 合同设置



![Picture 3](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/2M9qP5jzyE0oDO01/img/177b5abb-aaab-4632-87f0-66341853d65f.png?Expires=1774156467&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=JfJg9v%2ByyREgG%2FFR79JIFcFd1D8%3D "")
- 点击“合同设置”跳转如上页面，该页面支持对系统中**所有合同单据**进行“是否开启线上签署”设置
- 线上签署开关默认为“**关闭**”状态；
- 开启开关的同时，校验该合同单据表单中**是否存在“附件”组件**；存在：开启成功；不存在：弹窗提示“**该合同表单模板中未添加「附件」组件，无法开启线上签署**”，并支持跳转表单编辑页面

###### 管理后台
- 点击“管理后台”，弹窗提示“**e签宝后台可进行企业印章管理、人员权限管理等     是否跳转至e签宝后台？**”，点击“确定”，跳转“e签宝”企业控制台（免登录）
- 企业控制台服务API：[<span style="color: #0000FF;"><u>https://open.esign.cn/doc/opendoc/console/rhoap2</u></span>](https://open.esign.cn/doc/opendoc/console/rhoap2)

###### 整体流程图



![Picture 4](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/2M9qP5jzyE0oDO01/img/6ad0961e-db9d-4238-b6e0-accbf021ad7c.png?Expires=1774156467&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=2442foeIdGz8sp2Ns1Sx7dWvX3A%3D "")

### 5.2、管理后台-支持为企业开通并充值“e签宝”合同份数



![Picture 5](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/2M9qP5jzyE0oDO01/img/29e7a036-510f-4d6e-a3c6-91eb2882b171.png?Expires=1774156467&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=4Zlit7BeGAq%2FLR0uBeNfUjabACw%3D "")
1. 企业管理中-编辑类型选型增加「**e签宝开通与充值**」
2. 开通状态开关默认“**关闭**”；只有为开启状态时才可进行充值（才展示“剩余合同数”与 充值框）
3. “用户剩余合同数”-不可编辑；充值合同数填写范围：正整数

### 5.3、合同线上签署

<span style="color: #DF2A3F;">1）合同签署状态说明：</span>
- **草稿**：初始状态，上传合同文件发起签署，未调用「[<span style="color: #0000FF;"><u>开启签署流程</u></span>](https://open.esign.cn/doc/opendoc/pdf-sign3/pu4xsx)」开启签署流程，此时为“草稿”状态
- **签署中**：发起签署，调用以上接口开启签署流程后，状态变为“签署中”
- **已拒签**：当流程中的任一签署方拒绝签署文件后，状态变为“已拒签”
- **已过期**：“签署中”的流程，如果超过了流程设置的截止时间，流程将自动变更为“已过期”状态
- **已撤销**：“签署中”的流程，调用【撤销签署流程】接口成功后触发，流程将变更为“已撤销”状态
- **已完成**：所有人签署完成，调用「[<span style="color: #0000FF;"><u>完结签署流程</u></span>](https://open.esign.cn/doc/opendoc/pdf-sign3/ynwqsm)」完结流程，状态变为“已完成”

<span style="color: #DF2A3F;">2）合同不同状态对应的操作：</span>

| **合同审批状态** | **合同签署状态** | **支持的操作** |
|----------------------|----------------------|-------------------|
| 通过 | 草稿 | 发起签署 |
|  | 签署中 | 撤销签署 |
|  | 已拒签 | 重新发起签署 |
|  | 已过期 | 重新发起签署 |
|  | 已撤销 | 重新发起签署 |
|  | 已完成 | 下载已签署电子合同 |
| 不通过 | -- | -- |

##### 发起签署

###### 按钮展示及发起签署判断逻辑：



![Picture 6](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/2M9qP5jzyE0oDO01/img/5e00ccc2-34fb-45a8-aff2-0f0e3df450e9.png?Expires=1774156467&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=MjxbDANIK29tXQT5SwEoOSf5y8w%3D "")

###### 页面交互



![Picture 7](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/2M9qP5jzyE0oDO01/img/70632733-fcff-4d22-865e-6045dcfada20.png?Expires=1774156467&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=FcVhznJ7JIsGHpb079%2BT0of5%2FTg%3D "")

1、在满足“**合同审批通过**”&“**该合同开启了线上签**”条件下，合同详情页 展示“**发起线上签署**”按钮、“**签署详情**”tab页

2、点击“发起线上签署”，校验“剩余可签署合同数”、“单据是否上传附件”
- **剩余可签署合同数=0**  点击“发起线上签署”，提示：**当前可签署合同数为0，请联系客服充值！客服电话：13175030373**
- **单据中未上传附件**  点击“发起线上签署”，提示：**合同单据中未上传附件，无法发起线上签署**

3、**“剩余可签署合同数\>0”&“单据中已上传附件”**，点击“发起线上签署”，弹出进度提示弹窗。发起线上签署分两步：
- 生成待签署文件：调用「[<span style="color: #0000FF;"><u>上传本地文件</u></span>](https://open.esign.cn/doc/opendoc/pdf-sign3/rlh256)」，将合同中附件上传至e签宝服务端，生成待签署的PDF文件
- 发起签署：文件上传完成后，调用「[<span style="color: #0000FF;"><u>通过页面发起签署</u></span>](https://open.esign.cn/doc/opendoc/pdf-sign3/lp54bn)」，跳转e签宝合同发起签署页面，进行内容填写及签署提交

4、发起签署成功后，调用「[<span style="color: #0000FF;"><u>开启签署流程</u></span>](https://open.esign.cn/doc/opendoc/pdf-sign3/pu4xsx)」，签署状态变为“**签署中**”

5、当签署状态为<span style="color: #DF2A3F;">“已拒签”/“已过期”/“已撤销”</span>，展示“**重新发起签署**”按钮，点击“重新发起签署”相当于重新创建一个签署任务

##### 撤销签署



![Picture 8](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/2M9qP5jzyE0oDO01/img/90f2d945-634e-49c9-9006-d05976995496.png?Expires=1774156467&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=LbtfZh3WmCFN4xCxPWK1LP1fF4g%3D "")

1、当签署状态为“**签署中**”，展示“**撤销签署**”按钮

2、点击“撤销签署”，弹出撤销弹窗，支持输入 **撤销原因**（**非必填**），确认撤销 调用「[<span style="color: #0000FF;"><u>撤销签署流程</u></span>](https://open.esign.cn/doc/opendoc/pdf-sign3/klbicu)」撤销签署中的流程，签署状态变为“已**撤销**”

##### 签署详情

签署详情包括：**基本信息、电子合同、签署方、签署流程**

基本信息/签署方详情获取接口：「[<span style="color: #0000FF;"><u>查询签署流程详情</u></span>](https://open.esign.cn/doc/opendoc/pdf-sign3/xxk4q6)」

签署流程    详情获取说明文档：「[<span style="color: #0000FF;"><u>签署回调通知接收说明</u></span>](https://open.esign.cn/doc/opendoc/notify3/sblzg8)」

电子合同  下载接口：「[<span style="color: #0000FF;"><u>下载已签署文件及附属材料</u></span>](https://open.esign.cn/doc/opendoc/pdf-sign3/kczf8g)」

| **有成报销字段** |  | **e签宝参数** | **备注** |
|----------------------|---|-----------------|----------|
| 基本信息 | 发起人 | signFlowInitiator-psnInitiator-psnName或  signFlowInitiator-orgName-transactor-psnName |  |
|  | 签署状态 | data-signFlowStatus |  |
| 签署方 | 头像 |  | 固定头像 |
|  | 签署类型 | signers-signTaskType | 签署人有多个时，展示签署类型“**会签/或签**” |
|  | 签署人名称 | signers-psnSigner-psnName或 signers-orgSigner-transactor-psnName | 当签署方为机构签署方时，展示样式“**机构名称-经办人姓名**” |
|  | 当前签署状态 | signers-signStatus |  |
| 签署流程 | 头像 |  | 固定头像 |
|  | 操作时间 | 节点类型包括：**签署发起/签署人查看（已读）/签署结果/签署变更/签署转交/用章驳回/合同解约** |  |
|  | 流程节点名称 |  |  |

![Picture 9](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/2M9qP5jzyE0oDO01/img/0ed445bc-1f29-4715-ab9d-925abafc2ef2.png?Expires=1774156467&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=1SSft7KyLk7ahxE1SBWxMRSLw5I%3D "")

###### 未发起签署，无签署状态

签署详情页展示缺省图，文案“暂未发起线上签署”



![Picture 10](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/2M9qP5jzyE0oDO01/img/3a93a01c-57db-439a-86b4-14921da294cc.png?Expires=1774156467&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=mfnSBbxNY86HF92Lsluk%2FBN9c9E%3D "")

###### 签署状态：草稿



![Picture 11](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/2M9qP5jzyE0oDO01/img/b983bc39-4ba9-40d6-bd81-4d9a601c01fe.png?Expires=1774156467&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=XhVaynAt3iTucGpNRQYgFjZOaLQ%3D "")

1）**基础信息**展示：**发起人、签署状态**（取值逻辑见上表）

2）**电子合同**缺省文案：**签署未完成，暂无可下载的电子合同**

3）**签署方**缺省文案：**暂无签署方信息**

4）**签署流程**缺省文案：**暂未发起签署**

###### 签署状态：签署中



![Picture 12](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/2M9qP5jzyE0oDO01/img/9a6e7c5f-2aeb-4b49-befd-2e5340f67714.png?Expires=1774156467&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=U8DwJR6WPOPonwMl2KEcvhKEISI%3D "")

1）**基础信息**展示：**发起人、签署状态**（取值逻辑见上表）

2）**电子合同**缺省文案：**签署未完成，暂无可下载的电子合同**

3）**签署方**
- 头像：固定头像（UI提供）
- 签署类型：签署方选择多人签署时，展示签署方式（**会签/或签**）
- 签署方姓名：机构签署方—展示样式“**机构名称-经办人姓名**”；个人签署方—展示样式“**签署人姓名**”

4）**签署流程**

需要展示的流程节点类型包括：**发起签署、签署拒签/撤销/过期、签署人已读、签署变更、签署转交、签署完成、用章审批驳回、合同发起解约/解约成功**

详见：「[<span style="color: #0000FF;"><u>签署回调通知接收说明</u></span>](https://open.esign.cn/doc/opendoc/notify3/sblzg8)」



![Picture 13](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/2M9qP5jzyE0oDO01/img/0ed445bc-1f29-4715-ab9d-925abafc2ef2.png?Expires=1774156467&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=1SSft7KyLk7ahxE1SBWxMRSLw5I%3D "")

###### 签署状态：已拒签、已过期、已撤销



![Picture 14](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/2M9qP5jzyE0oDO01/img/41933725-ac5b-44a4-a3b5-2e11919a226f.png?Expires=1774156467&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=5qJxNOpB%2FDQCPhq%2B9ZGa2Rl0SKo%3D "")

签署状态为：已拒签/已撤销/已过期 时，可重新发起签署，流程同首次发起签署。（<span style="color: #DF2A3F;">注：撤销发起签署调用发起签署接口，重新创建一个新的签署任务</span>）

详情展示逻辑同“签署中”

###### 签署状态：已完成



![Picture 15](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/2M9qP5jzyE0oDO01/img/fd2c2dd1-32d0-4b12-95ea-831a81ad5c82.png?Expires=1774156467&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=4O%2FD05v%2FJGjz9cqtw2ZsUgcTXPg%3D "")

1）已完成签署的合同支持手动下载电子合同

2）**未下载合同**：电子合同 处展示缺省文案“暂未下载电子合同”

3）**已下载合同**：电子合同 处展示 已下载的电子合同，支持点击查看

### 5.4、合同列表增加合同“签署状态”字段

1）签署状态包括：**草稿、签署中、已拒签、已过期、已撤销、已完成**

2）**「我的-单据」「项目与合同-合同管理」，**列表中增加**“签署状态”**字段

##### 我的单据

我的-单据-全部，单据列表增加字段“签署状态”。当单据取不到签署状态时，显示为空；签署状态取e签宝签署任务状态



![Picture 16](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/2M9qP5jzyE0oDO01/img/a7b847d3-c9b6-4d29-bff6-9c49d142035f.png?Expires=1774156467&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=FIm8kwPdLGsH6ABgDyI0VMWyOK4%3D "")

##### 合同管理

合同管理-应付合同/应收合同/通用合同，单据列表增加字段“签署状态”。当单据取不到签署状态时，显示为空；签署状态取e签宝签署任务状态



![Picture 17](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/2M9qP5jzyE0oDO01/img/7f6d1415-2f14-4370-91dd-bd03a17ae65d.png?Expires=1774156467&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=8OpW0shEqyxJjTm6CFXKztpwVcg%3D "")
