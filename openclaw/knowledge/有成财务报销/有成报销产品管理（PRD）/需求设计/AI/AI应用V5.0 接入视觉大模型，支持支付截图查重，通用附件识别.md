---
title: "AI应用V5.0 接入视觉大模型，支持支付截图查重，通用附件识别"
nodeId: 7NkDwLng8ZM3BaPOhMAQDlOqJKMEvZBY
workspaceId: R2PmK2gngjVnZXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/7NkDwLng8ZM3BaPOhMAQDlOqJKMEvZBY?utm_scene=team_space"
exportedAt: 2026-04-07T08:15:35.594Z
source: dingtalk-document-mcp
---
| 修订时间 | 版本 | 修订说明 |
|------------|------|------------|
| 20251210 | v1.0 | 新建 |
| 2026.1.12 | V2.0 | 固定类型开放配置，整合开关形成一个页面 |

# **1\. 需求背景**

除了发票报销入账，一些企业无法获取到发票作为原始报销附件的场景中，往往会用支付截图来证明支付的合理性，但是支付截图之前没有统一编号，容易造成重复报销。

另外，在AI审核场景中，客户提出想要校验上传的行程单、合同内容是否和单据内容一致，也需要用到接入OCR/ LLM能力。

视觉大模型或者多模态大模型均具备此能力。

# **2\. 业务流程/架构**

## **迭代路线**

P1-基础能力，未购买AI应用的用户也能够使用。
1. 附件区分附件类型，所有附件类型有自己的详细信息
    1. 历史附件归为“未分类”，未分类的只有“文件名”。
    2. 涉及到所有录入附件的入口，支持设置附件类型、手工补充附件的详细信息。
2. 支持根据附件类型中的某些字段进行查重。



P2-AI
3. AI根据选择的附件类型，自动填写附件详情
4. mcp\_tools增加查询附件详情-AI审批



P3-AI，支付截图生成消费
5. 部分附件支持快速生成消费，自动填单。
6. AI可以识别附件类型，用户上传附件后，AI完成识别类型-填写详情-生成消费的链路，后接消费-行程-填单流程。



后续规划：
- 支持附件\+发票关联到同一笔费用
- 放开附件类型、附件详情字段自定义
- 对公场景，附件智能填单



![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Q35O851RVLjMJl9V/img/6df5c342-8263-43ae-8fa5-1ff2f56f0379.png?Expires=1775556936&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=DD%2Buh7ICO17ude61uXHfgmgF7og%3D "")

本期需求范围P1\+P2

## **LLM可用性验证**

prompt：
> 以json格式输出附件类型、附件详情。   
> 附件类型有：未分类、支付截图、收款截图   
> 各附件类型的详情格式：   
> 1、未分类：   
> 没有详情。   
> 2、支付截图：   
- payment\_id，支付单号，格式：文本，必填；
- payment\_date，年月日格式的支付日期，格式：日期，必填；
- payment\_amount，支付金额，格式：数字，必填；
- payee\_name，收款方名称，格式：文本，非必填。
> 3、收款截图   
- receipt\_id，收款单号，格式：文本，必填；
- receipt\_date，年月日格式的收款日期，格式：日期，必填
- receipt\_amount，收款金额，格式：数字，必填；
- payer\_name，付款方名称，格式：文本，非必填；

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Q35O851RVLjMJl9V/img/8443b3d6-b4ff-4d4b-9923-e00074dc7f2f.png?Expires=1775556936&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=kM4rlED6hYXFwOZFhjTzolfXpJw%3D "")

试了十来张不同样式的支付宝/微信支付截图，准确率100%。



# **3\. 功能清单**

| 模块 | 功能点 | 备注 |
|------|---------|------|
| 全局设置 | 新增附件设置，支持设置附件查重、AI识别 |  |
| 费用、单据上传附件、附件中心 | 支持编辑附件类型：支付截图、支付截图 |  |
|  | 支持上传时AI自动识别附件类型<br>支持AI识别附件自动识别附件类型 |  |
| 附件管理 | 支持查看附件类型 |  |
| AI审核 | MCP-tools支持查询附件详情 |  |

