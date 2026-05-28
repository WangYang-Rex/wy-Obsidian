---
title: "PRD_有成报销_泛嘉国际对接优化：订单金额拆分展示、事前申请行程推送、消费生成配置"
nodeId: amweZ92PV6vZeDLpIK2qwmglVxEKBD6p
workspaceId: R2PmK2gngjVnZXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/amweZ92PV6vZeDLpIK2qwmglVxEKBD6p?utm_scene=team_space"
updateTime: 1779088441000
exportedAt: 2026-05-28T11:32:49.418Z
source: dingtalk-document-mcp
---
> **版本**：v1.0 \| **产品**：有成报销v2.0 \| **客户**：拓烯、味千、中科视语 **修订记录**：v1.0(20260514)基于原始需求文档（20260304）重新梳理   

---

## 一、需求背景

### 需求现状：
1. 泛嘉订单只展示结算价settlementPrice，没区分个人支付和企业预付金额，无法按实际付费方式灵活处理报销
2. 事前申请推送泛嘉用的是消费明细组件，与商旅业务不匹配（携程/阿里商旅都用行程组件）
3. 火车票只返回省-市三级地址，同城市多火车站无法区分
4. 消费生成固定取结算金额，不支持按付费方式拆分、不支持扣除服务费

### 客户预期：
1. 订单展示完整金额拆分（订单总金额、结算价（企业月结）、个人支付、企业支付金额（企业预付））
2. 事前申请支持按行程组件推送泛嘉
3. 消费生成支持灵活配置（含/不含服务费、允许/禁止个付生成消费）
4. 火车票消费事由自动填写出发站-到达站
5. 泛嘉接口文档：[泛嘉开放平台渠道对接接口说明精简版_20260119.docx](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Mp7ld7beyRRxxOBQ/att/1533cb2d-a17e-43d2-829e-df109d0f9665.docx?Expires=1779975170&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=gQN%2BK4qD53i%2Fiq2Lm1gfVOGf6mw%3D)


---

## 二、功能清单

| 模块 | 功能点 | 备注 |
|------|---------|------|
| 订单管理 | 机票/酒店/火车增加订单总金额、个人支付金额、企业支付金额（企业预付）金额 | 结算价（企业月结）保留 |
| 订单管理 | 打车增加服务费、订单总金额、企业支付金额（企业预付）金额 |  |
| 订单管理 | 四类订单导出同步增加新字段 |  |
| 事前申请配置 | 支持配置申请单单据模板、按行程推送 | 新用户默认行程组件 |
| 订单同步-消费事由 | 火车订单自动填写出发站-到达站到消费事由 | 默认关闭 |
| 订单同步-消费金额 | "不含服务费"和"允许个付金额生成消费"配置 | 默认：含服务费 \+ 允许个付 |
| 行程组件 | 预置新增出差用车、市内用车、加班用车 | 仅初始化刷入 |

---

## 三、功能需求

### 3.1 订单管理-金额拆分展示

**位置**：应用中心 → 泛嘉国际 → 订单管理 → 查看订单

![画布 22.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/8oLl9527AGXAelap/img/b0b7c91d-4c00-43c1-b696-8f8b6f5d38db.png?Expires=1779975170&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=El30Ltqq96Vw9PvntIMrE869jPk%3D "")

**机票/酒店/火车/打车**：新增订单总金额、个人支付金额、企业支付金额（企业预付）金额、结算价（企业月结）

泛嘉结算价字段名次解释：泛嘉结算价根据支付方式显示对应金额，企业支付金额（企业预付）-结算价，企业月结-结算价，本次需求中有成报销内泛嘉应用订单原结算价字段保留，用于显示企业月结金额；

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/8oLl9527AGXAelap/img/9d762dba-5f0e-40d7-892f-f262b9c42abd.png?Expires=1779975170&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=v9kx1UnlRr1lC506nAyUnw8IU8U%3D "")

