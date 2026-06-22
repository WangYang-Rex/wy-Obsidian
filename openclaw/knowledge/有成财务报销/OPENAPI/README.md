---
tags:
  - 有成财务报销
  - OpenAPI
  - 接口文档
created: 2026-06-22
source: "/Users/wangyang/Downloads/报销OPAPI.md"
---

# 有成财务报销 OPEN API

> 对接时如有问题请对接相关商务，由商务负责协调技术人员解答。

## 环境地址

| 环境 | 域名 | 说明 |
|------|------|------|
| 测试环境 | `yiqbdatatest.superboss.cc` | 所有接口使用 HTTPS |
| 线上环境 | `yiqbdata.superboss.cc` | 所有接口使用 HTTPS |

## 接口总览

| # | 模块 | 接口数 | 详见 |
|---|------|--------|------|
| 1 | 对接授权 | 1 | [对接授权](对接授权.md) |
| 2 | 收款信息 | 1 | [收款信息](收款信息.md) |
| 3 | 预算开放接口 | 7 | [预算](预算.md) |
| 4 | 日记账 | 2 | [日记账](日记账.md) |
| 5 | 单据 | 8 | [单据](单据.md) |
| 6 | 公司账户/抬头 | 5 | [公司账户抬头](公司账户抬头.md) |
| 7 | 凭证 | 2 | [凭证](凭证.md) |
| 8 | 报销科目接入 | 3 | [报销科目接入](报销科目接入.md) |
| 9 | 用户信息 | 10 | [用户信息](用户信息.md) |
| 10 | 项目信息 | 4 | [项目信息](项目信息.md) |
| 11 | 收款信息（收款账户） | 2 | [收款账户](收款账户.md) |
| 12 | 组织架构（部门）信息 | 2 | [组织架构](组织架构.md) |
| 13 | 成本中心 | 1 | [成本中心](成本中心.md) |
| 14 | 辅助核算（表单） | 5 | [辅助核算表单](辅助核算表单.md) |
| 15 | 报销基础数据 | 2 | [报销基础数据](报销基础数据.md) |
| 16 | 辅助核算 | 7 | [辅助核算](辅助核算.md) |
| 17 | 发票 | 1 | [发票](发票.md) |
| 18 | 资金明细开放接口 | 1 | [资金明细](资金明细.md) |

**合计：17 个模块，63 个接口**

## 各模块接口明细

### 1. 对接授权
| 接口 | 方法 | 路径 |
|------|------|------|
| 免登授权，获取 accessToken | POST | `/auth/getAccessToken.rjson` |

### 2. 收款信息
| 接口 | 方法 | 路径 |
|------|------|------|
| 获取收款信息 | POST | `/reimburse/base/getBankCardInfoList.rjson` |

### 3. 预算开放接口
| 接口 | 方法 | 路径 |
|------|------|------|
| 获取预算列表 | GET | `/reimburse/budget/list.rjson` |
| 获取预算详情 | POST | `/reimburse/budget/detail.rjson` |
| 预算调整表（平铺） | POST | `/reimburse/budget/getAdjustReportList.rjson` |
| 根据单号获取预算占用详情 | POST | `/reimburse/ysfk/budget/queryOccupyResultByOrderCode.rjson` |
| 获取预算基本信息（管理员） | POST | `/reimburse/ysfk/budget/getBaseInfoListByAdmin.rjson` |
| 获取预算周期信息 | POST | `/reimburse/ysfk/budget/getCycleRanks.rjson` |
| 获取单据预算占用状态 | POST | `/reimburse/ysfk/budget/queryOrderOccupyStatus.rjson` |

### 4. 日记账
| 接口 | 方法 | 路径 |
|------|------|------|
| 日记账查询 | POST | `/reimburse/journal/queryListPage.rjson` |
| 日记账回调 | POST | `/reimburse/journal/callback.rjson` |

