---
title: "crm开票申请同步到有成电票优化"
nodeId: 14lgGw3P8vvl0xnzIGEPEdoY85daZ90D
workspaceId: R2PmK2gngjVnZXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/14lgGw3P8vvl0xnzIGEPEdoY85daZ90D?utm_scene=team_space"
updateTime: 1761036188000
exportedAt: 2026-05-14T12:13:33.864Z
source: dingtalk-document-mcp
---
| 修订时间 | 版本 | 修订人 | 修订说明 |
|-----------------------------------------------------------------------|-----------------------------------------------------------------|--------------------------------------------------------------------|-----------------------------------------------------------------------|
| 2025-8-8 | v1.0 | 黄艺平 | 新建 |
|  |  |  |  |

## 需求背景

报销-\>电票：
- 单据映射配置，报销侧可选单据中，单据类型=申请单and包含开票申请组件
- 单据中包含其他信息，如购买方信息、发票抬头、开票主体、开票类型、开票产品
- 电票完成开具后，信息回传至报销，并核销开票申请-关联单据-实际开票金额



crm-\>电票现状：
- 开票类型无法同步
- 发票抬头无法同步
- 开票申请关联单据无法同步
- 开完票后状态、发票、实际开票金额没有回传

## 需求详情

| 需求 | 描述 |
|-----------------------------------------------------------------|-----------------------------------------------------------------|
| 发票抬头同步 | 1、单据：【crm】发票信息--\>【报销】发票抬头<br>2、映射：<br><ul><li>\[crm\]发票抬头（invoice\_title）-\>\[报销\]抬头</li><br><li>\[crm\]纳税识别号（tax\_identify\_num）-\>\[报销\]税号</li><br><li>\[crm\]发票开户行（deposit\_bank）-\>\[报销\]开户行</li><br><li>\[crm\]发票开户账户（account\_num）-\>\[报销\]银行账号</li><br><li>\[crm\]发票电话（invoice\_tel）-\>\[报销\]固定电话</li><br><li>\[crm\]发票开票地址（invoice\_address）-\>\[报销\]地址</li><br><li>\[crm\]创建人（creator\_name）-\>\[报销\]可见范围.可见人员</li><br>3、逻辑<br><li>crm侧新增抬头</li><br><li style="margin-left:1em">无重复抬头：报销侧新增抬头，并绑定对应辅助核算（若有）</li><br><li style="margin-left:1em">有重复抬头：绑定对应辅助核算（目前绑定抬头无限制，绑定过的抬头支持重复被选中）</li><br><li>~~crm侧编辑：同步修改~~</li><br><li>~~crm侧删除：同步删除，并解绑客户对应辅助核算（若有）~~</li></ul><br>![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/r4mlQ5bVgyvZvlxo/img/65c753de-a6b1-414e-8270-8ac609bc458b.png?Expires=1778767520&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=NyABqwB8Sml2ArUrqvX4rK2%2B%2FaM%3D "")<br>![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/r4mlQ5bVgyvZvlxo/img/1878b45f-190c-4523-8b94-a1676324bf61.png?Expires=1778767520&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=pVgWKNxNj0aYB5pvrePsRWzYGo8%3D "") |
| 单据同步映射配置 | 一、报销侧字段增加获取<br><ul><li>发票类型（属性同下拉框）</li><br><li>收款场景、付款场景（属性同下拉框）\+发票金额</li><br><li style="margin-left:1em">收款/付款场景=部分开票收款/部分开票付款，才取映射的发票金额字段</li></ul><br>![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/r4mlQ5bVgyvZvlxo/img/2164b283-e669-415a-98e2-a13405535fb6.png?Expires=1778767520&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=yZYzDOli9GJwp6UUfoGuk67YErw%3D "")<br>二、当选择crm中开票申请数据做同步映射时，增加弹窗展示<br>![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/r4mlQ5bVgyvZvlxo/img/cf800ca7-7147-4596-9a93-fe31d18f6b22.png?Expires=1778767520&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=PLkip5eXO6%2BMBWqd9wrHlS7g3aQ%3D "") |
| 单据同步优化 | 一、发票抬头匹配<br>报销单据中\[发票抬头\]组件展示时，取开票申请中填写的发票抬头信息（以发票抬头唯一匹配）<br><ul><li>报销侧已有该抬头：在单据中关联选择</li><br><li>报销侧无该抬头：报销侧新增抬头（取本单中填写的抬头信息）\+单据中关联选择</li><br>![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/r4mlQ5bVgyvZvlxo/img/2e7594a3-42b3-46c7-b9c6-9361f63ecc34.png?Expires=1778767520&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=Z54nyZJwFDt%2BdHPbmm0Tix%2BmA88%3D "")<br>二、开票核销单据优化<br>![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/r4mlQ5bVgyvZvlxo/img/9b151095-0241-45bb-adc3-3b4677be24cc.png?Expires=1778767520&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=yAb1vRqpF1PesvTjQ%2F3rhMY0Woo%3D "")<br>报销单据中\[开票申请\]组件展示时，取开票申请中填写的关联回款<br><li>1. 关联单据映射</li><br><li style="margin-left:1em">1. 查找关联回款</li><br><li style="margin-left:2em">1. 关联回款已填写：查找对应**回款单（计划/实际两种类型，一张单据中不会同时存在）**在报销侧对应的收款单</li><br><li style="margin-left:3em">1. 均有查找对应单据到且满足可被关联的条件：关联对应单据</li><br><li style="margin-left:3em">2. 不满足上述条件：\[开票申请\]组件为空</li><br><li style="margin-left:2em">2. 关联回款未填写：执行  \[查找关联订单\]</li><br><li style="margin-left:1em">2. 查找关联订单</li><br><li style="margin-left:2em">3. 关联订单已填写：查找对应合同订单在报销侧对应的收款单</li><br><li style="margin-left:3em">3. 均有查找对应单据到且满足可被关联的条件：关联对应单据</li><br><li style="margin-left:3em">4. 未查找到符合条件的数据：\[开票申请\]组件为空</li><br><li style="margin-left:2em">4. 关联订单未填写：\[开票申请\]组件为空</li><br><li>2. 金额映射</li><br><li style="margin-left:1em">3. \[crm\]开票金额（invoice\_particular\_amount）-\>\[报销\]本次开票金额</li></ul> |
| 【crm】开票申请 | 一、增加字段‘发票开具状态’（所有新旧企业）<br><ul><li>字段类型：单选</li><br><li>字段属性：其他字段</li><br><li>字段名称：发票开具状态</li><br><li>描述信息：-</li><br><li>是否必填：默认非必填</li><br><li>是否隐藏：默认不隐藏</li><br><li>选项值：待开票、开票完成、开票失败</li><br><li>其他：新建编辑页面不展示</li><br>![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/r4mlQ5bVgyvZvlxo/img/3ac2258f-f153-4c2d-8787-6baaa64d2f65.png?Expires=1778767520&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=w4EmQ8Z5hYVhwWo9SUzeKU1W2%2Bo%3D "")<br>二、电票发票开具完成后（成功/失败），同步更新<br><li>发票开具状态</li><br><li>附件：文件从电票下载--\>传到crm文件服务器--\>更新至此字段（不要直接替换）--存储路径是钉盘的企业不支持回传</li><br><li>开票明细.开票金额：根据已开发票‘核销金额’，修改对应‘开票金额’</li></ul><br>![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/r4mlQ5bVgyvZvlxo/img/648bf3ff-ee72-4f3f-802e-ae7fea0066c8.png?Expires=1778767520&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=Zt%2Bv2tEKC8kgi0TL6oDOpzySHIw%3D "")<br>![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/r4mlQ5bVgyvZvlxo/img/3d5de91f-1358-4783-a14f-b53c97511fe1.png?Expires=1778767520&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=ns2k2TOeFASrKYC38GhXbcFwA94%3D "") |
