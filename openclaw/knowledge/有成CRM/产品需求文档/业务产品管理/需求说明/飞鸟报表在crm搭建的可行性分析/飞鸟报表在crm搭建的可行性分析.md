---
title: "飞鸟报表在crm搭建的可行性分析"
tags:
  - 有成CRM
  - PRD
  - 业务产品管理-需求说�
created: 2026-03-24
source: 钉钉文档
original_url: https://alidocs.dingtalk.com/i/nodes/QG53mjyd80Rjq0QOCdpkoDo2V6zbX04v?utm_scene=team_space
node_id: QG53mjyd80Rjq0QOCdpkoDo2V6zbX04v
exported_at: 2026-03-22
---

# 飞鸟报表在crm搭建的可行性分析

> 🔗 **原文链接**：[飞鸟报表在crm搭建的可行性分析 - 钉钉文档](https://alidocs.dingtalk.com/i/nodes/QG53mjyd80Rjq0QOCdpkoDo2V6zbX04v?utm_scene=team_space)

# 飞鸟报表在crm搭建的可行性分析

# 一、对报销数据的理解
- 系统信息（直接按照id匹配，不考虑独立端、crm侧自定义架构的场景）组织架构：不支持自定义，直接同步平台架构人员：同步平台人员
- 基础资料（在crm侧生成对象，其中不同类别的辅助核算生成多个对象）费用类别-父类别辅助核算类别-辅助核算-父类别公司账户收款账户抬头
- 单据（不同的单据=crm中同一对象不同模板）对象（在crm侧生成8个对象，不同单据不同模板，主单据中可以冗余增加子表单，用于后续表单穿透查看表单详情）主单据子表单-核销借款子表单-费用明细子表单-分摊明细（关联费用明细）子表单-关联单据（可关联不同单据类型，相当于指定关联对象）子表单-行程子表单-产品明细子表单---付款计划子表单-表格关联对象收款信息公司账户发票抬头发票项目辅助核算成本中心（系统预设）？

# 二、对飞鸟报表需求的理解


![Picture 1](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/3BMqYybNVkR4dqwZ/img/8b205c34-3b83-4fb2-bca1-53939aa01590.png?Expires=1774164934&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=IqTYEJ1Rjak1GIvHBEy11BkU68A%3D "")


![Picture 2](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/3BMqYybNVkR4dqwZ/img/e7deb478-3297-413c-9dc2-ba56fc6f841d.png?Expires=1774164934&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=%2FRJZrdFzMO4HkG2C2PN75X0iy0E%3D "")

## 1、统计维度
- 日期：每种单据，取的日期不一样，有些是单据创建时间、有的是支付时间（如报销单）
- 辅助核算：区分辅助核算类型、可能会有多个（会不止2级）
- 项目
- 项目状态
- 项目状态
- 费用类型-下级类型（会不止2级）（收入/成本和费用是不同的，见后续指标描述）
- 负责人：报销中是申请人
- 部门
- 合同订单
- 审批状态：审批中/已完成的状态需要单独统计，待提交/已拒绝的状态不需要计入

## 2、统计指标

统计的字段（金额），暂不考虑自定义字段
- 收入合同收入：报销中 \{单据类型\}=‘合同’and \{支付类型\}=‘应收合同’的单据 ∑ \{金额\}

（或取crm中【合同订单】的 \{合同订单金额\}）

\- 开票金额：报销【发票】的 \{金额\}（当前发票中要增加应收发票类型）

（或取crm中【开票申请】的 \{开票金额\}）

\- 实际收入：报销 \{单据类型\}=‘收款’的单据 \∑\</span\> \{金额\}\- 实际（内部）/实际（外部）=实际收入\*公式（自己定义的公式）\- 实际收入小计：=实际收入
- 支出监管员成本/研发成本/其他成本：报销 \{单据类型\}=‘合同’and \{支付类型\}=‘应付合同’的单据 ∑ \{金额\}不同类型的成本：根据自定义下拉选框区分或者单据中关联费用明细
- 税金及附加上述计算得出的某个值*7.3%*其他加减乘除运算
- 费用所有单据类型（除项目外其他6种类型） 费用明细组件（子表单）中 对应费用明细 ∑ \{金额\}会存在分摊的情况，即上述信息会存在费用明细中的 费用分摊（子表单）中,费用统计优先取 分摊明细--\>费用明细--\>主单据


![Picture 3](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/3BMqYybNVkR4dqwZ/img/1ca8466d-1362-44a3-83d4-832ec3eecd0e.png?Expires=1774164934&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=A7%2FGMmUpnCXPkzlcPGDZa98SU%2B8%3D "")

举例：

\* 项目1  部门1  200元\* 项目1  部门1  100元\+ 项目1  部门1  50元\+ 项目2  部门1  20元\+ 项目1  部门2  20元\+ 项目2  部门2  10元\* 结果\+ 项目1  部门1  250元\+ 项目2  部门1  20元\+ 项目1  部门2  20元\+ 项目2  部门2  10元
- 其他：业绩提成及巴长绩效/毛利等，都是通过计算得出的某个值\*其他加减乘除运算

## 3、其他要求
- 统计指标都需要穿透
- 明细表：需要展示【项目】\+项目下所有【费用明细】字段

# 三、crm现有能力简介

# 四、解决方案及要求

需要迭代：人员/部门控件

| **方案** |  | **分析** |
|----------|---|----------|
| 收入&成本 与费用合并展示 | 以【项目】/【核算维度】为分析对象 | \+ 好处- 利润等计算有可能实现（通过计算指标）- 不同单据不同统计日期字段可以实现\+ 问题- 因为项目中并没有科目、辅助核算、人员、部门、审批状态等维度，要展示的话就需要根据所需维度建非常多指标，维护成本很大- 目前一张报表里面最多12个指标，其中最多3个计算指标，按照需求远超这个数量，放开数量限制会导致查询超时- 计算指标中能够插入的字段也有限，维护起来工作量也很大- 科目关联的上级/上上级...科目无法展示/小计- ~~费用统计结果会不准~~\* ~~有取数判断逻辑：单据中最终费用金额取数顺序 分摊费用--\>费用明细---\>主单据~~ |
|  | 以【费用类别】为分析对象 | \+ 好处- 利润等计算有可能实现（通过计算指标）- 不同单据不同统计日期字段可以实现\+ 问题- 收入合同等中没有关联【费用类别】字段，故需要企业在维护合同等信息时，填写关联的费用类别- 同样是维度中没有项目、辅助核算、人员、部门、审批状态等信息，维护指标的数量会比以【项目】为分析对象少一个维度- 指标数量限制、多级科目、统计结果准确性问题同上 |
| 收入&成本 与费用分开展示（敲定方案） |  | \+ 方案- 收入&成本：通过【项目】或者其他维度为分析对象，建指标统计- 费用：通过【费用明细】为分析对象\+ 好处- 指标维护工作减少\+ 问题- 不满足用户需求- 需要做数据加工：收入等同步生成费用明细- 利润等计算无法实现：逻辑函数需要能取维度信息？？？- 费比等无法实现- 费用：不确定费用明细中是否包含所有企业所需要分析的维度/统计字段，灵活性及扩展性差- 费用：多级科目问题同前- ~~费用：统计结果不准确（无法剔除分摊费用、主单据费用）~~ |

![Picture 4](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/3BMqYybNVkR4dqwZ/img/2f18cee4-b4a9-4c13-b92d-69f86c979c08.png?Expires=1774164934&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=Faf8jgAIRZ0UN99wsTcCI8Ydiws%3D "")

![Picture 5](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/3BMqYybNVkR4dqwZ/img/cf794cda-f9e4-43cb-a803-8e4e8b148117.png?Expires=1774164934&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=1G3JfktsB%2B3fYRmItT0aw49MhYA%3D "")

![Picture 6](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/3BMqYybNVkR4dqwZ/img/f7cd3a6e-f1af-4222-8d22-c9ba0f23d2a7.png?Expires=1774164934&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=kQmdQRjHgd%2FuZv3aPpBv7Dy5br8%3D "")

![Picture 7](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/3BMqYybNVkR4dqwZ/img/a934eee7-ea42-4a35-9763-e8079cebfe37.png?Expires=1774164934&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=v%2FoO4wgnoqtUqXA3TrAANZIEwco%3D "")
