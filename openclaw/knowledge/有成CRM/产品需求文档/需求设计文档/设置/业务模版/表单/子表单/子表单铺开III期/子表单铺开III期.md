---
title: "子表单铺开III期"
tags:
  - 有成CRM
  - PRD
  - 需求设计文档-设置-业�
created: 2026-03-24
source: 钉钉文档
original_url: https://alidocs.dingtalk.com/i/nodes/mExel2BLV54XG9QpCE5Zk5pQWgk9rpMq?utm_scene=team_space
node_id: mExel2BLV54XG9QpCE5Zk5pQWgk9rpMq
exported_at: 2026-03-22
---

# 子表单铺开III期

> 🔗 **原文链接**：[子表单铺开III期 - 钉钉文档](https://alidocs.dingtalk.com/i/nodes/mExel2BLV54XG9QpCE5Zk5pQWgk9rpMq?utm_scene=team_space)

# 子表单铺开III期

| **修订时间** | **版本** | **修订人** | **修订说明** |
|----------------|----------|-------------|----------------|
| 20230726 | v1.0 | 黄艺平 | 新建 |

## 1、供应商（已上线）

自定义关联对象、子表单及数据联动铺开需求：供应商名称、备注字段默认值设置支持数据联动

## 2、联系人（供应商）（待测试）

自定义关联对象、子表单及数据联动铺开需求


![Picture 1](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbPXxwKrqXx/img/32f37abc-d8ba-4e59-be53-41b641bb11cf.jpeg?Expires=1774165334&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=6Fv%2FiCmAAj28cdlAaLr6Tt9svBw%3D "")

## 3、跟进记录（已上线）

自定义关联对象、子表单及数据联动铺开需求


![Picture 2](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbPXxwKrqXx/img/9e0a93ea-2ddb-4d35-8186-bb65bc34c7c1.png?Expires=1774165334&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=qEvGzKdI3YPy9BMdZ7GXOjXznWg%3D "")

| **需求** | **说明** |
|----------|----------|
| 关联对象/关联对象类型 | 一、4.4 【跟进铺开】指定关联对象支持自定义[<u>https://gykj.yuque.com/vhho51/asmkvg/enxg4k?singleDoc#</u>](https://gykj.yuque.com/vhho51/asmkvg/enxg4k?singleDoc#) 《子表单补充功能》二、公海/线索池中单据下，可以直接快捷新建跟进记录：若针对目前数据范围设置（不设置数据范围）可以直接快捷新建，则不做其他处理若不能，则需要前端处理，将线索/公海对象、数据带入 |
| 关联产品 | 技术先导出近一个月有用到该功能的客户，让客成同事进行沟通，提前告知要下架 |
| 跟进联系人数据范围配置 | 特殊处理：同目前线上流程\+ 关联客户：联系人可选择客户下的联系人\+ 关联报价单/销售机会/合同订单/协议/工单/项目：可选上述单据关联的客户，下的联系人\+ 其他：该字段隐藏 |
| 引用客户地址 | 4.3 【跟进铺开】引用字段：支持指定关联对象/支持地址组件[<u>https://gykj.yuque.com/vhho51/asmkvg/enxg4k?singleDoc#</u>](https://gykj.yuque.com/vhho51/asmkvg/enxg4k?singleDoc#) 《子表单补充功能》 |
| 字段配置 | 1.系统字段迁移如上字段说明，未注明的即保持原字段属性及配置不变2.用户自定义字段则原逻辑迁移 |
| 交互优化 | 一、样式固定1、pc端\+ 新建编辑（直接新建&快捷新建）- 跟进内容固定在最上方，其余同模板设置（改造前关联对象也是固定在最上方的，此次需要变动）- 子表单：同其他对象\+ 单据下列表/跟进记录列表- 跟进内容固定在最上方，其余同模板设置- 点击跟进记录整个区块，可穿透查看跟进记录详情\+ 跟进记录详情（新增）- 详情tab：跟进内容固定在最上方，其余同模板设置- 其他tab：同其他对象- 根据角色权限，展示‘打印’按钮2、mb端\+ 新建编辑- 将‘跟进内容’移动到基本信息区块下（因为要添加子表单）- 跟进内容固定在最上方，其余同模板设置（同线上）- 子表单：同其他对象\+ 单据下列表/跟进记录列表- 展示内容及样式同线上- 点击跟进记录整个区块，可穿透查看跟进记录详情\+ 跟进记录详情（新增）- 详情tab：展示内容及样式同线上- 其他tab：同其他对象二、指定关联对象选择弹窗交互优化1、‘对象类型’已选择（例：客户）：选择关联弹窗中‘对象’默认=已选择对象2、支持在选择关联弹窗中变更‘对象’，变更后对应的场景、搜索字段、按钮、列表字段及数据均变更为对应对象；3、选择数据后，若‘对象’有变更，须将‘对象类型’更新 |
| 其他 | 1、跟进记录保存草稿功能须保留2、跟进内容中支持@人员须保留3、跟进中语音、电话录音等，须保留4、拨打下一位功能须保留[<u>https://tb.raycloud.com/task/5ef312dfeeb76f3ff598d362</u>](https://tb.raycloud.com/task/5ef312dfeeb76f3ff598d362)5、呼叫中心：客户、线索列表，点击拨号后，自动进入详情页-跟进记录 功能须保留[<u>https://tb.raycloud.com/task/5ef31287110851400cc9a32d</u>](https://tb.raycloud.com/task/5ef31287110851400cc9a32d)6、跟进记录评论中支持@人员 须保留[<u>https://tb.raycloud.com/task/5fb63087a03d5c2a1f47c711</u>](https://tb.raycloud.com/task/5fb63087a03d5c2a1f47c711)7、跟进记录tab页支持内容搜索 须保留[<u>https://tb.raycloud.com/task/6268b9757bcbb500332e2176</u>](https://tb.raycloud.com/task/6268b9757bcbb500332e2176)8、跟进记录增加【批量删除】按钮\+ 未选中数据：点击按钮时toast提示‘请先选择要操作的数据’\+ 选中的数据中包含\{对象类型\}=‘客户’or ‘线索’or ‘销售机会’ or ‘合同订单’时，删除失败并toast提示‘删除失败：涉及到线索/客户回收，线索/客户/销售机会/合同订单下的跟进记录不支持批量删除’ |

![Picture 3](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbPXxwKrqXx/img/8fa4a173-1287-4a9e-832f-884c44a786e8.png?Expires=1774165334&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=mfPvpgS0Dl9irWxxpPFPZCAWXEo%3D "")

![Picture 4](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbPXxwKrqXx/img/6d83b1d3-2b7c-4cf7-bba2-28bd6a83b45f.png?Expires=1774165334&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=idrDg7JYrmv9OOgMdwQHidXvTyw%3D "")

## 4、销退入库单（已上线）

自定义关联对象、子表单及数据联动铺开需求


![Picture 5](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbPXxwKrqXx/img/048247e6-c025-480a-b6e4-c84dcffd5ecf.png?Expires=1774165334&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=rdH4tJUueqhm%2B%2BGpmNEo%2Fpg5pIs%3D "")

| **需求** | **说明** |
|----------|----------|
| 其他交互需求 | 详情页：源单明细行编码这个关联对象字段，不支持点击穿透 |
| 子表单配置 | 一、子表单移动端字段配置根据各企业现在的配置情况进行迁移二、子表单字段配置1.系统字段迁移如上字段说明，未注明的即保持原字段属性及配置不变。备注：1）批次保质期相关组件、单位成本/成本需求保持目前线上逻辑单位成本/成本：[<u>https://tb.raycloud.com/task/616cd86b933f542a1a514c7b</u>](https://tb.raycloud.com/task/616cd86b933f542a1a514c7b)2）待入库数量：\{源单明细行编码\}不为空的明细行的逻辑同目前线上；为空的，则该值为0；3）支持多仓库退货入库\+ 交互优化（参考其他入库单）- 添加一条明细：默认带出主单据的“仓库”（如主单据的“仓库”为空或隐藏，则不带出“仓库”，用户手动选择）- 变更主业务对象“仓库”：弹窗提示如下（pc\+mb）\* 用户点击“取消”后，变更仓库失败；\* 点击“确认”，变更仓库成功，并按照修改后的仓库批量变更明细行\{仓库\}信息；\+ 历史数据处理- 功能上线时，将历史其他入库单明细该字段，统一刷成主表\{仓库\}信息\+ 变更库存逻辑- 单据审核通过/编辑重新审批/删除等操作，增加/扣减库存的逻辑变更为根据明细表行仓库\+产品明细；2.用户自定义字段则原逻辑迁移 |
| 升级引导 | 1\. 历史客户：业务模板-销退入库单产品，统一展示提示页面如下，参考‘报价单产品’2\. 新签客户：去除‘业务模板-销退入库单产品’ |

![Picture 6](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbPXxwKrqXx/img/b22377b7-bd93-4d4e-871e-e6a01fd777de.png?Expires=1774165334&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=BXq8fZLXOq3lnzPpqxjoB82nYps%3D "")

![Picture 7](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbPXxwKrqXx/img/f8e196ea-36b0-42ad-b734-49bc2b4e065a.png?Expires=1774165334&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=ysRWxLMQDpeGdPi5UST3vRKho%2FY%3D "")

## 5、日报/月报/周报（一期已铺开）（已上线）


![Picture 8](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbPXxwKrqXx/img/301906d8-a3a9-4146-838d-43b2eb02e87c.jpeg?Expires=1774165334&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=vOt1GVSEzDbdHHOC1%2BwYh%2B4QEVk%3D "")

| **需求** | **说明** |
|----------|----------|
| 新建编辑页 | 一、pc端：页面布局同其他正常对象（目前线上逻辑是模板设置中的区块会失效）\+ 工作业绩：还是固定在字段‘报告时间’下二、mb端（页面布局同其他正常对象（目前线上逻辑是模板设置中的区块会失效）\+ 工作业绩：还是固定在页面顶部 |
| 详情页 |  |

![Picture 9](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbPXxwKrqXx/img/b106fdb6-b99a-4b9c-ac5a-d4f26149d241.png?Expires=1774165334&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=0cSR5jUbR%2Bao1LjnFJuy0tAetfE%3D "")

![Picture 10](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbPXxwKrqXx/img/13e784ed-b0e4-4a54-9cf1-e13b585c7b23.png?Expires=1774165334&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=meSLLw0M5CWz62PqVAhSCfYqgWU%3D "")

![Picture 11](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbPXxwKrqXx/img/d02ade17-b370-48fd-bd42-8393be083a21.png?Expires=1774165334&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=JME2Iike73JMffxrCAi32x0ys0I%3D "")

## 6、采购价目表（已上线）


![Picture 12](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbPXxwKrqXx/img/0cabbf9d-5a7f-4182-a20f-54534329456e.png?Expires=1774165334&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=F2Lf%2BuyFRimFSPMBlqG634MaTvM%3D "")

| **需求** | **说明** |
|----------|----------|
| 子表单配置 | 一、子表单移动端字段配置根据各企业现在的配置情况进行迁移二、子表单字段配置1.系统字段迁移如上字段说明，未注明的即保持原字段属性及配置不变。2.用户自定义字段则原逻辑迁移 |
| 升级引导 | 1\. 历史客户：业务模板-采购价目表产品，统一展示提示页面如下，参考‘报价单产品’2\. 新签客户：去除‘业务模板-采购价目表产品’ |

![Picture 13](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbPXxwKrqXx/img/f8e196ea-36b0-42ad-b734-49bc2b4e065a.png?Expires=1774165334&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=ysRWxLMQDpeGdPi5UST3vRKho%2FY%3D "")

## 7、采购退货单（已上线）


![Picture 14](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbPXxwKrqXx/img/56556fd6-5459-4da0-80a1-bbf5321f0d96.png?Expires=1774165334&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=7YNLXHn7RzjXQg7a%2BkeNxwvqgKI%3D "")

| **需求** | **说明** |
|----------|----------|
| 子表单配置 | 一、子表单移动端字段配置根据各企业现在的配置情况进行迁移二、子表单字段配置1.系统字段迁移如上字段说明，未注明的即保持原字段属性及配置不变。2.用户自定义字段则原逻辑迁移 |
| 升级引导 | 1\. 历史客户：业务模板-采购退货单产品，统一展示提示页面如下，参考‘报价单产品’2\. 新签客户：去除‘业务模板-采购退货单产品’ |

![Picture 15](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbPXxwKrqXx/img/f8e196ea-36b0-42ad-b734-49bc2b4e065a.png?Expires=1774165334&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=ysRWxLMQDpeGdPi5UST3vRKho%2FY%3D "")

## 8、产品/产品明细（已上线）


![Picture 16](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbPXxwKrqXx/img/3e246075-e734-490b-a1b7-70ab9203197d.jpeg?Expires=1774165334&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=nfw0mLIgLJsn6sT%2FIGWKXCnCocg%3D "")

| **需求** | **说明** |
|----------|----------|
| 说明 | 一、产品/产品明细：不支持插入子表单、阶段推进器，在点击添加时添加失败并toast提示‘当前对象类型不支持添加\{字段类型\}’二、关联对象、数据联动、计算公式、引用字段、工作流程等不支持获取对象‘产品’二、其他样式等同当前线上逻辑 |

## 9、采退出库单（已上线）

自定义关联对象、子表单及数据联动铺开需求


![Picture 17](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbPXxwKrqXx/img/2f001d23-83e7-4787-8bb0-fbfd20b9526a.png?Expires=1774165334&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=Uc9ZL0VwhG3ALgNyu%2Fzd3EV%2FTUc%3D "")

| **需求** | **说明** |
|----------|----------|
| 其他交互需求 | 详情页：源单明细行编码这个关联对象字段，不支持点击穿透 |
| 子表单配置 | 一、子表单移动端字段配置根据各企业现在的配置情况进行迁移二、子表单字段配置1.系统字段迁移如上字段说明，未注明的即保持原字段属性及配置不变。备注：1）批次保质期相关组件需求保持目前线上逻辑2）待出库数量：\{源单明细行编码\}不为空的明细行的逻辑同目前线上；为空的，则该值为0；3）支持多仓库退货出库\+ 交互优化（参考其他出库单）- 添加一条明细：默认带出主单据的“仓库”（如主单据的“仓库”为空或隐藏，则不带出“仓库”，用户手动选择）- 变更主业务对象“仓库”：弹窗提示如下（pc\+mb）\* 用户点击“取消”后，变更仓库失败；\* 点击“确认”，变更仓库成功，并按照修改后的仓库批量变更明细行\{仓库\}信息；\+ 历史数据处理- 功能上线时，将历史出库单明细该字段，统一刷成主表\{仓库\}信息\+ 变更库存逻辑- 单据审核通过/编辑重新审批/删除等操作，增加/扣减库存的逻辑变更为根据明细表行仓库\+产品明细；2.用户自定义字段则原逻辑迁移 |
| 升级引导 | 1\. 历史客户：业务模板-采退出库单产品，统一展示提示页面如下，参考‘报价单产品’2\. 新签客户：去除‘业务模板-采退出库单产品’ |

![Picture 18](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbPXxwKrqXx/img/b22377b7-bd93-4d4e-871e-e6a01fd777de.png?Expires=1774165334&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=BXq8fZLXOq3lnzPpqxjoB82nYps%3D "")

![Picture 19](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbPXxwKrqXx/img/f8e196ea-36b0-42ad-b734-49bc2b4e065a.png?Expires=1774165334&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=ysRWxLMQDpeGdPi5UST3vRKho%2FY%3D "")

## 10、客户（已上线）


![Picture 20](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbPXxwKrqXx/img/e920085b-5d54-419f-a2c2-68e13112d36c.jpeg?Expires=1774165334&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=4kBKlEBK6h4y6lOrz2fXIRcNB30%3D "")

| **需求** | **说明** |
|----------|----------|
| 客户合并 | 一、关联多选、子表单\+ 参考电话控件，可多选，多选时将两个客户的子表单数据进行合并（取并集）二、统计字段、计算字段\+ 不展示在合并设置页面\+ 客户合并后，需要重新计算统计值、计算值 |

![Picture 21](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbPXxwKrqXx/img/e8641295-1f66-4609-abda-f729e7a0e14e.png?Expires=1774165334&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=NLRI6evgLuWK0%2ByKnR1yQc2Lav0%3D "")

## 11、核算维度（已上线）


![Picture 22](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbPXxwKrqXx/img/1d247b75-619a-455c-8216-d556c2f96125.jpeg?Expires=1774165334&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=tiJfKYFq84Fh9qCOTxxb5g6ZJ8M%3D "")

## 12、调拨出库单（待测试）

自定义关联对象、子表单及数据联动铺开需求


![Picture 23](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbPXxwKrqXx/img/2649529b-5a86-4771-bd96-09f27fa07ba8.png?Expires=1774165334&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=RoXtpiaLPRJxGW3INVhVMaN%2FslA%3D "")

| **需求** | **说明** |
|----------|----------|
| 其他交互需求 | 详情页：源单明细行编码这个关联对象字段，不支持点击穿透 |
| 子表单配置 | 一、子表单移动端字段配置根据各企业现在的配置情况进行迁移二、子表单字段配置1.系统字段迁移如上字段说明，未注明的即保持原字段属性及配置不变。备注：1）批次保质期相关组件需求保持目前线上逻辑（参见其它入库单）2）待出库数量/库存数量：逻辑同目前线上2.用户自定义字段则原逻辑迁移 |
| 升级引导 | 1\. 历史客户：业务模板-调拨出库单产品，统一展示提示页面如下，参考‘报价单产品’2\. 新签客户：去除‘业务模板-调拨出库单产品’ |

![Picture 24](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbPXxwKrqXx/img/f8e196ea-36b0-42ad-b734-49bc2b4e065a.png?Expires=1774165334&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=ysRWxLMQDpeGdPi5UST3vRKho%2FY%3D "")

## 13、调拨入库单（待测试）

自定义关联对象、子表单及数据联动铺开需求


![Picture 25](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbPXxwKrqXx/img/c37caf8e-cb16-4a7b-9ab9-b83150d0128a.png?Expires=1774165334&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=7on%2FDmIShQDfBsYBq8azEbCUYuY%3D "")

| **需求** | **说明** |
|----------|----------|
| 其他交互需求 | 详情页：源单明细行编码这个关联对象字段，不支持点击穿透 |
| 子表单配置 | 一、子表单移动端字段配置根据各企业现在的配置情况进行迁移二、子表单字段配置1.系统字段迁移如上字段说明，未注明的即保持原字段属性及配置不变。备注：1）批次保质期相关组件需求保持目前线上逻辑（参见其它入库单）2）待入库数量：逻辑同目前线上3）新建编辑页面：入库的数量（良品\+次品\+损耗）必须与调拨出库单中保持一致2.用户自定义字段则原逻辑迁移 |
| 升级引导 | 1\. 历史客户：业务模板-调拨入库单产品，统一展示提示页面如下，参考‘报价单产品’2\. 新签客户：去除‘业务模板-调拨入库单产品’ |

![Picture 26](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbPXxwKrqXx/img/ea0ddaa6-2f3f-46fc-9984-2677f0bdc064.png?Expires=1774165334&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=xHkl57OxxfcJtKvLYalKi5jM6Cg%3D "")

![Picture 27](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbPXxwKrqXx/img/f8e196ea-36b0-42ad-b734-49bc2b4e065a.png?Expires=1774165334&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=ysRWxLMQDpeGdPi5UST3vRKho%2FY%3D "")

## 14、规格/规格值（待测试）


![Picture 28](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbPXxwKrqXx/img/ab87f9db-6893-4d09-99c1-31aa03b20d34.jpeg?Expires=1774165334&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=hbbRNxEiBw5hYGaw3fJlhSMe%2B9Q%3D "")

| **需求** | **说明** |
|----------|----------|
| 子表单配置 | 一、子表单移动端字段配置根据各企业现在的配置情况进行迁移二、子表单字段配置1.系统字段迁移如上字段说明，未注明的即保持原字段属性及配置不变。2.用户自定义字段则原逻辑迁移 |
| 升级引导 | 1\. 历史客户：业务模板-规格值，统一展示提示页面如下，参考‘报价单产品’2\. 新签客户：去除‘业务模板-规格值’ |

![Picture 29](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/meonarbPXxwKrqXx/img/f8e196ea-36b0-42ad-b734-49bc2b4e065a.png?Expires=1774165334&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=ysRWxLMQDpeGdPi5UST3vRKho%2FY%3D "")

## 15、账户设置（待测试）

自定义关联对象、子表单及数据联动铺开需求：‘备注’字段默认值设置支持数据联动