### 5. 单据
| 接口 | 方法 | 路径 |
|------|------|------|
| 生成单据（推送） | POST | `/reimburse/order/createOrder.rjson` |
| 获取推送结果 | POST | `/reimburse/order/getPushResult.rjson` |
| 获取审批结果 | POST | `/reimburse/order/getApproveResult.rjson` |
| 获取借款单待还款金额 | POST | `/reimburse/order/getRemainAmount.rjson` |
| 获取单据列表 | POST | `/reimburse/order/getOrderList.rjson` |
| 待支付单据回调 | POST | `/reimburse/order/payCallback.rjson` |
| 获取单据状态列表 | POST | `/reimburse/order/getOrderStatusList.rjson` |
| 查询关联单据 | POST | `/reimburse/order/findOrderRelation.rjson` |

### 6. 公司账户/抬头
| 接口 | 方法 | 路径 |
|------|------|------|
| 获取支付账户信息列表 | POST | `/reimburse/corp/payAccount/findPayAccountList.rjson` |
| 新增支付账户信息 | POST | `/reimburse/corp/payAccount/addPayAccount.rjson` |
| 删除支付账户信息 | POST | `/reimburse/corp/payAccount/deleteBatch.rjson` |
| 新增发票抬头 | POST | `/reimburse/corp/invoice/addOrUpdateInvoiceTitle.rjson` |
| 获取发票抬头列表 | POST | `/reimburse/corp/invoice/getInvoiceTitleList.rjson` |

### 7. 凭证
| 接口 | 方法 | 路径 |
|------|------|------|
| 凭证查询 | POST | `/reimburse/certificate/queryListPage.rjson` |
| 凭证回调 | POST | `/reimburse/certificate/callback.rjson` |

### 8. 报销科目接入
| 接口 | 方法 | 路径 |
|------|------|------|
| 新增科目 | POST | `/reimburse/subject/add.rjson` |
| 修改科目 | POST | `/reimburse/subject/update.rjson` |
| 删除科目 | POST | `/reimburse/subject/delete.rjson` |

### 9. 用户信息
| 接口 | 方法 | 路径 |
|------|------|------|
| 获取用户列表 | POST | `/reimburse/user/getUserList.rjson` |
| 批量新增/更新企业人员 | POST | `/reimburse/user/batchAddOrUpdateUser.rjson` |
| 新增角色 | POST | `/reimburse/role/add.rjson` |
| 查询角色 | POST | `/reimburse/role/query.rjson` |
| 查询角色分组 | POST | `/reimburse/roleGroup/query.rjson` |
| 更新角色 | POST | `/reimburse/role/update.rjson` |
| 查询用户角色列表 | POST | `/reimburse/userRole/queryList.rjson` |
| 批量新增企业人员与角色关系 | POST | `/reimburse/userRole/batchAdd.rjson` |
| 批量更新企业人员与角色关系 | POST | `/reimburse/userRole/batchUpdate.rjson` |
| 新增/修改角色组 | POST | `/reimburse/roleGroup/addOrUpdate.rjson` |

### 10. 项目信息
| 接口 | 方法 | 路径 |
|------|------|------|
| 获取项目信息 | POST | `/reimburse/ysfk/project/getProjectList.rjson` |
| 批量删除项目单据 | POST | `/reimburse/ysfk/project/batchDeleteProject.rjson` |
| 推送项目单据 | POST | `/reimburse/ysfk/project/pushProject.rjson` |
| 根据项目获取项目报表 | POST | `/reimburse/ysfk/project/getProjectReport.rjson` |

### 11. 收款信息（收款账户）
| 接口 | 方法 | 路径 |
|------|------|------|
| 获取收款信息 | POST | `/reimburse/corp/receiptAccount/findReceiptAccountList.rjson` |
| 新增收款信息 | POST | `/reimburse/corp/receiptAccount/addReceiptAccount.rjson` |

### 12. 组织架构（部门）信息
| 接口 | 方法 | 路径 |
|------|------|------|
| 获取部门列表 | POST | `/reimburse/dept/getDeptList.rjson` |
| 批量新增/更新组织架构 | POST | `/reimburse/dept/batchAddOrUpdateDept.rjson` |

### 13. 成本中心
| 接口 | 方法 | 路径 |
|------|------|------|
| 查询成本中心列表 | POST | `/reimburse/costCenter/getList.rjson` |