# **4\. 需求详情**

## ~~**全局设置，新增附件设置**~~

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Q35O851RVLjMJl9V/img/32ed956b-bff7-4ac0-b350-c4cfec2ef3fa.png?Expires=1775556936&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=I0OKmp%2BriqmNFumgxA7A4f62Dlo%3D "")
1. ~~全局设置，新增“附件设置”tab~~
2. ~~附件设置页面中，新增“附件查重”、“AI自动识别”两个功能开关。~~
3. ~~附件查重开关：默认关闭。~~
    1. ~~开启后，展示查重规则配置：~~

| ~~字段~~ | ~~说明~~ |
|----------|----------|
| ~~附件类型~~ | ~~单选必选，~~<br>~~可选项：收款截图、支付截图~~<br>~~多条规则的附件类型不能重复。直接过滤。~~<br>~~切换附件类型时清空“查重字段”。~~ |
| ~~查重字段~~ | ~~多选必选~~<br>~~可选项：根据附件类型展示不同的字段。~~<br>~~收款截图可选：收款单号、收款日期、收款金额、付款方名称~~<br>~~支付截图可选：支付单号、支付日期、支付金额、收款方名称~~ |
| ~~适用单据类型~~ | ~~多选必选~~<br>~~可选项：报销单、借款单、申请单、收款单、付款单、合同、项目~~ |
| ~~预警规则~~ | ~~单选必选~~<br>~~可选项：预警提醒、预警禁止~~ |
        1. ~~规则全部完整后失焦入库，否则提示：请设置【附件类型】的【必填未填字段名称】。~~
        2. ~~删除规则时无需二次确认。~~
    2. ~~首次开启需要初始化两条查重规则。：~~
        3. ~~收款截图-收款单号-适用全部单据类型-预警禁止。~~
        4. ~~支付截图-支付单号-适用全部单据类型-预警禁止。~~
4. ~~AI自动识别开关：默认关闭。提示文案：~~
> ~~开启后，上传附件时AI会自动识别附件类型并填写附件详情。~~   
    3. ~~开启时，判断企业当前是否购买了“AI应用”：~~
        5. ~~如果当前企业未开通“AI应用”，弹框提示，“企业尚未开通AI应用，欢迎联系客服了解详情”~~
        6. ~~如果企业已开通“AI应用”或正在试用AI应用，则可开启开关。~~
    4. ~~开启后，展示下级开关“AI自动识别后允许提交人修改附件类型”，并展示限制提交人编辑字段设置。~~
        7. ~~自动识别后允许提交人修改附件类型，默认关闭~~
        8. ~~限制提交人编辑字段：~~

| ~~字段~~ | ~~说明z~~ |
|----------|-----------|
| ~~附件类型~~ | ~~单选必选，~~<br>~~可选项：收款截图、支付截图~~<br>~~多条设置的附件类型不能重复。直接过滤。~~<br>~~切换附件类型时清空“限制提交人编辑字段”。~~ |
| ~~限制提交人编辑字段~~ | ~~提示文案：~~<br>> ~~此处设置的字段只能由AI自动识别，不允许提交人手工编辑。~~   <br>~~多选必选~~<br>~~可选项：根据附件类型展示不同的字段。~~<br>~~收款截图可选：收款单号、收款日期、收款金额、付款方名称~~<br>~~支付截图可选：支付单号、支付日期、支付金额、收款方名称~~ |
            1. ~~设置全部完整后失焦入库，否则提示：请设置【附件类型】的【必填未填字段名称】。~~
            2. ~~删除设置时无需二次确认~~
        9. ~~首次开启“AI自动识别”时需要初始化两条限制编辑设置。：~~
            3. ~~收款截图-收款单号、收款金额。~~
            4. ~~支付截图-支付单号、支付金额。~~

