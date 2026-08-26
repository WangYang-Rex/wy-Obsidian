---
title: "给AI看的需求在编状态【后端】"
nodeId: r1R7q3QmWe7M9wKYhXybGoOpJxkXOEP2
workspaceId: R2PmK2gngjVnZXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/r1R7q3QmWe7M9wKYhXybGoOpJxkXOEP2?utm_scene=team_space"
updateTime: 1776048316000
exportedAt: 2026-08-05T04:29:31.392Z
source: dingtalk-document-mcp
---
## <span style="color: rgba(0, 0, 0, 0.9);">**1\. 需求**</span>

## **1.1 需求背景**

<span style="color: rgba(0, 0, 0, 0.9);">员工基本信息增加是否在编字段；</span>



### <span style="color: rgba(0, 0, 0, 0.9);">**1.2 需求描述**</span>

<span style="color: rgba(0, 0, 0, 0.9);">在员工基础信息中新增"在编状态"字段（编内/编外）。</span><span style="color: rgba(0, 0, 0, 0.9);">第三方系统需要通过openApi接口获取和推送员工的【在编状态】字段</span>



---

## <span style="color: rgba(0, 0, 0, 0.9);">**2\. 本次需求功能点**</span>

### <span style="color: rgba(0, 0, 0, 0.9);">**3.1 功能点清单**</span>

| <span style="color: rgba(0, 0, 0, 0.9);">**变更类型**</span> | <span style="color: rgba(0, 0, 0, 0.9);">**功能点**</span> | <span style="color: rgba(0, 0, 0, 0.9);">**功能说明**</span> | <span style="color: rgba(0, 0, 0, 0.9);">**优先级**</span> |
|----------------------------------------------------------------|-------------------------------------------------------------|----------------------------------------------------------------|-------------------------------------------------------------|
| <span style="color: rgba(0, 0, 0, 0.9);">新增</span> | <span style="color: rgba(0, 0, 0, 0.9);">员工基础信息字段扩展</span> | <span style="color: rgba(0, 0, 0, 0.9);">员工信息新增"在编状态"字段（空/编内/编外）</span> | <span style="color: rgba(0, 0, 0, 0.9);">P1</span> |
| <span style="color: rgba(0, 0, 0, 0.9);">新增</span> | <span style="color: rgba(0, 0, 0, 0.9);">查看员工基础信息字段详情</span> | <span style="color: rgba(0, 0, 0, 0.9);">员工信息展示新增"在编状态"字段（空/编内/编外）</span> | <span style="color: rgba(0, 0, 0, 0.9);">P1</span> |
| <span style="color: rgba(0, 0, 0, 0.9);">新增</span> | <span style="color: rgba(0, 0, 0, 0.9);">员工信息导入导出扩展</span> | <span style="color: rgba(0, 0, 0, 0.9);">员工导入/导出Excel增加"在编状态"列</span> | <span style="color: rgba(0, 0, 0, 0.9);">P1</span> |
| 新增 | openApi兼容在编状态字段 | <ul><li>1. 获取用户列表接口（https://yiqbdata.superboss.cc/reimburse/user/getUserList.rjson）</li><br><li>2. 批量新增\\更新企业人员接口（https://yiqbdata.superboss.cc/reimburse/user/mutil/save.rjson）</li></ul> | <span style="color: rgba(0, 0, 0, 0.9);">P1</span> |

### <span style="color: rgba(0, 0, 0, 0.9);">**3.2 详细功能描述**</span>

#### <span style="color: rgba(0, 0, 0, 0.9);">**3.2.1 员工基础信息增加在编状态字段**</span>

<span style="color: rgba(0, 0, 0, 0.9);">**位置**</span><span style="color: rgba(0, 0, 0, 0.9);">：基础设置 → 员工管理 → 员工信息 → 新增/编辑员工</span>

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbw3Rew0qXx/img/3ae0bb8b-7c66-4368-b997-00ac3148f2fd.png?Expires=1785911261&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=Hj%2F3LgUnmaMVX%2BOxLsbpjjRz5Wo%3D "")![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbw3Rew0qXx/img/1f089c06-f6ec-4ba0-b00a-2308d9bc6842.png?Expires=1785911261&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=hkD4m99ri8jT8rg7kcG3W%2FCwBxA%3D "")

