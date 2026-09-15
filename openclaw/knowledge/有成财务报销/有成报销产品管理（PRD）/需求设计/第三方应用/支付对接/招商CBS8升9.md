---
title: "招商CBS8升9"
nodeId: ydxXB52LJq7laP2NhZvDYQBdWqjMp697
workspaceId: R2PmK2gngjVnZXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/ydxXB52LJq7laP2NhZvDYQBdWqjMp697?utm_scene=team_space"
updateTime: 1789453729000
exportedAt: 2026-09-15T06:33:49.686Z
source: dingtalk-document-mcp
---
| **修订时间** | **版本** | **修订说明** | **作者** |
|----------------|----------|----------------|----------|
| 20260902 | v1.0 | 初版编制 | 燧石 |
|  |  |  |  |

## 1、涉及系统

有成报销 PC& MB

## 2、需求背景

历史已经对接过招商CBS8（云直联）方式，目前招商内部完成了C8升C9，导致需要我们进行适配才能满足。

目前根据招商反馈，C8和C9的区别在于获取token和加密加签等会有所区别，以及相应的接口地址都做了更新，所以按照新对接方案来处理

## 3、功能清单

| **模块** | **功能点** | **备注** |
|----------|-------------|----------|
| 有成财务管理后台 | 新增版本 |  |
| 接口文档 | [https://cbscloud.cmbchina.com/open-center/#/cbs/doc/open-document?id=14755&mid=18966](https://cbscloud.cmbchina.com/open-center/#/cbs/doc/open-document?id=14755&mid=18966) |  |

## 4、需求详情

### **4.1后台管理**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/r4mlQ51Vm7meXlxo/img/9e54b1d9-4741-4f6b-8909-b4f21630c8e2.png?Expires=1789461230&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=VYeKPsRZ1t8muYqoRw18QABMNdA%3D "")

在后台管理中，选择招商CBS时，下方的版本新增选项“cbs9”
1. 应用id、应用密钥：必填项文本框，完成平台内应用创建时，即可拿到相应的内容![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/r4mlQ51Vm7meXlxo/img/22592d06-90c3-40ce-a17c-6bc4f5bbe043.png?Expires=1789461230&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=eC1sbEmOgdqwu%2FxLPF5pRybKXo0%3D "")
2. 企业公钥、企业私钥：必填项文本框可以通过工具生成公私钥对[https://cbscloud.cmbchina.com/open-center/#/cbs/tools/generateKeys](https://cbscloud.cmbchina.com/open-center/#/cbs/tools/generateKeys)
3. 平台公钥：必填项文本框，招行存在固定的平台公钥<span style="color: rgba(19, 34, 64, 0.95);">测试环境的值： 0401ED4B9E0FBC9754F36390D70D60AB4E50BE2B9C2D3AD7C9CF3F387721CBC6B90375BC0C6DF8754A1542BDB45DBB6D235EC968892F0C338F21414B366A3B3D07</span><span style="color: rgba(19, 34, 64, 0.95);">生产环境的值：04C591B5866F217E8D4F7AA11DF45FEF5102C65884D29F7D5D10234F18B0BC60FD312DA3C5FD506058D33643CFC7C926B2D7A4D5ECEFBFBAAE34734525722B0B55</span>

### **4.2应用中心**

#### 4.2.1调用接口流程

<span style="color: rgba(19, 34, 64, 0.95);">先获取accessToken，再使用accessToken去调用其他接口</span>

<span style="color: rgba(19, 34, 64, 0.95);">生产环境地址：</span>[<span style="color: rgba(19, 34, 64, 0.95);">https://openbanking.cmbchina.com/cbs-basic/common/cbs-service-open-rest-new/cbs/create/access-token</span>](https://openbanking.cmbchina.com/cbs-basic/common/cbs-service-open-rest-new/cbs/create/access-token)

<span style="color: rgba(19, 34, 64, 0.95);">测试环境地址：</span>[<span style="color: rgba(19, 34, 64, 0.95);">https://openbanking.cmburl.cn/cbs-common/com/cbs-service-open-rest-new/cbs/create/access-token</span>](https://openbanking.cmburl.cn/cbs-common/com/cbs-service-open-rest-new/cbs/create/access-token)

| **接口** | **入参** | **出参** | **备注** |
|----------|----------|----------|----------|
| 实 |  |  |  |
|  | 企业编码：必填 |  | 后台管理配置内容 |



#### 4.2.2支付明细管理

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/v9kqDejmDMYBMOVx/img/3a9a1a00-10ec-4ad6-9308-5c65512d4d86.png?Expires=1789461230&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=afafKsMmp%2B8yufiLUnyTJWbpKp0%3D "")

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/v9kqDejmDMYBMOVx/img/43a71ef1-22ff-4943-a941-4a0ee4060d6d.png?Expires=1789461230&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=ULeGcH%2BkMMwNOsp5fxzDWFTY2Dc%3D "")

表头字段：
- 序号：顺序生成
- 批次编号：系统自动生成，基于发起的每笔支付顺序生成。【复用其他财资银行的生成规则】
- 业务参考号：YOUCHENG-时间戳【复用其他财资银行的生成规则】
- 单据号：对应支付单据的单据号【若存在多个“，”隔开】
- 业务摘要：取接口中摘要（summary）内容
- 员工
- 收款账户：根据loanType：借贷标记（借:1；贷:2）判断，若是（1）则视为支出，则取值对方账号；若是（2）则视为收入，则取值账户
- 支付账户：根据loanType：借贷标记（借:1；贷:2）判断，若是（1）则视为支出，则取值账户；若是（2）则视为收入，则取值对方账号
- 金额：取接口中交易金额（amount）
- 用途：取接口中用途字段（transUse）
- 状态：
- 电子回单：展示文件。

#### **4.2.3账号管理**

默认无账户，页面展示为空。添加成功后，会展示相应的账户，并且会标记为“农行银企联”【同时基础档案--公司账户中的账户也会展示该标记】

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/r4mlQ51d1gjPBlxo/img/7bbe546e-ba24-4a5b-b1f2-fb048197105e.png?Expires=1789461230&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=AbWd2DhISTm0Q2WkcOqFG8bdWF4%3D "")

点击【添加】，展示选择账户弹窗：（仅展示银行账户，单选）

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/v9kqDejmDMYBMOVx/img/ea1bb5e0-d365-4429-a40d-28cee89b88d3.png?Expires=1789461230&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=weQn6ur36SJGUybpt0X%2Fs4Wn2dQ%3D "")

