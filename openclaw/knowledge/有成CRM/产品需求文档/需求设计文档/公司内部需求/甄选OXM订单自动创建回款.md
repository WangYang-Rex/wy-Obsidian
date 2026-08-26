---
title: "甄选OXM订单自动创建回款"
nodeId: Gl6Pm2Db8D3mXMgZTe6RxPD2JxLq0Ee4
workspaceId: R2PmK2Q8rxRbeXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/Gl6Pm2Db8D3mXMgZTe6RxPD2JxLq0Ee4?utm_scene=team_space"
updateTime: 1785894549000
exportedAt: 2026-08-05T04:11:55.976Z
source: dingtalk-document-mcp
---
| 修订时间 | 版本 | 修订人 | 修订说明 |
|-----------------------------------------------------------------------|-----------------------------------------------------------------|--------------------------------------------------------------------|-----------------------------------------------------------------------|
| 2026-7-3 | v1.0 | 黄艺平 | 新建 |
|  |  |  |  |

## 需求背景

钉钉甄选订单生成后，渠道同事需要手动去新增一笔实际回款，填写工作量大，需要订单生成后自动生成一笔实际回款，考虑实际回款配置变动较为频繁，用工作流生成。

## 需求说明

### **数据范围**

满足以下条件的合同订单，需要自动生成实际回款

![Pasted Graphic 52.tiff](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/YdgOk2b89JKL7q4B/img/f0181642-f627-41c5-8871-e6c9010ec51c.tif?Expires=1785910316&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=sScolgBAeDmd9t62xLK1IRcIMGQ%3D "")

### **触发条件**

**需要宏森开发：**通过接口的新增，也要触发工作流（仅有成系列客户管理平台这家企业）

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/YdgOk2b89JKL7q4B/img/1fb45a7c-a51c-4764-97c8-bf10af21b181.png?Expires=1785910316&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=MaOqKfPlyuxdCFyE4SDYTo37lHs%3D "")

### **字段映射**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/YdgOk2b89JKL7q4B/img/097c6b5e-a885-4025-b7d9-828df8f606ee.png?Expires=1785910316&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=FxHsI5H75Kfzxp0fVGZVeo6yIXc%3D "")