## **费用、单据，附件组件上传的附件支持编辑附件类型**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Q35O851RVLjMJl9V/img/0b067d5b-197e-4574-a4d1-00a3d9b2ecd0.png?Expires=1775556936&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=F7O9C%2F3hwT4xz2d36HX2BBp5vdU%3D "")

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Q35O851RVLjMJl9V/img/bd68682d-1ff5-4083-ae50-08ce9a141ac3.png?Expires=1775556936&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=KKSuFn5fKyrSumx6NiA9Ld0E1Sg%3D "")



### **支持编辑附件类型**
1. 历史附件默认的附件类型为“未分类”。
2. 上传附件的入口，判断附件设置中是否开启了“AI自动识别”：
    1. 当附件设置中未开启“AI自动识别”时，默认上传的附件类型为“未分类”
    2. 当开启了“AI自动识别”时，判断企业当前是否开通了AI应用：
        1. 如果当前企业未开通“AI应用”（到期场景），则默认上传的附件类型为“未分类”；
        2. 如果企业已开通“AI应用”或正在试用AI应用，则调用支持视觉llm的agent，自动识别并填写附件类型及附件详情。
            1. 通过AI识别过附件详情的附件，后台打上AI识别标记。未来数据统计要用。
3. 修改原线上交互，线上点击编辑附件时，弹出的是修改附件名称弹框。优化成弹出附件详情。
    3. **当启用了“AI自动识别**~~**允许提交人修改附件类型**~~**”时，允许提交人切换附件类型。审批人能否切换遵循自定义单据/费用编辑权限设置\+审批流中附件编辑权限设置。（以下字段审批人编辑权限都按照这个规则，不再赘述）**
    4. **切换附件类型时，清空除“文件名”以外的字段。****【文件名固定展示，无需在附件类型中配置。文本框，上限50，必填。有附件编辑权限的用户都可以编辑。】**
    5. 附件详情弹框左侧展示文件预览，支持预览的格式有：png\\jpg\\bmp\\pdf\\ofd,暂不支持的格式提示“暂不支持预览”。
    6. 当附件类型为“未分类”时，有编辑附件权限的用户可以编辑文件名；
    7. 当附件类型为已配置分类时，根据维护好的最新规则内字段进行展示
    8. ~~当附件类型为“支付截图”时~~

| ~~字段~~ | ~~说明~~ |
|----------|----------|
| ~~文件名~~ | ~~文本，上限50，必填~~<br>~~有附件编辑权限的用户都可以编辑。~~ |
| ~~支付单号~~ | ~~文本，上限50，必填~~<br>~~当未启用AI自动识别时，提交人可编辑。~~<br>~~当启用了AI自动识别时，根据配置的附件类型下“~~~~限制提交人编辑字段~~~~”中的设置，判断提交人是否可编辑。~~<br>~~以下字段可编辑判断都是这个逻辑。~~ |
| ~~支付日期~~ | ~~yyyy-mm-dd，必填~~ |
| ~~支付金额~~ | ~~小数点前9后2，CNY，必填~~ |
| ~~收款方名称~~ | ~~文本，上限100，非必填。~~ |
    9. ~~当附件类型为“收款截图”时~~

| ~~字段~~ | ~~说明~~ |
|----------|----------|
| ~~文件名~~ | ~~文本，上限50，必填~~<br>~~有附件编辑权限的用户都可以编辑。~~ |
| ~~收款单号~~ | ~~文本，上限50，必填~~ |
| ~~收款日期~~ | ~~yyyy-mm-dd，必填~~ |
| ~~收款金额~~ | ~~小数点前9后2，CNY，必填~~ |
| ~~付款方名称~~ | ~~文本，上限100，非必填。~~ |

