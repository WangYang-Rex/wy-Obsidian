---
title: "合同内回款/支付计划作为模版内sheet导入"
nodeId: YQBnd5ExVEwmpjMyigPAgyb68yeZqMmz
workspaceId: R2PmK2gngjVnZXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/YQBnd5ExVEwmpjMyigPAgyb68yeZqMmz?utm_scene=team_space"
updateTime: 1784021010000
exportedAt: 2026-07-16T11:10:52.621Z
source: dingtalk-document-mcp
---
版本：v1.0 \| 产品：有成报销v2.0 \| 客户：重庆顺泰生活服务

修订记录：v1.0(20260616)初始版本

---

## 一、需求背景

### 需求现状

用户在回款计划或支付计划中新增了自定义字段，在应付合同或应收合同下载导入模版后，模版内没有自定义的扩展字段导出

### 客户预期：

应收合同和应付合同导入模版支持自定义字段导入

---

## 二、功能清单

| 模块 | 功能点 | 备注 |
|------|---------|------|
| 合同管理-应收/应付合同导入模版 | 下载的导入模版包含收支付计划内的自定义字段且支持导入 |  |
| 导入模版 | 删除导入模版内原计划相关字段列 |  |

---

## 三、功能需求

### 3.1 合同内回款计划和支付计划作为应收合同导入模版内sheet栏导入

位置：合同管理 → 应收合同 → 导入模版下载

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/oJGq75kJevzaAlAK/img/d3a05c09-7116-47c0-b5b6-2a016eb8aa02.png?Expires=1784207453&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=QzyJ3cKo6I7Wn%2Bu3mf8IvmDV0dE%3D "")

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/oJGq75kJevzaAlAK/img/838befd0-37a4-4999-95f2-2def1c2d42fa.png?Expires=1784207453&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=%2FR8pu76PIG661JaEVZ4e5T2qwCs%3D "")

**功能描述：**
1. **删除原导入模版内“回款计划”和“支付计划”相关字段列“计划金额”“计划日期”“计划备注”**
2. 若该合同表单中包含回款计划组件或支付计划组件，则以组件名称在模板中新增sheet页。
    1. 各组件单独的sheet页中，最前面一列为必填的“单据序号”，后面各列为**子表单字段名称**，支持导入的子表单字段类型有：文本、数字、金额、下拉选项、项目、辅助核算、部门、日期、城市、同行人/员工、成本中心（同主表字段类型）。其中：
        1. 金额：金额币种填写币种编码，填写则默认为本位币；币种编码和金额之间用“\_”连接
        2. 下拉选项：按照文本内容匹配
        3. 项目：填写项目编码
        4. 辅助核算：填写辅助核算的编码
        5. 部门：填写部门的全路径，例如：xx测试集团/xx事业部/财务部
        6. 日期：格式为年/月/日；起止日期之间使用～连接；
        7. 城市：格式为省，市，区
        8. 同行人/员工：个人之间使用“，”号隔开，填写姓名
        9. 成本中心：填写成本中心编码
    2. 若回款计划或支付计划必填，且子表单组件中存在必填字段不在上述支持的子表单字段类型中，则限制该模板不支持导入，提示语“\[回款计划组件或支付计划组件名称\]存在暂不支持导入的必填字段\[必填字段名称\]”
    3. 导入时，回款计划或支付计划的数据按照单据序号匹配到合同主表中。若填写的单据序号在合同主表中找不到对应的单据序号，则本次导入全部失败，提示“\[回款计划组件或支付计划组件名称\]第\[x\]行数据找不到匹配的单据序号”
    4. **不支持“计划状态”和“合同发票”导入，导入的合同内计划的“计划状态”默认为未完成**
3. 导入合同弹框提示文案修改：11.支付/回款计划：再导入模版的sheet页中填写对应支付/回款计划的明细，能够支持的字段及格式要求同上。

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/oJGq75kJevzaAlAK/img/af0e71c5-aea8-4abc-82bb-218c0e796cf3.png?Expires=1784207453&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=0tJSKHPR8Mu9jfXsVX5kwY2hYtY%3D "")


