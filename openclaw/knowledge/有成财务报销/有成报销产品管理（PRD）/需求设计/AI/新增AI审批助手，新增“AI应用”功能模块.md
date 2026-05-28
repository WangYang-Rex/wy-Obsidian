---
title: "新增AI审批助手，新增“AI应用”功能模块"
nodeId: N7dx2rn0JbZ9KxGotq0Z1DgYJMGjLRb3
workspaceId: R2PmK2gngjVnZXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/N7dx2rn0JbZ9KxGotq0Z1DgYJMGjLRb3?utm_scene=team_space"
exportedAt: 2026-04-01T02:10:01.810Z
source: dingtalk-document-mcp
---
| 修订时间 | 版本 | 修订说明 |
|------------|------|------------|
| 20250828 | v1.0 | 新建 |
|  |  |  |

# **需求背景**

历史需求：[二期：AI自动报销优化，新增ai费用标准查询、AI客服咨询](https://alidocs.dingtalk.com/i/nodes/Y1OQX0akWm3gpzNXTYzgQRvGJGlDd3mE?utm_scene=team_space)


此前我们上线了通用场景agent、提单助手agent、查询费用标准agent、在线客服agent，主要解决的是员工的诉求，为每个员工配置了专属助理。

## **业务背景**

在企业费控报销场景中，财务扮演了至关重要的角色，一方面财务作为审批角色，日常中需要花费很多时间精力审批单据，任务重、责任重，另一方面财务也对企业费控系统选型有一定决策权，能够一定程度上影响老板是否购买我们的产品。

和费用标准、发票验真这类规则性校验不同，企业在审批报销单据时还有很多偏向业务上的校验，这些规则每个企业都不同，用代码实现的成本也很高。可以让企业自行上传业务规则作为企业知识库，agent利用RAG能力，调用单据详情接口获取单据信息，匹配校验规则。

（这里需要能够实现企业间知识库隔离）

本期开始因为面向多个角色集成了不同AI应用能力，也以此搭建AI应用模块，为三期面向老板的ai看板、ai报告做准备。

## **商业价值**

此外，该功能作为提升效率、控制风险的高价值功能，计划单独收费。其能力依赖AI能力，成本和token正相关，具体商务模式和价格需要测算后确定，故先在后台预留收费开关。

# **业务流程/架构**

[白板]

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0b9JyMJNnw1/img/4e87c5e4-c156-472d-a370-8a2982a20c8e.png?Expires=1775016602&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=3UQ8JtRt6admrmJHtYlAQhuNxbA%3D "")



# **功能清单**

| 模块 | 功能点 | 备注 |
|------|---------|------|
| AI应用 | 新增“AI应用”一级功能模块 |  |
| AI应用-AI运行看板 | 本期先放静态图 |  |
| AI应用-AI审批 | AI审批助手（含审批规则） |  |
| 审批流 | 新增AI审批节点，AI自动审批。 |  |
| 单据审批 | AI审批助手开关，人工单据审核时辅助审核。 |  |
| AI应用-AI审批 | AI审批记录 |  |
| AI应用-AI分析 | 本期先放静态图 |  |
| 管理后台 | 管理后台开关增加AI应用 |  |

# **需求详情**

## **新增“AI应用”一级功能模块**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0b9JyMJNnw1/img/21fa5b51-8f2f-4bdd-a554-ab45f1742835.png?Expires=1775016602&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=fIkw%2F3yJHI2A9lNG1w9ypUGDYD8%3D "")
1. 新增AI应用一级功能模块，顺序在报表中心之后。下设四个子菜单：AI运行看板、AI审批、AI分析、AI异常监控。支持设置菜单排序，停用启用。
2. 系统设置-角色与权限-功能授权对应新增模块及其子菜单。默认权限处理见[三期：新增AI审批助手，新增“AI应用”功能模块](https://alidocs.dingtalk.com/i/nodes/N7dx2rn0JbZ9KxGotq0Z1DgYJMGjLRb3?utm_scene=team_space&iframeQuery=anchorId%3Duu_metea96552yqwyrg3ht)


![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0b9JyMJNnw1/img/f81630d2-0b6c-44c8-b3d6-36798f50289d.png?Expires=1775016602&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=slfv1WrMC8FWVTG2r0Fb6hxj8RE%3D "")





## **AI运行看板**

本期先静态页面

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0b9JyMJNnw1/img/86e5fc35-e885-4589-9e2f-9ad40394b33c.png?Expires=1775016602&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=TEMmPpIPA%2BM6F%2BOc1pP7Ty7U3sg%3D "")