选中账户后点击确定时，调用【实时余额查询】接口

| **接口** | **入参** | **出参** | **备注** |
|----------|----------|----------|----------|
| 实时余额查询 |  |  |  |
|  | 企业编码：必填 |  | 后台管理配置内容 |
|  | ERP编号：必填 |  | 后台管理配置内容 |
|  | 请求ID：必填 |  | 每次调用请求的唯一ID，要求按照“年月日时分秒毫秒\+corpID；yyyyMMddHHmmSSsssXXXX”的格式来生成 |
|  | 交易码：必填 |  | 调用接口的编码，当前接口固定传：itms0009 |
|  | 余额类型：必填 |  | 固定传：1（实时余额） |
|  | 账号：必填 |  |  |
|  |  | 指令状态（cmdStat） |  |
1. 若系统未查询到符合条件的交易明细数据，会返回 cmdStat：3
2. 若系统查询到数据，并正常返回则视为已开通可以添加



注：添加成功后可删除，点击删除出现二次确认弹窗，确认后则直接将账号从授权账户列表删除【同时公司账户的对应账户解绑，去掉标记】

#### **4.2.4管理设置**

点击后弹窗展示：

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/r4mlQ51d1gjPBlxo/img/e7ea2537-7a90-4b76-a0e3-0f02734fa51b.png?Expires=1789461230&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=TUCCF0%2Bm9JdnQGkdV2O5GgcKM%2B0%3D "")

1、页面展示：用途、摘要两个选项

2、用途、摘要这两个字段为下拉多选框：从固定字段、单据字段、费用字段选择字段【同现有逻辑一致】

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/v9kqDejmDMYBMOVx/img/72430d83-047a-4080-90d9-c908811405e6.png?Expires=1789461230&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=UV7LiKdbGHAiIrfjJgPchH7xP8E%3D "")

3、批量提交人id、名称；提交人id、名称：这四个字段均为文本框，必填项。用户自行填写，会在调用【批量支付】接口时传参使用