| 字段 | 取值 | 备注 |
|------|------|------|
| 订单总金额（新增） | 个人支付 \+ 企业支付金额（企业预付）金额 |  |
| 个人支付金额（新增） | personalPayAmount |  |
| 企业支付金额（企业预付）金额（新增） | 企业支付金额（企业预付） → settlementPrice | 企业支付金额（企业预付）和结算价（企业月结）在泛嘉中取自同一字段，根据支付方式判断当前字段值属于哪种支付类型；订单中企业月结和企业支付金额（企业预付）的金额不会同时存在 |
| 结算价（企业月结） | 企业月结 → settlementPrice | 同上 |
- 四类订单导出同步增加新字段

### 3.2 事前申请-按行程推送泛嘉

**位置**：管理配置 → 事前申请配置

![画布 27.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/8oLl9527AGXAelap/img/1b821d34-2b5e-42d5-9ba0-30a04e7fb93e.png?Expires=1779975170&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=UCYffkae%2BXDDzJRZ8Q7NE42c0gA%3D "")

**配置项**：
- "同步至泛嘉的申请单"：多选，可选申请单类型的单据模板
- 推送内容：**单选必选**
    - 同步消费明细（老用户保持）
> 当消费明细中存在费用类型映射配置中的费用时，取费用中的字段进行推送。   
> 机票、火车：需要填写出发城市、目的城市、消费日期   
> 酒店：需要填写消费城市、起止日期   
> 出差用车、市内用车、加班用车：需要填写消费城市、消费日期   
    - 同步行程组件（新用户默认）
> 根据行程组件中交通工具的名称，取行程组件中的字段进行推送。   
> 飞机、火车、出差用车：需要填写出发城市、目的城市、日期   
> 市内用车、加班用车：需要填写目的城市、日期   
> 酒店：需要填写目的城市、起止日期   
    - 当行程组件中仅配置了单一日期，但接口中要求传开始日期、结束日期时，开始日期和结束日期都传行程中的日期。当行程组件中配置了起止日期时，对应传入开始日期、结束日期。

![PixPin_2025-11-20_15-20-15.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/8oLl9527AGXAelap/img/963947be-8da4-463d-8571-71494fe02667.png?Expires=1779975170&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=pU6L4TmKyWK%2BzZR84YQXnpKktLs%3D "")
    - 行程是国际还是国内，接口文档中有明确说明。
    - 当交通工具名称为飞机、火车，出差用车时，行程按照出发城市、目的城市对应传参。
    - 当交通工具名称为市内用车、加班用车、酒店时，
    - 若用户未填写出发城市，则传目的城市到出发城市中去。
    - 若用户填写了出发城市，则按照用户填写值传。
    - 若用户均没有填写，就不传，泛嘉中有默认城市的逻辑。
    - 注意：因为泛嘉的事前申请和携程一样，只到国家-省-市级，但我们的城市组件支持到国家-省-市-区县级，不管是用费用组件同步还是用行程组件同步，本次都需要针对选到区县级的情况做兼容。有成单据中的城市选择到了区县，则按照区县对应的市传给泛嘉。
    - 按照行程上维护的行程类型，单程还是往返，对应传参。
    - 出行员工id按照申请单补充设置中的配置传参。

![PixPin_2025-11-20_15-17-20.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/8oLl9527AGXAelap/img/6decb276-355d-4184-a338-0685ca040562.png?Expires=1779975170&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=%2F%2FB4bSAQyn7DSSKKppP5PveRjO0%3D "")



**城市兼容**：选到区县级时，取对应**市**传给泛嘉

### 3.3 订单同步-增加自动生成消费事由配置开关

#### 自动生成消费事由
- 开关控制，开启后火车订单自动将订单内的"出发站-到达站"填写到费用里的消费事由
- 历史用户、新用户默认关闭

![PixPin_2025-11-20_16-54-57.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/8oLl9527AGXAelap/img/9d6fcf67-3ea4-4fe7-85f5-784974489359.png?Expires=1779975170&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=NqN3hf0dJj%2F2%2FNCnToBopIZ34iA%3D "")

