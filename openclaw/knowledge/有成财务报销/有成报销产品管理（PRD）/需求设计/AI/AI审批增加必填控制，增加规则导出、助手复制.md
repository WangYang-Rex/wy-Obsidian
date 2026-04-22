------
type: knowledge
tags:
  - 有成财务报销
  - PRD
  - AI审批
  - 必填控制
  - 规则导出
  - 助手复制
created: 2026-04-22
source: 钉钉知识库
original_url: https://alidocs.dingtalk.com/i/nodes/ZgpG2NdyVXrOqRxzHbYq1pGn8MwvDqPk?utm_scene=team_space
node_id: ZgpG2NdyVXrOqRxzHbYq1pGn8MwvDqPk
exported_at: 2026-04-22
---

# AI审批增加必填控制、规则导出、助手复制

> **原文链接**：[AI审批增加必填控制 - 钉钉知识库](https://alidocs.dingtalk.com/i/nodes/ZgpG2NdyVXrOqRxzHbYq1pGn8MwvDqPk?utm_scene=team_space)
> **导出时间**：2026-04-22 | **整理时间**：2026-04-22---
| 修订时间 | 版本 | 修订说明 |
|------------|------|------------|
| 20251219 | v1.0 | 新建 |
|  |  |  |

# **1\. 需求背景**

AI审批上线后，因系统发布或大模型问题，重试后依然可能存在AI审批节点卡住、超时的情况，此时需要人工介入干预。

原需求中的解决方案是让审批流的流程监督员进行干预，但因为创建审批流时大部分用户都没有设置流程监督员，还是可能卡住。

因此，比照之前自动开票“同步”节点，给AI审批节点也增加节点管理员。[自动开票（购买电票）](https://alidocs.dingtalk.com/i/nodes/oP0MALyR8k79kzMNhERBL1og83bzYmDO?utm_scene=team_space&iframeQuery=anchorId%3Duu_md79aq9f3eah8mclaan)


# **2\. 业务流程/架构**

# **3\. 功能清单**

| 模块 | 功能点 | 备注 |
|------|---------|------|
| 审批流 | 审批流，AI审批节点保存时增加审批流流程监督员必填校验。 |  |
| AI审批 | 审批助手支持复制 |  |
|  | 审批规则批量编辑细节优化 |  |
|  | 审批规则支持导出 |  |

# **4\. 需求详情**

## **审批流，AI审批节点保存时增加审批流流程监督员必填校验。**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/oJGq75kYQj6BylAK/img/2c1d3036-385d-4143-8834-f2b2bb31b973.png?Expires=1776848171&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=efnI%2FSyicpySwZ1glzk3IIFw77s%3D "")
1. AI审批节点增加超时设置，20分钟之后如果依然还在审批中，则处理为审批失败。
2. 审批流，AI审批节点保存时增加审批流流程监督员必填校验，“AI审批”

## **审批助手支持复制**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/oJGq75kYQj6BylAK/img/d9d8f6a7-3e81-4c89-b283-c333c1b7c878.png?Expires=1776848171&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=9IBE%2FK9zuQ6FYevzbmAOoxBPdHo%3D "")
1. AI审批助手列表，操作列增加“复制”，点击弹出复制AI审批助手弹框。其中：
- AI审批助手名称默认为空，需要用户输入。
- 审批详情数据权限默认带出原助手的审批详情数据权限，允许修改。
2. 点击保存，复制原助手的所有规则，新增一个助手。

## **审批规则批量编辑细节优化**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/oJGq75kYQj6BylAK/img/743815e1-27c8-45f3-8ba6-c12d4c8eeeb3.png?Expires=1776848171&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=zmHrkO7hkkvIi6NfBuvSDgcnVx0%3D "")
1. 去掉批量编辑审批规则中，适用单据和风险强度的必填。
2. 风险强度允许不选，默认不选。
3. 适用单据为空时，点击确定，不覆盖选中规则的适用单据；
4. 风险强度为空时，点击确定，不覆盖选中规则的风险强度。

## **审批规则支持导出**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/oJGq75kYQj6BylAK/img/78cacf9c-5c42-4530-93d2-7435ee5c11fe.png?Expires=1776848171&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=Mhki24vAvmT%2B3LbWZFc8N%2BF6kCU%3D "")

导出当前审批助手所有的审批规则。
- 模板名称：【AI审批助手名称】-审批规则.xls
- 模板字段：序号、适用单据、规则名称、具体规则、风险强度、问题定位（组件名称）
