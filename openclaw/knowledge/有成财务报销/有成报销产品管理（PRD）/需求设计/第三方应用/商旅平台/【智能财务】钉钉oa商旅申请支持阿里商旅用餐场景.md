---
title: "【智能财务】钉钉oa商旅申请支持阿里商旅用餐场景"
nodeId: G1DKw2zgV2RXBKQ3CP9YEdbRVB5r9YAn
workspaceId: R2PmK2gngjVnZXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/G1DKw2zgV2RXBKQ3CP9YEdbRVB5r9YAn?utm_scene=team_space"
updateTime: 1784101998000
exportedAt: 2026-07-16T11:07:06.525Z
source: dingtalk-document-mcp
---
> **版本**：v1.0 \| **产品**：智能财务 \| **客户**：智能财务客户   
> **修订记录**：v1.0(20260603)初始版本   

---

## 一、需求背景

### 需求现状：
1. 智能财务用户无法在钉钉oa中创建的商旅申请单发起用餐申请后，跳转至阿里商旅进行用餐业务；
2. 因为无法通过钉钉oa发去用餐申请，导致使用阿里商旅的客户无法将这部分用餐费用在智能财务里进行预算占用和费用标准控制。
3. 智能财务-阿里商旅订单入口后台可配置灰度，由技术将可使用阿里商旅订单入口的钉钉用户加入灰度配置内

### 客户预期：
1. 钉钉oa可以配置用餐申请单，发起用餐申请审批完后，可点击跳转至阿里商旅开始用餐
2. 钉钉oa中用餐申请发起时，支持根据所选的用餐费用校验费用标准是否超标和预算标准是否超额（费用标准和预算标准取自智能财务-预算费控）
3. 用餐申请产生的订单可以生成费用去报销

---

## 二、功能清单

| 模块 | 功能点 | 备注 |
|------|---------|------|
| 智能财务-申请套件 | “行程”控件增加招待用餐开关，隐藏部分行程参数 |  |
| 智能财务-招待用餐申请单 | 对接阿里商旅“新增用餐申请单” |  |
| 智能财务-单据详情 | 申请单审批通过后，显示“用餐”入口 |  |
| 智能财务-用餐费用 | 企业支付费用自动报销个人支付部分手动报销 |  |

## 三、功能需求

### 3.1 智能财务-申请套件内“行程”控件设置内增加“启用招待用餐”开关

**位置**：钉钉OA管理后台 → 工作台 → 应用管理 → OA审批-进入 → 创建审批单-空白 → 表单编辑 → 智能财务-申请套件  → “行程”控件打开设置 

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1GXn45Kp8BzwMqDQ/img/68998dd6-043a-4cfa-837d-ca36151ae203.png?Expires=1784207227&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=Hs28WG4%2FCTK6ih3uue7FoFeQPCA%3D "")

**功能描述**：
- **本次需求仅需实现钉钉OA差旅申请和钉钉OA招待用餐申请单详情出现“用餐”入口，满足企业用餐生成订单获取费用后去报销的业务场景，后续智能财务-个人-ai差旅相关用餐入口放后续版本迭代跟进**
- **“行程”控件设置增加“启用招待用餐”开关：**存量和新用户都默认关闭；
1. 开关开启：用户创建该单据的“行程”内隐藏“交通工具”“单程往返”“目的城市”，设置项看下图
2. 开关关闭：保持原逻辑不变

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1GXn45Kp8BzwMqDQ/img/ef934d77-1d12-4dd8-90bb-c4fdb1ed3b61.png?Expires=1784207227&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=UXmtNYNj12DZ0MisSt8dlM5OWZo%3D "")

### 3.2 钉钉OA表单-智能财务招待用餐申请单推送阿里商旅用餐申请

**流程**：发起钉钉OA用餐申请 → 填写用餐行程 → 审批后通过阿里商旅openapi-新增用餐申请接口传入 → 阿里商旅侧同步生成用餐申请  → 跳转阿里商旅首页h5。/ → 用餐结束生成订单 

**单据：**用餐申请单（包含智能财务申请套件），下不赘述

