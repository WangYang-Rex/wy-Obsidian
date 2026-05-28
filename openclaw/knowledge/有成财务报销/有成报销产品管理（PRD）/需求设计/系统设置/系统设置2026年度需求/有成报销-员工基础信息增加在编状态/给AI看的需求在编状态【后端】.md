---
title: "给AI看的需求在编状态【后端】"
nodeId: r1R7q3QmWe7M9wKYhXybGoOpJxkXOEP2
workspaceId: R2PmK2gngjVnZXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/r1R7q3QmWe7M9wKYhXybGoOpJxkXOEP2?utm_scene=team_space"
updateTime: 1776048316000
exportedAt: 2026-05-14T12:11:54.767Z
source: dingtalk-document-mcp
---
## **1\. 需求**

## **1.1 需求背景**

员工基本信息增加是否在编字段；



### **1.2 需求描述**

在员工基础信息中新增"在编状态"字段（编内/编外）。第三方系统需要通过openApi接口获取和推送员工的【在编状态】字段



---

## **2\. 本次需求功能点**

### **3.1 功能点清单**

| **变更类型** | **功能点** | **功能说明** | **优先级** |
|----------------------------------------------------------------|-------------------------------------------------------------|----------------------------------------------------------------|-------------------------------------------------------------|
| 新增 | 员工基础信息字段扩展 | 员工信息新增"在编状态"字段（空/编内/编外） | P1 |
| 新增 | 查看员工基础信息字段详情 | 员工信息展示新增"在编状态"字段（空/编内/编外） | P1 |
| 新增 | 员工信息导入导出扩展 | 员工导入/导出Excel增加"在编状态"列 | P1 |
| 新增 | openApi兼容在编状态字段 | <ul><li>1. 获取用户列表接口（https://yiqbdata.superboss.cc/reimburse/user/getUserList.rjson）</li><br><li>2. 批量新增\\更新企业人员接口（https://yiqbdata.superboss.cc/reimburse/user/mutil/save.rjson）</li></ul> | P1 |

### **3.2 详细功能描述**

#### **3.2.1 员工基础信息增加在编状态字段**

**位置**：基础设置 → 员工管理 → 员工信息 → 新增/编辑员工

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbw3Rew0qXx/img/3ae0bb8b-7c66-4368-b997-00ac3148f2fd.png?Expires=1778767378&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=FnYYclJwYGzd9Cq9MqxRgmkQ8wc%3D "")![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbw3Rew0qXx/img/1f089c06-f6ec-4ba0-b00a-2308d9bc6842.png?Expires=1778767378&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=jQTICfFT1GKvm9DsZYORVu0LfV4%3D "")

后端接口地址：

新增/修改：/corp/user/save.rjson

**界面调整**

在"基础信息"区域增加"在编状态"字段：
```plain
基础信息
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
* 姓名          [输入框]
  工号          [输入框]
  手机号        [输入框]
  邮箱          [输入框]
  角色          [下拉选择]
  直属上级      [下拉选择]
  常驻地        [输入框]
  在编状态      [下拉组件▼]  ← 新增字段
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

**字段定义**

| **属性** | **值** |
|----------------------------------------------------------|-------------------------------------------------------|
| 字段名 | 在编状态 |
| 数据类型 | 枚举（单选） |
| 可选项 | 编内、编外 |
| 默认值 | 空（NULL） |
| 必填 | 否 |

#### **3.2.2 员工信息导入导出增加在编状态**

**1.导入模板**

在导入模版中增加"在编状态"列，位置放在最后。

下载导入模版接口：

corp/user/import-template.rjson

参数：

Content-Disposition: form-data; name="templateName"

batchStaff

**数据校验**
- 导入时若填写值不在枚举范围内，提示"在编状态填写错误，请填写'编内'或'编外'"
- 为空时保持为空，不自动填充



**2.导出Excel**

在导出文件中增加"在编状态"列，位置放在最后。

导出员工接口：

/sys/permission/report/exportEmpInfoList.rjson



#### **3.2.4 公有成报销api接口【获取用户列表】和【批量新增/更新企业人员】增加【在编状态】字段**
1. 获取用户列表接口（https://yiqbdata.superboss.cc/reimburse/user/getUserList.rjson）
2. 批量新增\\更新企业人员接口（https://yiqbdata.superboss.cc/reimburse/user/mutil/save.rjson）