4、审批人、经办人：文本框，非必填。若用户在农银睿达司库平台配置了需要审批，那么这两个字段就需要有值才能调用；若未配置需要审批，那么可以不填不传注：若用户配置了需要审批，在调用的时候这边并未配置，那么接口调用失败报错即可



### **4.3资金明细**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/WgZOZA8eW6V98qLX/img/535dc65a-07dd-480c-943d-ec0ed899f949.png?Expires=1789461230&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=xv%2Fifkzb0qcxhVsXreFKrbGm2nA%3D "")

| **接口** | **入参** | **出参** | **备注** |
|----------|----------|----------|----------|
| 交易明细查询 |  |  |  |
|  | 企业编码：必填 |  | 后台管理配置内容 |
|  | ERP编号：必填 |  | 后台管理配置内容 |
|  | 请求ID：必填 |  | 每次调用请求的唯一ID，要求按照“年月日时分秒毫秒\+corpID；yyyyMMddHHmmSSsssXXXX”的格式来生成 |
|  | 交易码：必填 |  | 调用接口的编码，当前接口固定传：itms0008 |
|  | 账号 |  |  |
|  | 起始日期 |  | 格式 yyyy-MM-dd HH:mm:ss，
起始日期与结束日期间隔不能大于 31 天。 |
|  | 结束日期 |  | 格式 yyyy-MM-dd HH:mm:ss，
起始日期与结束日期间隔不能大于 31 天。 |
|  |  | 响应ID（rspId） |  |
|  |  | 交易返回码（resultCode） | "0","通信成功" <br>"1","交易处理中" <br>"2","交易失败" <br>"9","通信出错" |
|  |  | 交易返回信息（resultMsg） |  |
|  |  | 交易时间 | ![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/WgZOZA8eW6V98qLX/img/0eaa3458-1734-4135-8dc8-313e9b2dd270.png?Expires=1789461230&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=UvpEHOMAvpJ1zyUNDbPG%2BX4%2BWT0%3D "") |
|  |  | ERP单号（企业流水号） | ![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/WgZOZA8eW6V98qLX/img/ecc474e7-b514-4415-af0b-29111731b076.png?Expires=1789461230&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=6CMWiZNGBppVCVXrNHB2vvcQpFA%3D "") |
|  |  | 交易金额 | ![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/WgZOZA8eW6V98qLX/img/57d3725e-16cf-4cbd-ac4f-d7431211943b.png?Expires=1789461230&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=7zf1CLZjYW3jcL%2BmULVgP%2B3y1zQ%3D "") |
|  |  | 借贷标记 | ![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/WgZOZA8eW6V98qLX/img/1f95dc9d-e2f7-4929-82e0-4d5859f87aab.png?Expires=1789461230&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=XgP%2Fi3jAgA6MArGj8XmKpziFbCs%3D "")<br>借：1【支出】<br>贷：2【收入】 |
|  |  | 对方账号 | ![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/WgZOZA8eW6V98qLX/img/e60f3fd9-2222-4853-8f83-9042ba8ba19e.png?Expires=1789461230&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=4nLAXjCuv0IC3QYBR8Yp%2BQxLFEI%3D "") |
|  |  | 对方账号名称 | ![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/WgZOZA8eW6V98qLX/img/218aecff-7b09-4ead-b142-2ad8ea5f3544.png?Expires=1789461230&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=3RvQcrdaotZnYq1woA3Ft0z%2BAc4%3D "") |
|  |  | 用途 | ![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/WgZOZA8eW6V98qLX/img/02bb67f5-f26f-4029-a4a6-dbf06eb24ae4.png?Expires=1789461230&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=8fPqd8ebSCa9rCCRfJ9Fah6JVPI%3D "") |
|  |  | 账户余额 | ![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/WgZOZA8eW6V98qLX/img/4c26caf7-8ac1-466f-a259-0701ecaf3d0c.png?Expires=1789461230&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=0HXUMRO3l4rRJe1Hv9S5XMOoF0k%3D "") |
|  |  | 摘要 | ![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/WgZOZA8eW6V98qLX/img/352cfa53-81ef-4713-99e6-ed9637f8e97a.png?Expires=1789461230&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=oTrQwpU5dAcHhreCGKkrgi%2FNfuY%3D "") |
|  |  | 银行流水号 | 查询电子回单时使用 |
| 注：该接口是通过定时任务每半小时查询一次，获取更新账户交易明细信息，交易成功后最晚半小时可获取到交易明细。 |  |  |  |
| 电子回单下载 |  |  |  |
|  | 企业编码：必填 |  | 后台管理配置内容 |
|  | ERP编号：必填 |  | 后台管理配置内容 |
|  | 请求ID：必填 |  | 每次调用请求的唯一ID，要求按照“年月日时分秒毫秒yyyyMMddHHmmSSsss”的格式来生成 |
|  | 交易码：必填 |  | 调用接口的编码，当前接口固定传：itms0007 |
|  | 银行流水号 |  | 用交易明细查询接口中返回的银行流水号进行查询（bankBusinessId） |
|  | 账号 |  |  |
|  |  | 文件流 | 经过base64加密后的文件流 |
|  |  | 下载状态 | "1","下载成功" <br>"2","下载失败" |
|  |  | 失败原因 |  |
| 注：该接口可查询过去到前一日的电子回单（T-1 日）。 |  |  |  |