![画布 70.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1GXn45Kp8BzwMqDQ/img/7398dd38-6c8d-4d0a-8b82-a5fff05d8810.png?Expires=1784207227&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=xckT4TVi07GW1NOA30Ve9UrpcaE%3D "")

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1GXn45Kp8BzwMqDQ/img/5c65ad9f-4565-4927-95a4-d3866a57b5c4.png?Expires=1784207227&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=Mzsq1dSsxpjl8Yah8k2YfM2xcSs%3D "")

**功能描述**：
- **对接阿里商旅“新增用餐申请”接口，满足招待用餐场景：**

开通接口权限，获取应用凭证app\_key和app\_secret；地址：[阿里商旅开放平台](https://open.alibtrip.com/#/document/server/corptoken-enterprise-access-credential?handbookId=development-support)

审批完成的用餐申请单通过**“新增用餐申请单”接口将单据信息推送至“阿里商旅”，接口地址：**[https://open.alibtrip.com/#/document/server/api-btripopen-2022-05-20-applyadd-1?handbookId=development-support](https://open.alibtrip.com/#/document/server/api-btripopen-2022-05-20-applyadd-1?handbookId=development-support)

**传参信息：**

| **是否必传** | **商旅申请单（钉钉侧）** | **商旅申请单（钉钉侧）** | 描述 |
|----------------|----------------------------------|----------------------------------|------|
| 是 | 单据号钉钉单据号唯一id | 单据号third\_part\_apply\_id | 三方申请id参考对接酒店机票逻辑 |
| 是 | 单据状态传已完成的单据 | 申请单状态status1：已同意 |  |
| 是 | 申请总额 | 用餐额度meal\_amount | 根据单据申请总额去控制本次用餐可用额度 |
| 是 | 备注 | 用餐事由meal\_cause |  |
| 是 | 归属人钉钉用户id | 申请人-员工 Iduser\_id | 参考对接机酒逻辑 |
| 是 | 项目 | 项目名称project\_title | 参考对接机酒逻辑 |
| 是 | 行程 list行程唯一id | 第三方行程 Idthirdpart\_itinerary\_id |  |
| 是 | 出发城市 | 用餐城市-城市名称city\_name |  |
| 是 | 开始时间 | 开始时间start\_date | 时间参数填写必须为 yyyy-MM-dd HH:mm:ss 字符串格式 |
| 是 | 结束时间 | 结束时间end\_date | 时间参数填写必须为 yyyy-MM-dd HH:mm:ss 字符串格式 |
| 是 | 成本中心 | 申请单关联的三方成本中心 Id，和商旅成本中心 Id 二者选择其一即可 | 参考对接机酒逻辑 |
| 是 | 发票抬头 | 三方发票抬头 Id，和商旅发票抬头 Id 二者选择其一即可 | 参考对接机酒逻辑 |

其他用餐场景入口显示由阿里商旅后台用餐规则配置生效，其他用餐关联无需关联申请单若关联了申请单不影响其他业务场景，不影响本次需求

申请套件中“出发城市”作为阿里商旅的“用餐城市”

**对接阿里商旅“新增出差审批单”接口，跳转阿里商旅功能页：**

**已完成的差旅用餐申请单和招待用餐申请单**推送后获取“阿里商旅”返回的状态“success-true”，代表推送成功；本次需求差旅用餐申请使用的是之前机票酒店已经对接的“新增出差审批单”接口，已实现推送差旅申请单至“阿里商旅”，但是推送成功后单据详情需要显示“用餐”入口（目前没显示）；“新增出差审批单”接口地址：[https://open.alibtrip.com/#/document/server/api-btripopen-2022-05-20-applyadd-1?handbookId=development-support](https://open.alibtrip.com/#/document/server/api-btripopen-2022-05-20-applyadd-1?handbookId=development-support)

**用餐场景:**员工打开钉钉oa审批中的差旅用餐申请单和招待用餐申请单详情，则差旅和招待**“用餐”入口**分别显示，点击“用餐”唤起“阿里商旅”首页即视为成功，用户自行点击本次实际用餐场景“差旅用餐/团建招待”，选择后阿里商旅会参与处理；本次需要调用**商旅功能页跳转地址，枚举值传4**：[https://open.alibtrip.com/#/document/server/addressget-jump-to-business-travel-function-page?handbookId=development-support](https://open.alibtrip.com/#/document/server/addressget-jump-to-business-travel-function-page?handbookId=development-support)

**阿里商旅现有用餐规则管控逻辑：**阿里商旅用餐场景的规则可由申请单中的申请起始时间和申请总额管控或阿里商旅后台配置的规则管控，若申请单中的用餐额度不为0，则本次申请起始时间内可使用用餐订单总费用=申请单中申请总额；若申请单中用餐额度为0则以阿里商旅后台配置规则生效；阿里商旅用餐界面显示的用餐规则描述，不影响本次用餐申请中填写的申请总额的生效；示例：差旅用餐额度管控逻辑示例：

发起差旅申请，填写了申请额度1000元，阿里商旅后台配置了每日用餐额度50元-----申请通过后-----只要本次差旅申请时间内酒店订单，机票订单，用车订单和用餐订单的金额总计没有超过1000元，都可以使用

招待用餐额度管控逻辑示例：

发起招待用餐申请，填写了申请额度1000元，阿里商旅后台配置了每日用餐额度50元-----申请通过后-----只要本次招待申请时间内用餐订单的金额总计没有超过1000元，都可以使用

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1GXn45Kp8BzwMqDQ/img/80971a95-53d2-4c85-8b42-ac87c0491acf.png?Expires=1784207227&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=Eg%2FwULT6Yq7iCsp%2FLUbvoGIasp4%3D "")

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1GXn45Kp8BzwMqDQ/img/ab0b087f-2390-426f-a6ad-91264e3b3964.png?Expires=1784207227&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=F3Ch%2Fuvc%2BwaJEH4cZIlVgRVEO9w%3D "")

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1GXn45Kp8BzwMqDQ/img/d19a1526-b129-49b3-894a-1d5075d06399.png?Expires=1784207227&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=tO45bKk9zZx%2F29weDjhJuRf%2FgZ8%3D "")

支付完成后，**“阿里商旅”**后台生成一笔用餐订单

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1GXn45Kp8BzwMqDQ/img/73e1e207-80a3-4089-8dfa-e964f99adc97.png?Expires=1784207227&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=glRAyOO6YvNcoW7HEjvYWxCvPiE%3D "")