### 14. 辅助核算（表单）
| 接口 | 方法 | 路径 |
|------|------|------|
| 辅助核算模版 | POST | `/reimburse/ysfk/auxiliaryItem/getTemplateList.rjson` |
| 新增辅助核算 | POST | `/reimburse/ysfk/auxiliaryItem/add.rjson` |
| 辅助核算详情 | POST | `/reimburse/ysfk/auxiliaryItem/detail.rjson` |
| 修改辅助核算 | POST | `/reimburse/ysfk/auxiliaryItem/update.rjson` |
| 获取辅助核算标签 | POST | `/reimburse/ysfk/auxiliaryItem/getTagList.rjson` |

### 15. 报销基础数据
| 接口 | 方法 | 路径 |
|------|------|------|
| 拉取单据/费用模板 | POST | `/reimburse/template/getTemplateList.rjson` |
| 拉取单据/费用模板（树形） | POST | `/reimburse/template/getTemplateTree.rjson` |

### 16. 辅助核算
| 接口 | 方法 | 路径 |
|------|------|------|
| 新增辅助类别 | POST | `/reimburse/ysfk/auxiliaryCategory/add.rjson` |
| 修改辅助类别 | POST | `/reimburse/ysfk/auxiliaryCategory/update.rjson` |
| 新增选项 | POST | `/reimburse/ysfk/auxiliaryItem/add.rjson` |
| 查询选项 | POST | `/reimburse/ysfk/auxiliaryItem/queryList.rjson` |
| 修改辅助选项 | POST | `/reimburse/ysfk/auxiliaryItem/update.rjson` |
| 获取辅助核算列表 | POST | `/reimburse/ysfk/auxiliaryCategory/queryList.rjson` |
| 根据映射id获取辅助核算项目 | POST | `/reimburse/ysfk/auxiliaryMapping/getItemByMappingId.rjson` |

### 17. 发票
| 接口 | 方法 | 路径 |
|------|------|------|
| 获取发票列表 | POST | `/reimburse/invoice/getInvoiceList.rjson` |

### 18. 资金明细开放接口
| 接口 | 方法 | 路径 |
|------|------|------|
| 资金明细列表 | POST | `/reimburse/fundDetail/getList.rjson` |

## 公共说明

### 认证方式

所有接口（除获取 Token 外）均需在 URL 中携带 `appKey` 和 `accessToken` 参数：

```
POST https://yiqbdata.superboss.cc/reimburse/xxx.rjson?appKey=xxx&accessToken=xxxx
```

### ContentType

大部分接口使用 `application/json; charset=utf-8`，少数 GET 接口使用 `application/x-www-form-urlencoded`，详见各接口文档。

### 公共错误码

所有接口共享以下错误码体系：

| 错误码 | 含义 | 说明 |
|--------|------|------|
| 100 | 调用成功 | 1xx 统一表示成功 |
| 110 | 预算超标 | 特殊业务码 |
| 200 | 请求参数异常 | 2xx 统一表示参数异常 |
| 201 | 对象转换异常 | |
| 202 | 接口请求参数类型不匹配 | |
| 300 | 服务运行时异常 | 3xx 统一表示程序运行时异常 |
| 302 | 未查询到数据 | |
| 304 | 数据重复 | |
| 311 | 服务未知异常 | |
| 312 | dubbo 服务异常 | |
| 313 | 前端传入参数异常 | |
| 314-317 | 数据库操作异常 | 查询/新增/修改/删除 |
| 322 | 请求参数异常 | |
| 400 | 系统内部异常 | 4xx 统一表示程序内部错误 |
| 500 | 远程调用异常 | 5xx 统一表示内部服务调用失败 |
| 600 | 请求淘宝 API 异常 | 6xx 统一表示第三方服务调用失败 |
| 601 | API 接口调用已知错误 | |
| 700 | Token 过期 | 7xx 统一表示权限错误 |
| 701 | Session 过期 | |
| 702 | Session 获取用户失败 | |
| 703 | 认证异常 | |
| 704 | 短授权异常 | |
| 705 | 权限受限 | |
| 706 | 用户权限不够 | |
| 707 | 停机维护 | |
| 708 | 用户不在钉钉授权范围内 | |
| 709 | 当前版本需要升级 | |
| 710 | 前端需展示提示信息 | |
| 750 | 异步导出统一返回码 | |
| 800 | JVM down | 8xx 统一表示程序异常 |

---
*整理自报销 OPEN API 文档，最后更新：2026-06-22*