### **4.4支付**

注意：PC\+移动端均需要进行如下调整

#### **4.4.1单笔/批量支付**
- 点击确定向农行发起支付，无论是单条还是批量都走【批量转账】接口。发起完成后在支付明细列表生成相应的数据，并自动生成批次编码

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/r4mlQ51d1gjPBlxo/img/f1e7bf40-c2d4-4ded-9002-57786b94659a.png?Expires=1789461230&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=u0%2BuZ%2FmrFN8dlVwE4AjQ5Nx%2FTpk%3D "")

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/r4mlQ51d1gjPBlxo/img/b2fd79dc-a631-415f-9a9f-504cbf9f049e.png?Expires=1789461230&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=Ziw%2BLEvWL0Z5P3jbkIwCFCK08x0%3D "")
1. 当选择农行银企联支付时，右侧会展示“加急标识”字段，并且默认选中“一般”
2. 加急标识：下拉单选框，枚举值“一般、加急、特急”。
3. ~~并且当选择农行银企联支付时，多加一个判断，本次的收付款银行是否填写了开户行所在省市、开户行和联行号。若均填写则可以正常否则，只要有一个未填写（无论是收款还是付款银行）均会提示“农行银企联要求维护收付款银行的开户行所在地及名称以及联行号信息才可发起支付”~~注：该判断特指农行银企联中的司库版本

| **接口** | **入参** | **出参** | **备注** |
|----------|----------|----------|----------|
| 先调用开户行信息查询接口 |  |  | 查询收款银行的银行类型 |
|  | 企业编码：必填 |  | 后台管理配置内容 |
|  | ERP编号：必填 |  | 后台管理配置内容 |
|  | 请求ID：必填 |  | 每次调用请求的唯一ID，要求按照“年月日时分秒毫秒\+corpID；yyyyMMddHHmmSSsssXXXX”的格式来生成 |
|  | 交易码：必填 |  | 调用接口的编码，当前接口固定传：itms0019 |
|  | 联行号：必填 |  |  |
|  | 开户行名称：必填 |  |  |
|  |  | 银行类型 | 拿到返回的银行类型编码 |
| 再调用批量转账接口 |  |  |  |
|  | 企业编码：必填 |  | 后台管理配置内容 |
|  | ERP编号：必填 |  | 后台管理配置内容 |
|  | 请求ID：必填 |  | 每次调用请求的唯一ID，要求按照“年月日时分秒毫秒yyyyMMddHHmmSSsss”的格式来生成 |
|  | 交易码：必填 |  | 调用接口的编码，当前接口固定传：itms0002 |
|  | ERP 系统批次提交 <br>人 id：必填 |  | 后台管理配置内容 |
|  | ERP 系统批次提交 <br>人 名称：必填 |  | 后台管理配置内容 |
|  | 经办人：非必填 |  | 我们必填，固定取值后台管理配置内容。一旦司库系统配置需要审批该值就是必填 |
|  | 审批人：非必填 |  | 我们必填，固定取值后台管理配置内容。一旦司库系统配置需要审批该值就是必填 |
|  | 付款金额：必填 |  |  |
|  | 付款账号：必填 |  |  |
|  | 付款账户名称：必填 |  |  |
|  | 收款账号：必填 |  |  |
|  | 收款账号名称：必填 |  |  |
|  | 收款银行联行号：必填 |  | ~~是否必填要根据本次支付是跨行还是同行~~<br>~~再根据附录1表规则判断收款银行在这个情况下是否必填联行号~~ |
|  | 收款银行类型：必填 |  | 根据开户行信息查询接口来获取 |
|  | 是否同城：必填 |  | ~~根据收付款账户开户行所在城市判断是同城还是异地。~~<br>~~而是否要填写该值，需要根据收款银行前往附录一进行判断，同城异地标识是否必填~~<br>1：同城<br>2：异地 |
|  | 加急标识：必填 |  | 根据发起支付时选择的标识来传参<br>1:一般<br>2：加急<br>3：特急 |
|  | 对公对私属性：必填 |  | 1：对公<br>2：对私 |
|  | 跨行标识：必填 |  | 根据收付款账户开户行所在城市判断是同城还是异地<br>1：同行<br>2：跨行 |
|  | 汇款附言：非必填 |  | 由于一旦满足某些条件，该字段需要上送“ERP单号”才能完成该条件下的点击回单获取。<br>所以为必填做额外复杂判断，该字段值固定传erp单号字段<br>【已跟银行确认，该值固定传参没有任何影响】 |
|  | erp系统提交人id：必填 |  | 后台管理维护 |
|  | erp系统提交人名称：必填 |  | 后台管理维护 |
|  | erp单号（企业流水号） |  | 生成规则：年月日时分秒\+8位流水<br>要求每次发起，都要重新生成一个新的（例如发起失败，再次发起也要重新生成） |
|  |  | 指令状态  | "0","成功" <br>"2","交易失败" |
| （1）需要审批：审批通过后，根据定时任务五分钟内发送支付指令。 <br>（2）不需要审批：根据定时任务五分钟内发送支付指令。 |  |  |  |