![PixPin_2025-11-20_16-54-00.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/8oLl9527AGXAelap/img/77ab97f2-e8e3-4c58-b0c5-5ee23602abc9.png?Expires=1779975170&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=Iq%2BQj9WDQIpW1qTXgDakyaRyBZA%3D "")



#### 生成消费金额规则

![画布 23.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/8oLl9527AGXAelap/img/6d8c2b65-a0f6-4df1-ac42-a31bc12ff2ba.png?Expires=1779975170&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=QLGRd%2BIVXoyLZ6xPOcTfH2%2FZp0M%3D "")

**订单按付费方式拆分生成消费**：

| 付费组成 | 消费数 | 消费金额 | 服务费归属 |
|------------|---------|------------|---------------|
| 个付 \+ 企业结算 | 2笔 | 个付 \+ 企业结算 | 归属企业结算 |
| 个付 \+ 企业支付金额（企业预付） | 2笔 | 个付 \+ 企业支付金额（企业预付） | 归属企业支付金额（企业预付） |
| 个付 | 1笔 | 个付 | 归属个付 |
| 企业结算 | 1笔 | 企业结算 | 归属企业结算 |
| 企业支付金额（企业预付） | 1笔 | 企业支付金额（企业预付） | 归属企业支付金额（企业预付） |

**泛嘉服务费归属逻辑**：有企业支付金额（企业预付）/结算时服务费归企业；仅个付时服务费归个付

**新增“消费金额”生成规则配置**：

| 配置 | 默认 | 效果 |
|------|------|------|
| 不含服务费 | 不勾选 | 消费中扣除服务费 |
| 允许个付金额生成消费 | 勾选 | 勾选状态：<br>a.个付金额生成消费，支持报销<br>b.企业支付金额（企业预付）/企业月结生成消费，消费上有“企业月结”“企业支付金额（企业预付）”标签，带入报销后不统计这部分金额<br>不勾选状态：<br>a.个付金额不生成消费<br>b.企业支付金额（企业预付）/企业月结生成消费，消费上有“企业月结”“企业支付金额（企业预付）”标签，带入报销后不统计这部分金额 |
- 新配置只对新订单生效
- 默认币种 **CNY**

### 3.4 我的-泛嘉消费展示pc端和mb端

![](https://static.dingtalk.com/media/lQDPM4AxB0jX463NBBHNBQCw2RHQJFCWu2AJ3D_R1tE2AA_1280_1041.jpg "")

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Mp7ld7beyRRxxOBQ/img/b7358335-a1ca-4404-b7d2-dbf955e277b9.png?Expires=1779975170&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=jKI6dYEg8Dbmhuvk85rzF7V1PTg%3D "")

泛嘉订单生成的消费信息，会有个付，企付，月结标签，pc和mb都要有

### 3.5 行程组件预置选项
- 初始化行程组件时新增：**出差用车、市内用车、加班用车三个可选项**
- 用户可删除，仅初始化时刷入

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/8oLl9527AGXAelap/img/9be4c77c-e2ce-4de4-b7f0-fa06df1d5e0a.png?Expires=1779975170&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=UYS3ybJRAcCDxWJm%2FyiRV8kbq4k%3D "")

### 3.6 端适配

| 端 | 适配说明 |
|---|------------|
| PC端 | 订单管理 \+ 管理配置 |
| 移动端 | 消费信息展示，报销支付金额不统计预付和月结 |

---

## 四、附录

### 4.1 历史关联需求

无

### 4.2 技术方案参考

| 文档名称 | 说明 |
|------------|------|
| 泛嘉开放平台渠道对接接口说明精简版 | 接口字段定义 |

---

## 五、变更记录

| 日期 | 版本 | 变更内容 | 负责人 |
|------|------|------------|---------|
| 20260514 | v1.0 | 基于原始文档重新梳理 | 小策 |