### **附件查重**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Q35O851RVLjMJl9V/img/4c054603-419e-4b09-b8c1-32e7f4319e10.png?Expires=1775556936&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=U2yErGYEyfzBkCo89LfTXnfwZzk%3D "")
1. 如果附件设置开启了“附件查重”，则根据查重选择的附件类型和查重字段，在以下入口校验
- 上传附件：编辑单据、费用，附件中心-我上传的-添加文件
- 附件详情保存
2. **校验规则：多个查重字段联合判断，和历史的同类附件，全部一致的视作重复。提示语：**

**预警提示：**

如果原附件还没有生成费用、生成单据：
> 已有重复的【附件类型】：【查重字段值逗号拼接】，所属员工：张三，   
> 是否继续？   

如果原附件已经生成了费用或者单据，则提示：
> 已有重复的【附件类型】：【查重字段值逗号拼接】，所属员工：张三，办公费，BX1231231313213，   
> 是否继续？   

**预警警告：**

如果原附件还没有生成费用、生成单据：
> 上传/保存失败。已有重复的【附件类型】：【查重字段值逗号拼接】，所属员工：张三。   

如果原附件已经生成了费用或者单据，则提示：
> 上传/保存失败。已有重复的【附件类型】：【查重字段值逗号拼接】，所属员工：张三，办公费，BX1231231313213。   
3. 对于预警提示，提示语需要展示在单据上，hover移入展示提示详情。

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Q35O851RVLjMJl9V/img/2d8afebd-3ec6-4280-a27f-dd937d1c6e57.png?Expires=1775556936&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=TMGhvcT7%2FEemBo9VfQfEWo6avVU%3D "")

如果原附件还没有生成费用、生成单据：
> 已有重复的【附件类型】：【查重字段值逗号拼接】，所属员工：张三，   

如果原附件已经生成了费用或者单据，则提示：
> 已有重复的【附件类型】：【查重字段值逗号拼接】，所属员工：张三，办公费，BX1231231313213。   

### **AI识别**

（适用于第一次AI自动识别不准确后修改类型场景）
1. 附件详情弹框中，当用户选择了不是“未分类”的附件类型时，展示“AI识别”功能。

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Q35O851RVLjMJl9V/img/f9dfc04e-fa6f-4f1a-8bc9-b984ea2f7203.png?Expires=1775556936&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=LDlfrNqU5jUOsiYsWkzqM19unK0%3D "")
2. 点击AI识别，判断当前企业是否开启了“AI应用”，：
    1. 如果当前企业未开通“AI应用”，弹框提示，“企业尚未开通AI应用，欢迎联系客服了解详情”
    2. 如果企业已开通“AI应用”或正在试用AI应用，则调用支持视觉llm的agent，上传附件、附件类型，识别并自动填写附件详情。
        1. AI识别中时，该附件详情均无法编辑。
    3. 通过AI识别过附件详情的附件，后台打上AI识别标记。未来数据统计要用。

## **附件中心-我上传的**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Q35O851RVLjMJl9V/img/12698e62-19b8-454e-a609-b023ecd9bee4.png?Expires=1775556936&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=%2B30jK819GzYY6I%2FR%2Bj8Akni2pGs%3D "")
1. 新增“附件类型”列，历史附件均为“未分类”，展示附件对应的类型。
2. 点击附件类型展示附件详情弹框，未关联单据、关联费用的支持编辑。
    1. 弹框中的编辑权限控制，和附件组件本地上传入口提交人的权限控制保持一致。
3. 添加文件时，按照“报销单”的附件查重控制处理。
4. 添加时，按照附件组件本地上传的附件类型处理逻辑处理。

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Q35O851RVLjMJl9V/img/dff05915-3841-4d8d-b3f4-53d486be111b.png?Expires=1775556936&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=hlgRk0Lsxar%2BWbTBgTsrnyOK%2BtU%3D "")