## **AI审批-AI审批助手**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0b9JyMJNnw1/img/543475ff-65cc-4e45-a5f3-7b3d2ec90f77.png?Expires=1775016602&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=mFYPVjMDLGdB6LUAE8BH01uBZjk%3D "")

用户在这个页面上维护好审批助手及其规则， 在审批流节点上调用。

### **列表字段**

| 字段 | 说明 |
|------|------|
| 助手名称 | 展示各AI审批助手的名称 |
| 审批详情数据权限 | 展示各AI审批助手的审批详情数据权限； |
| 审批规则 | 展示各AI审批助手维护的规则条数； |
| 关联审批流 | 展示在节点中配置了该助手的审批流名称，若多个审批流配置了该助手，则逗号分隔多个审批流名称。 |

### **新增、编辑**

点击新增或编辑，当前页面打开新增AI审批助手页面。

限制一个企业最多50个审批助手，超出时点击新增，提示“一个企业最多50个审批助手”。

排序，最新创建的助手在最下面。

| 字段 | 说明 |
|------|------|
| 助手名称 | 文本输入框，必填，上限30字符。<br>同一企业内不可重名，若有重名则在文本框失焦时下方提示“已有同名审批助手，请修改名称” |
| 审批详情数据权限 | 文本框，不可输入，点击文本框后展示选择人员、部门、角色组件。（复用线上已有弹框）。<br>提示气泡文案：有审批详情数据权限的用户才可在单据中看到该助手的AI审批详情。 |
- 保存：仅保存，回到AI审批助手列表刷新。
- 保存并设置规则：保存并打开该助手设置审批规则页面。

### **设置审批规则**

点击当前页面打开该助手设置审批规则页面。

每个助手的规则即为Agent的知识库。

#### **列表字段**

排序，最新规则在最下面。

| 字段 | 说明 |
|------|------|
| 适用单据 | 展示规则的适用单据类型名称，一条规则同时适用多类单据的，名称用逗号分开。 |
| 规则名称 | 展示规则的名称。 |
| 具体规则 | 展示具体规则，超出列宽部分...，hover气泡展示完整规则。 |
| 风险等级 | 展示规则的风险等级。 |
| 问题定位 | 展示规则的问题定位。 |

#### **新增、编辑规则**

限制一个助手最多500条审批规则，超出时点击新增，提示“一个助手最多500条审批规则”。

| 字段 | 说明 |
|------|------|
| 适用单据 | 多选下拉框，必选，可多选单据类型。 |
| 规则名称 | 文本输入框，必填，上限100字符。<br>同一审批助手内不可重名，若有重名则在文本框失焦时下方提示“已有同名审批规则，请修改名称” |
| 具体规则-自然语言规则输入框 | 文本输入框，必填，上限800字符。<br>输入内容后用户可以点击格式化，调用agent能力将自然语义转化为规则表达式格式的文本。<br>本期支持识别的字段包含原条件规则表达式中支持的字段，以及：<br>[我的附件]<br>当点击之后无法将内容转化为格式化内容，则在下方提示：录入内容未检测到有效规则，请检查 |
| ~~具体规则-格式化规则内容~~ | ~~文本，仅展示格式化之后的文本。用户可以查看核对。~~ |
| 风险等级 | 单选必选，可选：低风险（默认）、高风险。 |
| 问题定位 | 单选非必选，可选单据常用字段。 |

点击保存时自动触发一次规则校验，只有校验通过的才允许保存。

#### **上传**
- 上传为增量上传。
- 上传时控制上传文件格式：doc、docx、xls、xlsx；
- 控制上传文件大小：不能超过5M
- 上传规则：根据内容解析出适用单据、规则名称、具体规则、风险等级。——调用知识库上传接口，定义好字段格式，自动切片。
    - 若在上传文件中未获取到风险等级的，默认为“低风险”
    - 问题定位不支持上传，需要用户在系统内维护。
- 上传时同样需要进行规则名称重名校验，提示“已有同名审批规则，请修改名称”。
- 若本次上传后会导致数据量超出500条上限，则这次上传都失败，提示“一个助手最多500条审批规则”。除了这种情况外为过滤上传，过滤上传失败的规则，剩余规则成功上传。

#### **批量编辑**

支持多选规则、批量编辑。

点击批量编辑展示批量编辑弹框，可批量覆盖所选规则的适用单据、风险等。为空则不覆盖。

未选择规则时点击提示“请选择规则”。

#### **删除**

支持多选规则、批量删除。支持单条删除。

删除时需要二次确认。“是否确认删除？确定/取消”

#### 其他页面元素