<span style="color: rgba(0, 0, 0, 0.9);">后端接口地址：</span>

<span style="color: rgba(0, 0, 0, 0.9);">新增/修改：/corp/user/save.rjson</span>

<span style="color: rgba(0, 0, 0, 0.9);">**界面调整**</span>

<span style="color: rgba(0, 0, 0, 0.9);">在"基础信息"区域增加"在编状态"字段：</span>
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

<span style="color: rgba(0, 0, 0, 0.9);">**字段定义**</span>

| <span style="color: rgba(0, 0, 0, 0.9);">**属性**</span> | <span style="color: rgba(0, 0, 0, 0.9);">**值**</span> |
|----------------------------------------------------------|-------------------------------------------------------|
| <span style="color: rgba(0, 0, 0, 0.9);">字段名</span> | <span style="color: rgba(0, 0, 0, 0.9);">在编状态</span> |
| <span style="color: rgba(0, 0, 0, 0.9);">数据类型</span> | <span style="color: rgba(0, 0, 0, 0.9);">枚举（单选）</span> |
| <span style="color: rgba(0, 0, 0, 0.9);">可选项</span> | <span style="color: rgba(0, 0, 0, 0.9);">编内、编外</span> |
| <span style="color: rgba(0, 0, 0, 0.9);">默认值</span> | <span style="color: rgba(0, 0, 0, 0.9);">空（NULL）</span> |
| <span style="color: rgba(0, 0, 0, 0.9);">必填</span> | <span style="color: rgba(0, 0, 0, 0.9);">否</span> |

#### <span style="color: rgba(0, 0, 0, 0.9);">**3.2.2 员工信息导入导出增加在编状态**</span>

<span style="color: rgba(0, 0, 0, 0.9);">**1.导入模板**</span>

<span style="color: rgba(0, 0, 0, 0.9);">在导入模版中增加"在编状态"列，位置放在最后。</span>

<span style="color: rgba(0, 0, 0, 0.9);">下载导入模版接口：</span>

<span style="color: rgba(0, 0, 0, 0.9);">corp/user/import-template.rjson</span>

<span style="color: rgba(0, 0, 0, 0.9);">参数：</span>

<span style="color: rgba(0, 0, 0, 0.9);">Content-Disposition: form-data; name="templateName"</span>

<span style="color: rgba(0, 0, 0, 0.9);">batchStaff</span>

<span style="color: rgba(0, 0, 0, 0.9);">**数据校验**</span>
- <span style="color: rgba(0, 0, 0, 0.9);">导入时若填写值不在枚举范围内，提示"在编状态填写错误，请填写'编内'或'编外'"</span>
- <span style="color: rgba(0, 0, 0, 0.9);">为空时保持为空，不自动填充</span>



<span style="color: rgba(0, 0, 0, 0.9);">**2.导出Excel**</span>

<span style="color: rgba(0, 0, 0, 0.9);">在导出文件中增加"在编状态"列，位置放在最后。</span>

<span style="color: rgba(0, 0, 0, 0.9);">导出员工接口：</span>

<span style="color: rgba(0, 0, 0, 0.9);">/sys/permission/report/exportEmpInfoList.rjson</span>



#### <span style="color: rgba(0, 0, 0, 0.9);">**3.2.4 公有成报销api接口【获取用户列表】和【批量新增/更新企业人员】增加【在编状态】字段**</span>
1. 获取用户列表接口（https://yiqbdata.superboss.cc/reimburse/user/getUserList.rjson）
2. 批量新增\\更新企业人员接口（https://yiqbdata.superboss.cc/reimburse/user/mutil/save.rjson）