## **附件管理支持查看附件类型**
1. 附件管理中新增“附件类型”列。
2. 点击具体附件类型可弹框查看附件详情。这里仅能查看，不能编辑。

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Q35O851RVLjMJl9V/img/da70a1db-7c81-4b31-9fe1-70b68e2fe2c7.png?Expires=1775556936&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=1345pce4MjaGAwEZX6tHYLPmjp0%3D "")



## **移动端编辑附件、查看附件交互**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Q35O851RVLjMJl9V/img/2533998f-207d-4874-b0df-4bfaf0b7d224.png?Expires=1775556936&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=hnxdYsStehmcoZUZeYJFa8l%2FLa0%3D "")



## **AI审核，mcp能力拓展**

AI审核mcp，新增查询单据上/单据的费用上/单据子表单上附件的附件详情。

例如：
- 单据上消费明细组件中的费用如果包含“零星支出”的，则单据上附件4组件中必须包含“支付截图”类型的附件。
- 单据上附件组件中“收款截图”类型的附件，收款方名称必须和单据上辅助核算组件中辅助核算名称一致。
- 单据的消费明细组件中，如果费用上的附件组件上传了“支付截图”类型的附件，则该附件上的支付金额必须和对应费用金额一致。







## **开放附件类型可编辑，整合相关规则维护**

【部分内容会延用上方原文档，有调整的会重新说明】

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Q35O851RVLjMJl9V/img/aa02ec41-6713-4243-ad80-f97e98b3c23f.png?Expires=1775556936&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=I%2F1j0H8pY%2FzGo%2FxOuKQ%2F20uvuJE%3D "")

基础档案下新增“附件类型”