| 实际回款字段 | 取值逻辑 | 备注 | 备注 |
|------------------|------------|------|-------------------------------------------|
| 真实姓名\+工作花名 | 客户负责人.员工姓名 |  |  |
| 提交人 | 合同订单.客户负责人
sale\_order\_refer\_object\_3 | **需靖哥开发：**
生成订单时，取 合同订单.客户 的 负责人
新客户 没有分配时是系统或者为空 负责人取谁？
确认：负责人取小雾 | OK |
| 负责人 | 合同订单.客户负责人 |  |  |
| 客保架构客户名称 | 合同订单.客户 |  |  |
| 付款客户名称 | 合同订单.客户名称 |  |  |
| 下单架构组织名称 | 合同订单.客户名称 |  |  |
| 回款类型 | 合同订单.回款类型
sale\_order\_select\_100008
字典值如下：
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/YdgOk2b89JKL7q4B/img/be13dddf-19d4-475a-8960-00622f5951b3.png?Expires=1785910316&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=cFCZdynwTO7oTPAC%2FvRr3xe6ysw%3D "") | **需靖哥开发：**
生成订单时，自动生成，选项判断逻辑参考 合同订单.合同订单交易类型 字段选项值
新订-\>新签(无实施)-有成财务/crm/报销/智能财务预算费控
续订-\>续费
升版本续费-\>续费
降版本续费-\>续费
升级-升级人数增加
依据订单里面字段 还是需要我们自己的订单表里面查询
确认：取订单字段 | ok |
| 客户交接单 | - |  |  |
| 转化周期(天) | - |  |  |
| 该客户来源 | 服务商/代理商 |  |  |
| 是否是代理商客户 | 是 |  |  |
| 代理商提单 | - |  |  |
| 关联代理商 | 合同订单.关联代理商
real\_payment\_refer\_object\_7 | **需靖哥开发：**
生成订单时，自动生成
直接依据代理商名称来匹配 代理商库cus\_form\_13？
是的，没有匹配到就设置为空 优先等值查询 再包含查询（如原始订单代理商=杭州光云，优先看是否有代理商=杭州光云，若没有，则看有无代理商名称包含杭州光云，若有多个取第一个） |  字段应是 ：sale\_order\_refer\_object\_4 |
| 代理商分润比例 | 关联代理商.服务商分润比例 |  |  |
| 业务日期 | 合同订单.下单日期 |  |  |
| 客户公司地址 | - |  |  |
| 销售对接客户需求（承诺需求） | - |  |  |
| 是否有售前 | - |  |  |
| 开通架构管理员姓名 | - |  |  |
| 开通架构管理员手机号码 | - |  |  |
| 下单情况详细描述 | - |  |  |
| 关联优惠价申请单 | - |  |  |
| 收款方式 | 甄选OXM |  |  |
| 收款截图 | 设置固定值 | **需要宏森开发：**
-活动-字段映射-图片/附件类型字段，可以设置空值/固定值/联动值
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/YdgOk2b89JKL7q4B/img/6fdde081-98da-4beb-b76c-439ee6ba3ac9.png?Expires=1785910316&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=Z3lFvnLd054qYIqUFTL8HRPMggM%3D "") |  |
| 本次收款金额 | 0 |  |  |
| 本次收款日期 | 合同订单.开始时间 |  |  |
| 未回款金额 | 0 |  |  |
| 是否预收 | 否 |  |  |
| 下单日期 | 合同订单.下单时间 |  |  |
| 客户来源 | 代理商 |  |  |
| 订购平台 | 钉钉 |  |  |
| 订购产品 | 合同订单.订购产品
sale\_order\_select\_100009
字典值如下：
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/YdgOk2b89JKL7q4B/img/2b17a7c9-da28-48ff-80ad-538b0cacb74d.png?Expires=1785910316&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=7LU9szhR2Axoh%2BoSyJr7%2FlrFfJA%3D "") | **需靖哥开发：**
生成订单时，自动生成
这个取值在哪里？
公共字典 |  |
| 订购类型(单选)：合同订单-合同订单交易类型（新订-\>新签、续订-\>续费、升版本续费-\>升级续费、降版本续费-\>降级续费、升级-\>升级(人数增加）) | 合同订单.订购类型
sale\_order\_select\_100010
字典值如下：
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/YdgOk2b89JKL7q4B/img/9676f102-8b9c-4d93-bbde-bf5e5b1aa4e7.png?Expires=1785910316&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=XevwE%2BoqeTzFw16rs8xOrf%2B7KNQ%3D "") | 需靖哥开发：
生成订单时，自动生成，选项判断逻辑参考 合同订单.合同订单交易类型 字段选项值
新订-\>新签
续订-\>续费
升版本续费-\>升级续费
降版本续费-\>降级续费
升级-\>升级(人数增加）
这个和上面的 sale\_order\_select\_100008 有什么不同？
逻辑一致 数据字典不一致 | OK |
| 订购版本 | 合同订单.订购版本
sale\_order\_select\_100007
字典值如下
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/YdgOk2b89JKL7q4B/img/0b4363b3-773c-4c14-a0b1-67853ca05434.png?Expires=1785910316&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=qxpWxTY5mj%2FQ0ID7g%2FrSTEwd1sw%3D "") | **需靖哥开发：**
生成订单时，自动生成--- 
数据字典取值 |  |
| 购买人数：取订单中的版本信息（订单中目前没有） | 合同订单.订购人数
sale\_order\_integer\_0 | **需靖哥开发：**
生成订单时，自动生成
sale\_order\_select\_100007 ？这个是数字字段还是select字段？
整数 |  |
| 购买时长套餐 | - |  |  |
| 购买时长(月数) | 0 |  |  |
| 是否有协作人 | 否 |  |  |
| 下单类型 | 甄选订单 |  |  |
| 合同编号 | - |  |  |
| 软件售卖版本金额(原价) | 0 |  |  |
| 软件版本金额(实收) | 0 |  |  |
| 软件折扣比例(折)自动计算 | - |  |  |
| 是否有实施费 | 否 |  |  |
| 是否有增值服务费 | 否 |  |  |
| 合同总额(自动计算) | 0 |  |  |
| 收款比例 | 智能财务的订单是25%
其他的是55% |  |  |
| 代理商分润金额 | - |  |  |
| 2年内业绩销售额 | 0 |  |  |
| 2-3内业绩销售额 | 0 |  |  |
| ＞3年业绩销售额 | 0 |  |  |
| 总业绩销售额 | 0 |  |  |
| 协作人（1）2年内业绩销售额 | 0 |  |  |
