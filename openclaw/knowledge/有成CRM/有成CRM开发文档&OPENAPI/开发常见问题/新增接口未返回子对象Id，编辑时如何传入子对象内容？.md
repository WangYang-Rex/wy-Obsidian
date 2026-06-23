---
type: knowledge
tags:
  - openclaw
  - 有成CRM
  - OPENAPI
  - 开发FAQ
created: 2026-06-23
source: 有成CRM官网帮助中心
original_url: https://www.ycbg.com/help-center.html?tab=1&id=641
exported_at: 2026-06-23
---

# 新增接口未返回子对象Id，编辑时如何传入子对象内容？

> **原文**：[新增接口未返回子对象Id，编辑时如何传入子对象内容？ - 有成CRM官网帮助中心](https://www.ycbg.com/help-center.html?tab=1&id=641)  
> **导出时间**：2026-06-23

**Q:新增接口未返回子对象Id，编辑时如何传入子对象内容？**

A：可通过查询接口，根据主对象id获取对应的子对象列表，

具体见：[开放业务对象数据列表](http://www.ycbg.com/help-center.html?tab=1&id=645)

请求示例（以产品查询产品明细为例）：

``` ql-syntax
{
    "corpAccessToken": "CORP_ACCESS_TOKEN",
    "corpId": "CORP_ID",
    "deployId": "product_particular",
    "conditionConfig": [
        {
            "conditions": [
                {
                    "comparison": "EQUAL",
                    "deployId": "product_particular",
                    "fieldName": "product_id",
                    "fieldTitle": "产品ID",
                    "fieldValue": "{新增接口返回的主产品Id}",
                    "domType": "INPUT"
                }
            ]
        }
    ],
    "page": 1,
    "pageSize": 200
}
```

---
> **相关：** [[有成CRM开发文档&OPENAPI/README|有成CRM OPENAPI 总览]]