### 3.3 智能财务获取阿里商旅订单生成个人费用申请和企业支付会自动报销

**流程**：智能财务 → **获取“阿里商旅”用餐记账数据 → 拿到申请人id和订单id → 获取“阿里商旅”用餐订单** → 智能财务-个人支付部分随手记中生成费用申请/企业支付部分自动报销→ 个人支付部分根据费用申请提报销单

**功能描述**：
- **阿里商旅订单-差旅用餐订单和招待用餐订单金额=个人支付\+企业支付；当用餐金额全部由个人支付时，该笔订单不在阿里商旅后台作记录；用餐金额由个人和企业混合支付或全部由企业支付时，该笔订单在阿里商旅后台作记录；**
- **对接阿里商旅“用餐记账数据”接口：**

用餐记账数据接口地址：[https://open.alibtrip.com/#/document/server/api-btripopen-2022-05-20-mealbillsettlementquery?handbookId=development-support](https://open.alibtrip.com/#/document/server/api-btripopen-2022-05-20-mealbillsettlementquery?handbookId=development-support)

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1GXn45Kp8BzwMqDQ/img/abbd986c-4caa-4405-9b74-3bb4ea77031c.png?Expires=1784207227&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=rPv5bBPSdQX9COZ0ge9Zdynq4HQ%3D "")

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1GXn45Kp8BzwMqDQ/img/82a74104-fd2a-4d17-8c36-e33533ce8f6a.png?Expires=1784207227&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=VJhiEbhixIOsA2xmb2dEy5cfedQ%3D "")

- **对接阿里商旅“订单-用餐”接口：**