规则能力说明，点击后浏览器新标签页打开文档[AI审核规则能力说明](https://alidocs.dingtalk.com/i/nodes/G1DKw2zgV2RXBKQ3CQpw3G0vVB5r9YAn?utm_scene=team_space)


### **批量编辑**

可多选助手批量编辑。

点击批量编辑展示批量编辑弹框，可批量覆盖所选助手的审批详情数据权限，为空则不覆盖。

未选择助手时提示“请选择助手”。

### **删除**

仅支持单个助手删除。

删除时，需要校验助手是否已经配置到了审批流当中，若已经配置到了审批流中则阻断删除并提示“审批助手已经配置到审批流中，请调整审批流后再删除。”

删除时需要二次确认。“删除审批助手时将一并删除审批规则，是否确认删除？确定/取消”。

### **预置数据**

为方便用户使用，为启用了AI应用功能的企业预置一个AI审批助手，并给这个助手预置一套规则。
- 助手名称：AI审批助手（预置）
- 审批详情数据权限：默认给企业管理员、财务主管~~角色~~
- 审批规则：[AI审核规则能力说明](https://alidocs.dingtalk.com/i/nodes/G1DKw2zgV2RXBKQ3CQpw3G0vVB5r9YAn?utm_scene=team_space&iframeQuery=anchorId%3Duu_mev50flugq704pvls0i)


## **审批流-新增AI审批节点**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0b9JyMJNnw1/img/91e8df8c-d4d7-40a1-856e-e27c451d6645.png?Expires=1775016602&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=GrwO0TCjtdJIHAYKOgz%2FVUZcFTA%3D "")

注意：AI审批节点后的第一个审批/出纳节点上的“设置审批人”不能是“由审批人选择”，否则将无法提单。

### **新增AI审批节点**

新增节点“AI审批”。

| 字段 | 说明 |
|------|------|
| 节点名称 | 文本框，可编辑，默认“AI审批”。上限10字符。 |
| AI审批助手 | 下拉单选必选。保存时校验，提示“请选择AI审批助理”。<br>可选AI应用-AI审批助手，展示助手名称。<br>~~可点击“去新增”新标签页打开助手列表。~~<br>~~当已经选择了审批助手时展示“设置审批规则”，可点击新标签页打开该助手的设置审批规则页面。~~ |
| 审批选项 | 单选必选。<br>自动审批通过（默认）；<br>无论高低风险，存在风险项时，就自动驳回；<br>存在高风险时自动驳回。 |
| 抄送设置 | 功能开关“审批通过时，抄送给以下人员”<br>本期先仅支持指定抄送人，开启开关时，展示“指定抄送人”多选框，可选择具体人员。 |
| ~~其他设置~~ | ~~功能开关“允许调整信用分”~~<br>~~当开关开启时，和常规的审批节点一样，根据信用规则匹配，若命中规则执行扣减信用动作。~~ |

### **单据提交审批逻辑**
1. 单据提交时，AI审批节点不出现在选择审批人弹框中。

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0b9JyMJNnw1/img/95e1a808-4f40-4376-9d8f-7053bcff26bc.png?Expires=1775016602&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=%2FEMKZZvj4pQZoPdWRw8n8oDXy6A%3D "")
2. 单据提交审批时，若执行到了AI审批节点，则调用单据详情查询接口获取单据完整信息，传递给该节点上配置的审批助手（规则作为知识库），利用AI能力进行分析。

能够匹配的规则需要以单据类型过滤。

提示词示例：
> 根据\{\{知识库\}\}中单据类型为\{\{单据类型\}\}的规则，逐条校验\{\{单据详情\}\}中的信息是否存在风险，并输出【规则名称】、【规则分析】、【是否有风险】，输出格式为json。   
> 规则名称：符合单据类型的规则名称   
> 规则分析：根据具体规则，分析单据详情中的信息是否存在问题，控制在200字以内。   
> 风险情况：若单据中存在这条规则定义的问题，则根据规则的风险等级，输出“无风险、低风险、高风险”其中之一。   
3. 执行完匹配校验后，将输出记录到审批记录。[新增AI审批助手，新增“AI应用”功能模块](https://alidocs.dingtalk.com/i/nodes/N7dx2rn0JbZ9KxGotq0Z1DgYJMGjLRb3?utm_scene=team_space&iframeQuery=anchorId%3Duu_meteep4ujpz6ypazpjc)


根据审批节点上审批选项，确定审批结果（自动同意、驳回），并将本次审批分析输出记录到单据审批详情。
4. 当审批结果~~为驳回~~存在风险时，需要额外调用大模型能力生成AI审批总结并记录。

提示词示例：
> 用简洁明了的语言，总结\{\{上个输出节点内容\}\}。字数控制200字。   

驳回原因文案：
- 审批选项==无论高低风险，存在风险项时，就自动驳回：“存在风险项：【风险项名称】，【风险项名称】...”
- 审批选项==存在高风险时自动驳回。“存在高风险项：【高风险的风险项名称】，【高风险的风险项名称】...”
5. 当审批结果为自动同意时，流转到下一个节点。

根据抄送设置、信用分设置，执行抄送、扣减信用分逻辑。
6. 若因调用大模型接口超时，重试3次，依然失败则停留在当前节点上，并给系统管理员发送一条系统消息。
> 消息标题：AI审批节点异常，请关注   
> 消息内容：单据【单据编号】AI审批节点【节点名称】异常，请在流程监督页面人工干预。   

同时，在流程监督中展示该AI审批节点，可以人工同意或驳回。

### **单据退回的逻辑**

历史需求：[审批退回校验优化](https://alidocs.dingtalk.com/i/nodes/NZQYprEoWoerzxXOHP6ZZD1EJ1waOeDk?utm_scene=team_space)


若后续审批节点选择了AI审批节点进行退回，则重新执行AI校验逻辑。

## **待审批单据-AI审批详情**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0b9JyMJNnw1/img/7a6ef603-aef0-4b51-a454-0738a949254f.png?Expires=1775016602&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=%2FjE7r3h2azxRd%2BKIZYKULn3iRnw%3D "")

### **AI审批详情**

有对应AI审批助手数据权限的用户，在AI审批节点记录可以看到“详情”入口，点击后在单据详情右侧展示**该条记录的**详情。没权限的不展示“详情”。

若该条记录审批结果为驳回，则自动展开审批总结。

各规则校验结果按照高风险、低风险、无风险的顺序排序。

点击具体校验结果可以收缩、展开显示完整规则分析。

对于审批出存在风险的规则：
- 在AI审批助手规则库中配置了“问题定位”的组件，则展示“去查看”按钮。点击“去查看”在左侧单据详情中自动定位并高亮该组件。
- 若找不到该组件或未配置问题定位组件，则不展示“去查看”。

### “自动打开AI审批记录”开关
1. 待审批单据详情：对于启用了AI审批的企业，其下所有用户在待审批单据详情页面可以看到“自动打开AI审批记录”开关。

开启效果：在待审批单据详情页面右侧展示该单据上的最新一次AI审批详情

该开关按照用户维度记忆。
2. 其他能够看到审批记录的单据详情，不展示“自动打开AI审批记录”开关。

## **AI审批-AI审批记录**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0b9JyMJNnw1/img/ce988f84-ef2e-47bd-813c-861aa3ecd469.png?Expires=1775016602&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=yO47ryHCa%2BaFNvLbN1fVAZ6ssHE%3D "")

根据AI审批助手权限控制，展示AI审批助手审批记录。

按照审批时间从新到旧排序，最新的在最上面。

列表分页：50/100/200

筛选条件：
- 审批时间：前端控制近30天。
- ~~关键字：支持被审批单据单号、标题、申请人、部门、单据类型、审批结果、AI审批助手名称，模糊匹配筛选。~~

### **列表字段**

| 字段 | 说明 |
|------|------|
| 单号 | 被审批单据单号。列表数据对象为审批记录，因此可能会存在多条记录同一个单号的情况。<br>支持表头筛选。 |
| 标题 | 被审批单据标题<br>支持表头筛选。 |
| 申请人 | 被审批单据申请人<br>支持表头筛选。 |
| 部门 | 被审批单据部门<br>支持表头筛选。 |
| 单据类型 | 被审批单据类型<br>支持表头筛选。 |
| 审批结果 |  该条AI审批记录的审批结果：<br><ul><li>自动同意</li><br><li>驳回</li></ul> |
| 风险等级 |  该条AI审批记录的风险等级情况汇总。<br><ul><li>全部无风险的：无风险</li><br><li>仅存在高风险的：高风险（个数）</li><br><li>仅存在低风险的：低风险（个数）</li><br><li>存在高低风险的：高风险（个数），低风险（个数）</li></ul> |
| AI审批助手名称 | 该条AI审批记录的AI审批助手名称 |
| 审批时间 | 该条AI审批记录的审批时间<br>YYYY-MM-DD HH:MM:SS |

点击操作弹出该条审批记录的审批详情弹框。

| 字段 | 说明 |
|------|------|
| AI审批助手名称 | 该条AI审批记录的AI审批助手名称 |
| 审批时间 | 该条AI审批记录的审批时间<br>YYYY-MM-DD HH:MM:SS |
| 单据编号 | 被审批单据单号。列表数据对象为审批记录，因此可能会存在多条记录同一个单号的情况。<br>支持表头筛选。 |
| 审批选项 | 该条审批记录执行时，节点上的审批选项。<br><ul><li>自动审批通过；</li><br><li>无论高低风险，存在风险项时，就自动驳回；</li><br><li>存在高风险时自动驳回。</li></ul> |
| 审批结果 | 该条AI审批记录的审批结果：<br><ul><li>自动同意</li><br><li>驳回</li></ul> |
| 审批总结 | 当审批结果为驳回时，展示此字段。<br>该条AI审批记录的审批总结。 |
| 审批详情列表 | 序号、规则名称、分析详情、风险等级。<br>同展示在单据详情的审批详情。 |

### **导出**

支持导出当前查询条件下的主表\+审批详情列表字段信息。

导出文件名：AI审批记录-时间戳.xls

导出模板：[AI审批记录导出模板](https://alidocs.dingtalk.com/api/doc/transit?dentryUuid=gwva2dxOW4KpAvQ3t4zKk1YY8bkz3BRL&queryString=utm_medium%3Ddingdoc_doc_plugin_card%26utm_source%3Ddingdoc_doc)


## **AI分析**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0b9JyMJNnw1/img/44b32366-e41f-419f-91c1-9731e5350dca.png?Expires=1775016602&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=F3Xx7u0KV1uZqyX3kDiHJGFn5Cw%3D "")

本期先放个静态页面，敬请期待。AI四期完成这部分内容\+动效。

## **AI异常监控**

本期先放个静态页面，敬请期待。AI四期完成这部分内容。

## **管理后台-新增AI应用开关**

管理后台操作-模块开启/关闭，增加

1、AI应用功能开关。该开关控制用户是否购买了AI应用模块，只有购买了在模块开启中才能看到对应AI应用及其下的菜单。

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0b9JyMJNnw1/img/104d9f3a-afd4-425e-9754-1734dab76d5c.png?Expires=1775016602&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=QH7IyLRO6DMAoAYtwyfzl%2Fzlk1w%3D "")

2、模块开启关闭增加AI应用开关。该开关控制：

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0b9JyMJNnw1/img/8bf1127d-fdb7-4e38-99b9-a0e2554bb275.png?Expires=1775016602&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=s%2FEbhadGIga2xWEEoAt0Y%2BLnUfk%3D "")

3、菜单上AI应用及AI审批菜单的展示。

4、审批流节点上能否新选择AI审批节点。历史已经选择的依然能够看见，但新提交的单据若走的审批流中包含AI审批节点，则会提交失败。提示“审批流中包含AI审批节点，请联系管理员”

5、系统设置-角色与权限中：

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0b9JyMJNnw1/img/90c8dbc3-c10d-4041-a497-e96858c9a06f.png?Expires=1775016602&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=K0lwXGx8n6%2FZsTdLgB%2Bd3wA%2Btrw%3D "")
- 功能权限是否展示该模块。
    - 启用时，默认权限处理：
        - 企业下的系统管理员、财务主管给AI应用、AI运行看板、AI审核、AI分析、AI异常监控的功能权限。
    - 若先启用后关闭模块，则之前配置的权限依然保![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0b9JyMJNnw1/img/bdc344cc-ba11-4bd9-8afc-fdf699f32e6d.png?Expires=1775016602&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=F1wB6iBEHy4mC8FfNt%2Fq1ymLyBg%3D "")留，仅前台不做展示。
- 数据权限本期不单独设置，有功能权限的用户可以看到所有数据。

6、待审批单据详情中，“自动打开AI审批记录”开关是否展示。

已经通过AI审批的记录不影响。

## **移动端交互**

见设计稿

## **其他关联影响**

### **AI审批节点后的人工审批节点，审批人的选择对提单的影响**

员工提单的时候后端校验下，如果该单据审批流中出现了AI审批节点的下一个审批/支付节点上，设置审批人为“由审批人选择”，就阻断并提示“AI审批节点后的第一个审批/支付节点（审批节点名称）需要指定审批人，请联系管理员”

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0b9JyMJNnw1/img/d2154628-51ac-4b1e-b162-59caf78820f9.png?Expires=1775016602&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=StmluFJxA9gv64OxzvZ6WZAq%2F0E%3D "")

### **流程效率报表**

AI审批节点和人工审批节点一样，也需要记录节点开始时间（到达节点的时间）、节点结束时间（AI分析完成开始往下个节点流转或驳回的时间）

### 材料

《人工智能生成合成内容标识办法》2025年9月1日起施行，设计页面上需增加标识。