#### **4.4.2支付状态**

调用【付款结果查询】接口，查询支付请求的状态：

| **接口** | **入参** | **出参** | **备注** |
|----------|----------|----------|----------|
| 付款结果查询 |  |  |  |
|  | 企业编码：必填 |  | 后台管理配置内容 |
|  | ERP编号：必填 |  | 后台管理配置内容 |
|  | 请求ID：必填【报文头】 |  | 每次调用请求的唯一ID，要求按照“年月日时分秒毫秒\+corpID；yyyyMMddHHmmSSsssXXXX”的格式来生成 |
|  | 交易码：必填 |  | 调用接口的编码，当前接口固定传：itms0003 |
|  | 请求ID：必填【报文体】 |  | 用批量转账接口中上送的reqId（请求ID）字段来上送<br>注：批量转账接口的响应报文会返回这个请求ID，需要存储下来，进行付款结果查询使用 |
|  | ERP单号：必填 |  |  |
|  |  | 审核状态 | "0","待提交" <br>"1","待审核" <br>"2","审批未通过" <br>"4","审批通过" <br>"5","已撤回" <br>"7","退回待处理" <br>"8","已作废"<br>若未配置审批，会回传审批通过 |
|  |  | 交易状态 | "1","待发送" <br>"2","已发送" <br>"3","等待获取结果" <br>"4","同步处理结果异常" <br>"5","交易失败" <br>"6","已发送异步消息" <br>"7","异步处理结果异常" <br>"8","交易成功" <br>"9","交易超时" <br>"10","发送失败" <br>"11","发送中" <br>"12","交易异常" <br>"13","交易撤销" <br>"14","交易不存在" <br>"15","交易未明" <br>"16","部分交易完成" <br>"17","退回 ERP" |
|  |  | 付款账号  |  |
|  |  | 付款账号名称  |  |
|  |  | 失败原因 |  |
| 注：<br>1、交易信息发送后，通过定时任务五分钟一次查询交易结果，最晚十分钟可通过该接口 <br>查询到交易结果。【5分钟一次轮询调用接口】<br>2、当交易状态为“交易成功”时，视为支付成功 |  |  |  |

#### **4.4.3电子回单**

需要调用“电子回单下载”接口获取：
- 单据详情：取到回单后，将回单对应上传到单据中的审批历史中可查看到；
- 资金明细：资金明细中可查看到回单

### **4.5银行图标**

[农业银行.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/r4mlQ51Vm7meXlxo/att/bdf9d6de-0470-4b0c-ba08-d7ac4b44c081.png?Expires=1789461230&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=2BGxupCRDdEyBu7vv4HEJ76yHaE%3D)