用餐订单列表接口地址：[https://open.alibtrip.com/#/document/server/api-btripopen-2022-05-20-mealorderlistquery?handbookId=development-support](https://open.alibtrip.com/#/document/server/api-btripopen-2022-05-20-mealorderlistquery?handbookId=development-support)

用餐订单详情接口地址：[https://open.alibtrip.com/#/document/server/api-btripopen-2022-05-20-mealorderdetailquery?handbookId=development-support](https://open.alibtrip.com/#/document/server/api-btripopen-2022-05-20-mealorderdetailquery?handbookId=development-support)

**参考机酒获取订单存储的字段，用餐订单获取的订单详情字段内容不变，订单金额仅显示企业支付总额和个人支付总额，以下示例：**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1GXn45Kp8BzwMqDQ/img/65f7273f-4417-44ea-ad43-ae60d8d75530.png?Expires=1784207227&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=3sl8XHvsAWFTdydB32qL0qh%2FhIM%3D "")

**以下列出用餐场景重要的业务字段，本次需求需开发：**

| **字段** | **名称** |
|----------|----------|
| merchant\_name | 餐饮商家门店名称 |
| settle\_time | 支付结算时间 |
| meal\_reason | 用餐事由 |

**“用餐信息”显示「餐饮商家门店名称」「支付结算时间」「用餐事由」，示例：**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1GXn45Kp8BzwMqDQ/img/1b4eafcf-45fe-4d62-98f4-711aad75e5da.png?Expires=1784207227&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=ps0dEl59LkAlJUqeBxf7qPKPpF4%3D "")
- **阿里商旅用餐订单需要通过【scene\_name 场景名称】字段将用餐订单区分成【差旅用餐】和【招待用餐】的订单，【差旅用餐】和【招待用餐】的订单同步到智能财务中可以分别绑定不同的支出，示例：【支出-差旅用餐】和【支出-招待用餐】**![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1GXn45Kp8BzwMqDQ/img/3870dafc-a470-418b-9a35-41c02baec231.png?Expires=1784207227&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=i2J2g%2FOdPh9iVTkIlZN5GVUVl7Q%3D "")
- **用餐订单信息中有企业支付的费用自动报销无需审批，**报销单中用餐支出-费用需提前指定由技术建立映射，企业提供智能财务-设置-收支出类别-支出里创建的费用的**类别编码**，智能财务中可查看该费用和报销信息，同时可在这笔报销单中查看订单信息，示例图如下**：**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1GXn45Kp8BzwMqDQ/img/e9088afd-4eba-464f-a704-9ae42168be5d.png?Expires=1784207227&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=kOz2y5vEvFjwuXyxlEVEVv5FST8%3D "")![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1GXn45Kp8BzwMqDQ/img/207e4f0b-b15a-4265-83af-cce1b7c38985.png?Expires=1784207227&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=uF3ru2wFFzc%2BHwLQRi5Db6JK56Y%3D "")

- **用餐订单信息中个人支付的费用作为个人随手记费用，**用户可直接使用该费用去报销或创建报销单关联该笔申请单自动带入费用去报销，报销单关联的申请单中点击穿透可查看到该申请单内订单信息，点击订单信息查看订单详情，示例图如下**：**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1GXn45Kp8BzwMqDQ/img/782cd93e-4fef-483f-8be6-82be699a4a01.png?Expires=1784207227&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=55%2BBCGz4Pi%2F4e%2FDorLUsqeqCwec%3D "")

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1GXn45Kp8BzwMqDQ/img/78c66efe-488d-4bac-a79d-da58481350e2.png?Expires=1784207227&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=8ck4L4jypVLLcT3fR1xtLFOc2dg%3D "")

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1GXn45Kp8BzwMqDQ/img/b7730b91-4850-4dd4-a98b-0ce37dfb24f0.png?Expires=1784207227&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=AVJFBKPC3%2B5igZ1%2BDM1n9oY4mcs%3D "")

**自动报销参考文档**

[预算、考勤、差旅对接实施手册.pdf](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1GXn45Kp8BzwMqDQ/att/25e43747-2105-4132-bb0f-97b6190bfdde.pdf?Expires=1784207227&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=zoHjIdMT3OShlCYRAeYQFY%2BQwWQ%3D)

