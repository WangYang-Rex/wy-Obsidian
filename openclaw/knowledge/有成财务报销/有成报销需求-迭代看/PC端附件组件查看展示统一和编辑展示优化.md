---
title: " PC端附件组件查看展示统一和编辑展示优化"
nodeId: R1zknDm0WR3ey6R2TxNraaDkVBQEx5rG
workspaceId: R2PmK2gngjVnZXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/R1zknDm0WR3ey6R2TxNraaDkVBQEx5rG?utm_scene=team_space"
updateTime: 1779085967000
exportedAt: 2026-05-28T11:32:58.771Z
source: dingtalk-document-mcp
---
> **版本**：v1.0 \| **产品**：有成报销v2.0 \| **客户**：天津纽莱克进出口有限公司，沈阳市公安局大东分局   **修订记录**：v1.0(20260511)初始版本   

---

# **需求背景**

## **需求现状：**

  PC端附件查看展示效果不统一，企业客户无法查看附件时进行上一张/下一张操作对附件进行切换查看；客户希望查看附件和编辑附件时能尽量更清晰的看到附件内容；

##   **客户预期**

  企业希望查看附件详情时可快速上一张/下一张切换查看附件详情；企业客户希望可以自行展示收缩附件字段信息；



# **功能清单**

| 模块 | 功能点 | 备注 |
|------|---------|------|
| 查看附件详情 | 所有附件格式的文件查看附件详情展示页面统一 |  |
| 查看附件详情-切换查看 | 支持上一张/下一张切换查看 |  |
| 查看附件详情/编辑附件详情-展开收起 | 支持用户展示收起右侧字段区 |  |

# **需求详情**

## 查看附件详情-收起/展开

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ZWGl05mxaXw4Bn34/img/d6b30651-f6a1-4481-8031-2b87a3a20731.png?Expires=1779975179&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=47f%2FPf6zDF7d2oXja4JG4B89Onw%3D "")



![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ZWGl05mxaXw4Bn34/img/9e4e4f95-720b-4e75-9ab4-a300cedb7b58.png?Expires=1779975179&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=QtgrLuWruY6URhwDMKomjqD5yqk%3D "")

查看模式下：上一张下一张按钮固定在左侧底端，设计图已修改

**收起展开按钮说明**：
- 位置：预览区右上角，在【浏览器打开】按钮上方
- 提醒：编辑状态下右上角带红点提醒（表示该附件字段区有ai识别结果，提醒用户可展开查看）
- 点击后：右侧字段区滑出展开，预览区宽度自适应缩小
- 再次点击：字段区收起，预览区恢复占满状态

**默认状态**：
- **查看模式**：打开弹窗时，右侧字段区**默认收起**，预览区占满可用宽度



## 编辑附件详情-收起/展开

**默认收起**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ZWGl05mxaXw4Bn34/img/372200d7-32e9-4ef3-8166-3d5e8ea5bb90.png?Expires=1779975179&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=N%2Bf6KxjuK2TP2MDLHoEMcvgTXfE%3D "")

**收起展开按钮说明**：
- 位置：同查看附件详情
- 提醒：编辑状态下右上角带红点提醒（表示该附件字段区有ai识别结果，提醒用户可展开查看）
- 点击后：同查看附件详情
- 再次点击：同查看附件详情

**默认状态**：
- **编辑模式**：打开弹窗时，右侧字段区**默认收起**，预览区占满可用宽度



### **附件切换规则：上一张 / 下一张**
- 仅查看附件有该功能
- 按附件在单据中的排列顺序切换
- 当前为第一个附件时，「上一张」按钮**置灰不可点**
- 当前为最后一个附件时，「下一张」按钮**置灰不可点**
- 所有附件类型均支持切换（图片、PDF、Word、Excel 等）



### **附件格式不支持预览的文件-查看/编辑：**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ZWGl05mxaXw4Bn34/img/937c0d01-a8de-4c20-afae-78e418fe3070.png?Expires=1779975179&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=MUbBYtui8O89%2BJCK32F7b97wSho%3D "")

查看附件

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ZWGl05mxaXw4Bn34/img/a6216e9a-15d6-4c95-a1a3-8399884afac1.png?Expires=1779975179&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=fdFfoM4tglywIGWLCjVe%2FZqGa3g%3D "")

编辑附件

**不支持预览的附件**：
- Word、Excel 、zip等不支持直接预览的附件，切换后显示「暂不支持预览，请点击此处按钮查看」
- 不支持预览的附件同样支持上一张/下一张切换，不跳过