| **功能** | **具体描述** | **图示** |
|----------|----------------|----------|
| 附件类型 | 左侧类型列表：展示所有维护好的类型<br><ul><li>1. 固定展示“未分类”，点击右侧展示“历史附件统一归属于【未分类】”【图1】【后续可以做成维护条件，系统定时刷数据，赋值历史附件对应的类型】</li><br><li>2. 新增类型按钮：默认常亮。点击后弹出弹窗【图2】</li><br><li style="margin-left:1em">1. 类型名称：必填，文本框，20字符上限。</li><br><li style="margin-left:1em">2. 类型说明：必填，文本框，50字符上限。</li><br><li style="margin-left:1em">3. 保存时校验“类型名称”是否重复。确认不重复则左侧列表生成相应的新附件类型，并且右侧直接展示该附件类型的详情内容【图3】</li><br><li>3. 会在功能上线后初始化的时候，创建“支付截图、收款截图”两类</li></ul> | 图1:<br>![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Q35O851RVLjMJl9V/img/12b8e98e-c970-4f48-b2fa-06a5c6169488.png?Expires=1775556936&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=0UTHIlNXzOXLDQcp6vbj2s6jO6s%3D "")<br>图2:![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Q35O851RVLjMJl9V/img/c0cec1a7-9757-49a2-8281-8511611e2854.png?Expires=1775556936&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=THRGDZMJAw5yhpQeqjkMZrGmhTA%3D "")<br>图3:<br>![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Q35O851RVLjMJl9V/img/c6670514-63e8-49bf-9d7a-85eb6c92d72d.png?Expires=1775556936&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=9y1j1A9zToc7foZ%2FUAaq5JWfNKw%3D "") |
| 右侧附件类型详情内容 | 页面按钮：<br><ul><li>1. 编辑：按钮常亮，点击将页面变更为可编辑状态【部分字段可编辑，部分不可以】同时按钮变为“保存和取消”</li><br><li style="margin-left:1em">1. 点击保存统一校验所有必填项是否填写：</li><br><li style="margin-left:2em">1. 有一个不通过则所有内容都不保存，提示“存在必填项未填写”</li><br><li style="margin-left:2em">2. 全部通过后才会保存，同时更新操作人、最近一次操作时间字段</li><br><li style="margin-left:1em">2. 点击取消视为并未编辑返回原状态</li><br><li>2. 删除：按钮常亮，点击后判断是否部分配置字段已经存在值</li><br><li style="margin-left:1em">3. 若存在则不允许删除，提示“当前附件类型内的部分字段已经存在数据，无法删除”</li><br><li style="margin-left:1em">4. 若不存在则弹出二次确认弹窗【右图】</li></ul> | ![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Q35O851RVLjMJl9V/img/e06fc5e1-a0da-4276-9bd5-80866b5ae132.png?Expires=1775556936&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=g%2FFGiQoWvuaMSqqisUdzJNJEv7M%3D "") |
|  | 基础信息-非编辑态：【图1】<br><ul><li>1. 类型名称：创建时填写的名称</li><br><li>2. 类型说明：创建时填写的类型说明</li><br><li>3. 创建时间：该类型初次创建的时间</li><br><li>4. 操作人：最近一次操作的操作人员姓名</li><br><li>5. 最近一次操作时间：最近一次操作保存成功的时间</li><br>基础信息-编辑态：【图2】<br><li>1. 类型名称：不可编辑</li><br><li>2. 类型说明：文本框，回显填写内容</li></ul> | 图1:<br>![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Q35O851RVLjMJl9V/img/b1c9a2bb-db66-4b73-bb4d-18f37e2e6490.png?Expires=1775556936&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=%2Fa%2FWDIqZtWAT9dGz9BlkQfuE5JA%3D "")<br>图2：<br>![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Q35O851RVLjMJl9V/img/8119c941-6b69-484e-a2cb-361bb7fc5c1e.png?Expires=1775556936&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=qlqdjGhRyTFDcV6zhgftEN6FG5M%3D "") |
|  | 字段信息-非编辑态：【图1】<br><ul><li>1. 字段名称：英文属性名，唯一ID</li><br><li>2. 字段显示名称：中文名</li><br><li>3. 字段类型：填写字段类型限制</li><br><li>4. 字段格式：填写字段格式/长度限制</li><br><li>5. 是否必填：字段填写限制</li><br><li>6. 填写方式：字段填写规则限制</li><br><li>7. 字段描述：纯文本，解释备注</li><br><li>8. 是否可编辑：后续业务控制使用</li><br><li>9. 是否查重使用：后续业务控制使用</li><br>字段信息-编辑态：【图2】<br><li>1. 字段名称：文本框，40字符上限。可编辑时需要填写保存后校验是否与系统中其他类型下字段名称重复，若重复则提示“与“附件类型”内的“字段名称”重复”，若不重复则正常保存</li><br><li>2. 字段显示名称：文本框，20字符上限。可编辑时需要填写保存后校验是否与系统中其他类型下字段显示名称重复，若重复则提示“与“附件类型”内的“字段显示名称”重复”，若不重复则正常保存</li><br><li>3. 字段类型：下拉单选框，枚举值“文本、日期、数字”。</li><br>注：字段名称、字段显示名称、字段类型这三个值在未被使用并生成数据时，是可以进行删除修改的，而一旦生成了数据就不能再修改了【第一个是唯一编码，字段类型一旦存了数据再改会对历史数据存在影响】<br><li>4. 字段格式：根据所选字段类型做相应的可选内容展示。</li><br><li style="margin-left:1em">1. 字段类型为文本：文本框，底色提示语“填写字符长度上限”</li><br><li style="margin-left:1em">2. 字段类型为日期：下拉单选框，枚举值“YYYY-MM-DD、YYYY.MM.DD、YYYYMMDD、YYYY/MM/DD”</li><br><li style="margin-left:1em">3. 字段类型为数字：文本框，底色提示语“填写“位数，小数点后几位””</li><br><li>5. 是否必填：下拉单选框，枚举值“必填、非必填”</li><br><li>6. 填写方式：下拉单选框，枚举值“AI识别、人工填写”</li><br><li style="margin-left:1em">4. AI识别：附件详情弹窗中系统自动获取采集内容补充该字段</li><br><li style="margin-left:1em">5. 人工填写：附件详情弹窗中需要手动维护该字段时</li><br><li>7. 字段描述：文本框，50字符上限</li><br><li>8. 是否可编辑：下拉单选框，枚举值“是、否”</li><br><li style="margin-left:1em">6. 是：在附件详情弹窗中，只要具备附件编辑权限的人员都可以编辑。（就算是AI识别后也可以编辑）</li><br><li style="margin-left:1em">7. 否：在附件详情弹窗中，AI识别后则不再允许提交人手动编辑，但是审批人可以根据权限判断编辑</li><br><li style="margin-left:1em">8. 存在鼠标悬浮提示语“若不可编辑，则只能由AI自动识别补充，不允许提交人手动编辑，审批人能否编辑则需要按照审批流中的附件编辑权限控制”</li><br><li>9. 是否查重使用：下拉单选框，枚举值“是、否”</li><br><li style="margin-left:1em">9. 是：则在查重校验时，会根据当前字段来判断是否重复</li><br><li style="margin-left:1em">10. 否：则在查重校验时不会使用当前字段</li><br><li style="margin-left:1em">11. 存在鼠标悬浮提示语“查重字段完全一致时，视为同一份附件。查重字段自动选择必填”</li><br>注：标记为查重字段时，是否必填会自动选择“是”<br><li>10. 按钮：每一行左侧都有添加删除按钮，若仅有一行的时候只有添加【即：最少要有一个字段】</li><br><li style="margin-left:1em">12. 添加：在当前行下新增一行，全部为空值</li><br><li style="margin-left:1em">13. 删除：点击判断当前行字段是否已经存储数据，若已经存在则不允许删除，若不存在则弹出二次确认弹窗【图3】</li></ul><br>注：除字段描述外，均必填 | 图1:![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Q35O851RVLjMJl9V/img/0296b3f9-570b-4ccb-9458-6a02ec30f63f.png?Expires=1775556936&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=Vm79vct4P2B1U7%2F8PkGSTHylkJY%3D "")<br>图2:<br>![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Q35O851RVLjMJl9V/img/c87046a1-c43d-4b1c-8578-c064f5f27245.png?Expires=1775556936&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=uLClEyD7Fmq9Qs9siJsU8kCJktM%3D "")<br>图3:<br>![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Q35O851RVLjMJl9V/img/e06fc5e1-a0da-4276-9bd5-80866b5ae132.png?Expires=1775556936&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=g%2FFGiQoWvuaMSqqisUdzJNJEv7M%3D "") |
|  | 查重规则维护：<br><ul><li>1. ~~查重单据类型：多选必选；可选项：报销单、借款单、申请单、收款单、付款单、合同、项目~~</li><br><li>2. 查重预警规则：单选必选；可选项：预警提醒、预警禁止</li></ul> | ![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Q35O851RVLjMJl9V/img/6ced69aa-32f8-4ba7-adb0-27d4c227c4c0.png?Expires=1775556936&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=n42BlxNddO71T7uKWqfHxGLdbLM%3D "") |

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Q35O851RVLjMJl9V/img/8636393b-ea43-4551-a5e8-4f0b770af6a4.png?Expires=1775556936&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=oZ8vOUQ3I07kgjtCYOTUu0XYJNc%3D "")

【基础设置-全局设置】下新增“附件设置”tab
1. 附件查重开关：默认关闭
    1. 开启后在附件上传后就可以进行查重判断
2. AI自动识别开关：默认关闭。提示文案：
> 开启后，上传附件时AI会自动识别附件类型并填写附件详情。   
    2. 开启时，判断企业当前是否购买了“AI应用”：
        1. 如果当前企业未开通“AI应用”，弹框提示，“企业尚未开通AI应用，欢迎联系客服了解详情”
        2. 如果企业已开通“AI应用”或正在试用AI应用，则可开启开关。
