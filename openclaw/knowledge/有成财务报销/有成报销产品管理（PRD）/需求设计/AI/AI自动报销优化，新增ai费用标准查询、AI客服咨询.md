---
title: "AI自动报销优化，新增ai费用标准查询、AI客服咨询"
nodeId: QG53mjyd80Rjq0QOCQ4NNnP7V6zbX04v
workspaceId: R2PmK2gngjVnZXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/QG53mjyd80Rjq0QOCQ4NNnP7V6zbX04v?utm_scene=team_space"
exportedAt: 2026-04-01T02:10:02.857Z
source: dingtalk-document-mcp
---
| 修订时间 | 版本 | 修订说明 |
|------------|------|------------|
| 20250730 | v1.0 | 新建 |
| 20250905 | v2.0 | 调整 |
| 20251010 | v2.1 | 优化：<br><ul><li>☑ 重新登录依然保留对话、引导用户通过新建对话重新建单——2@吴靖(岱宗-吴靖)</li><br><li>☑ 首页增加“去报销”入口——5</li><br><li>☑ 支持发票和消费混合提交场景——3</li><br><li>☑ 自动计算补贴——1</li><br><li>☐ 生成单据兼容单据模板上配置的填写逻辑（辅助核算带出上一次选项）——7</li><br><li>☑ 支持企业级智能填单规则——4@吴靖(岱宗-吴靖)</li><br><li>☑ 咨询费用标准，支持其他标准——0@吴靖(岱宗-吴靖)</li><br><li>☑ 自动带入单据申请人（暂不支持委托报销场景，v4.3优化）——6</li></ul> |

# **1\. 需求背景**

## **历史需求**

[有成报销AI需求](https://alidocs.dingtalk.com/i/nodes/jb9Y4gmKWr7lmxrahaKO93mEVGXn6lpz?utm_scene=team_space)
目前已上线：
- rag有成报销产品手册
- 上传发票-生成费用（会自动保存发票、费用）-单据带入消费明细组件

## **业务场景**
    1. 用户期望通过与ai交互，完成附件上传-整理-提报销单的完整流程。目前单据字段需要用户一个个手填，填写成本比较高。
    2. 业务员在出差时，希望能够询问ai自己的报销标准，不需要问财务也不需要单独打开企业制度文档查询。
    3. 后续有成报销内会深度融合ai能力，需要设计好ai融合的框架、交互形式。

## **技术实现**

线上ai助手用的智能体搭建平台为阿里百炼。限制一个业务空间上传的知识库文档不能超过10万份。

[大模型服务平台百炼控制台](https://bailian.console.aliyun.com/?switchAgent=11550323&productCode=p_efm&switchUserType=3&tab=api#/api/?type=app&url=https%3A%2F%2Fhelp.aliyun.com%2Fdocument_detail%2F2834219.html&renderType=iframe)

## **产品规划**

![ai流程蓝图.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/a2QnV4jEypd6DO4X/img/6d007ddc-9dce-46b7-9372-1b85cc4d1317.png?Expires=1775016603&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=kFD5zF5dHpwUqw0XaETQdZTD6xA%3D "")

[https://m3.mockplus.cn/preview/BtSpvnQ1S6yJ](https://m3.mockplus.cn/preview/BtSpvnQ1S6yJ)

## **需求拆解**

1、提供给用户简介、智能、丝滑的**首次**使用ai体验➡️引导、功能露出给零体验用户

2、提供给**使用过**一次的用户，快速使用的路径

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/a2QnV4jEypd6DO4X/img/b5984b89-a649-4fc9-ba01-1d6d4e4dfad4.png?Expires=1775016603&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=VG%2FmZnMPrC7Af%2Bh89Se9SA6Gkeo%3D "")

# **2\. 业务流程/架构**

[白板]



# **3\. 功能清单**

| 模块 | 功能点 | 备注 |
|------|---------|------|
| 报销ai | 交互框架优化，场景分流、快速入口 |  |
|  | 通用场景Agent优化 |  |
|  | 报销助手Agent优化 |  |
|  | 新增查询费用标准Agent |  |
|  | 在线客服Agent优化 |  |

# **4\. 需求详情**

## **ai交互框架搭建**

### **交互形式**

pc：浮窗改分屏

mb：全屏遮罩改80%高度拉起

### **agent场景分流**

通用agent内增加场景分流（埋点）

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/a2QnV4jEypd6DO4X/img/83b35a5c-81bd-41ad-b483-c85f3a1e4354.png?Expires=1775016603&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=l6o2yPA5NOxj6RZnGInUWO4l4Aw%3D "")
- 帮我报销，点击后ai助理由通用场景自动切换到“帮我报销”场景，后续会话由**报销助手agent**接管（以后可拓展为由企业提供agent接管会话）。流程见[二期：AI自动报销优化，新增ai费用标准查询、AI客服咨询](https://alidocs.dingtalk.com/i/nodes/Y1OQX0akWm3gpzNXTYzgQRvGJGlDd3mE?utm_scene=team_space&iframeQuery=anchorId%3Duu_mdppuk5ofu7ynobh2gc)

- 查询费用标准。点击后自动切换到“查询费用标准”场景，后续会话由**查询费用标准agent**接管（以后可拓展为由企业提供agent接管会话）。流程见[二期：AI自动报销优化，新增ai费用标准查询、AI客服咨询](https://alidocs.dingtalk.com/i/nodes/Y1OQX0akWm3gpzNXTYzgQRvGJGlDd3mE?utm_scene=team_space&iframeQuery=anchorId%3Duu_mdppuz727uj2301e6e)

- ai客服。点击后自动切换到“ai客服”场景，后续会话由**在线客服agent**接管。流程见[二期：AI自动报销优化，新增ai费用标准查询、AI客服咨询](https://alidocs.dingtalk.com/i/nodes/Y1OQX0akWm3gpzNXTYzgQRvGJGlDd3mE?utm_scene=team_space&iframeQuery=anchorId%3Duu_mdr1m047gflusp666uo)

- 支持分agent统计会话数、消息数、单轮会话时长。

### **首页增加“去报销”入口**

白名单内企业在首页设置可见模块中可见“去报销”开关，默认开启。开启后首页新增“去报销”入口。

### ![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1wvqreb7VQ9o2nak/img/a92f7ea3-f067-4809-9bc5-c98faa2c7c34.png?Expires=1775016603&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=ziFTO4TSjvKeL0vQWoPdbIk1uWk%3D "")

用户点击“去报销”入口，自动打开ai助理侧边栏。
- 用户已经有过历史对话的，打开历史会话。
- 用户没有过历史会话的，创建会话并自动定位到帮我报销Agent，抛出卡片并自动切换到“帮我报销”后续流程同用户主动在ai助理侧边栏中点击“帮我报销”。

“去报销”入口记增加前端埋点，统计pv、uv。

### **其他细节元素调整**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/a2QnV4jEypd6DO4X/img/56bf7d1a-76e0-49b1-8a32-f83c06d5c92b.png?Expires=1775016603&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=RDvTEk4syg9YIiq%2BIT7AxIbPU8A%3D "")
- 关闭改收起
- 新对话改为清空
- 新功能提醒气泡，关闭后不显示

### **按照用户记录会话**

背景：报销过程中，移动端用户可能会切出应用进行其他操作，目前重新登录就视作新对话会导致报销中断。

按照用户维度记录会话，即便用户重新登录，打开对话依然展示历史的会话。

## **通用场景Agent优化**

### **配置**

欢迎语：你好！我可以帮你快速报销，查询费用标准、解答软件操作疑问等等，请告诉我你的问题吧！

常用问题：
1. 如何实现批量支付？
2. 如何自动生成财务凭证？
3. 如何查看项目利润表？

### **流程**

提示语抛出后根据用户首条消息进行意图识别，分流到具体agent下。

意图识别以在线客服Agent兜底。

~~特殊逻辑：~~

~~1、当用户消息为“提些建议”时，不分流~~

~~通用场景agent回复“请一句话描述您的建议，我将不断优化😊”，后台采集用户的下一句消息。记录用户所在企业、用户名称、联系方式、具体消息内容。~~

~~用户发出消息后，agent回复“我们已经记录下您的反馈，感谢您对产品的支持！”。~~

## **报销助手Agent优化**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1wvqreb7VQ9o2nak/img/67c139db-ecd7-46ba-9b05-3de4b64914a4.png?Expires=1775016603&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=%2Fu0ee80tay9ifkz7K53ADOV%2BsC8%3D "")

### **流程**
1. 用户发送文字，也可以文字\+附件
    1. 卡片交互：
        1. 点击选择消费，弹出选择消费弹框，用户选择消费后带入到下方对话框中
        2. 点击上传发票，弹出上传文件弹框，用户选择发票后带入到下方对话框中
        3. 点击消息发送，将用户选择的发票和消费执行后续逻辑。
    2. 下方的输入框中直接文字说明\+上传
    3. 下方的输入框需要支持语音录入
2. 增量附件中存在发票的情况下发票校验
    4. 存在校验不通过的，文案提示用户
        4. ~~卡片交互：重走流程，重走流程时可以选择已有发票；~~
        5. ~~卡片交互：过滤掉有问题发票，继续报销~~
    5. 附件校验全部通过的，继续流程
3. 结合文字和全部附件判断报销类型是否为差旅报销
    6. 是差旅报销的，整理行程~~让用户核对~~并输出行程
> 判断要求告诉给ai，具体规则可以由ai基于合理性判定，我们要求输出结果即可。校验行程是否有问题的核心逻辑是：**发票信息需形成 “时间连续、地点衔接、类型匹配、金额合理” 的完整链条**。   
> 以下是规则示例：   
> 判断行程本身是否有误的标准有：   
> 最早行程的出发地和最晚行程的目的地一致，不含员工常驻地。   
> 按照时间排序的行程城市前后衔接。例如前一天目的地还在上海，后一天出发地变成北京，这种属于不衔接。   
> 禁止出现 “同一时刻在两个地点消费” 的矛盾，例如：   
> 8:00 北京某餐厅的餐饮发票 \+ 8:30 上海某酒店的住宿发票（北京到上海最快高铁需 4.5 小时，时间无法衔接）。   
>    
> 判断行程发票是否完整的标准有：   
> 行程跨日，是否有住宿费发票   
> 跨城市，至少有飞机、火车、交通费其中一项   
    7. 不是差旅报销的，不用输出行程，继续流程
4. 预生成全部费用，根据费用、行程自动生成所有可选补贴。生成逻辑：
    8. 读费用标准中的补贴标准，已启用的、**开启了自动计算**的才计算补贴。没有匹配的补贴标准直接跳过这个环节。
    9. 根据AI生成的行程和费用计算补贴。由AI来判断是否已有补贴无需生成。
    10. 生成补贴的费用类型读控制费用标准中的费用类型。
    11. 生成补贴的日期由AI匹配行程生成。
    12. 生成补贴的金额根据不超过费用标准的最大金额计算。即走费用标准查询agent的逻辑查询出补贴的金额。
5. 费用入库，创建单据草稿。
    13. **生成单据草稿需要兼容单据模板上配置的填写逻辑****。**加载单据模板，根据默认填充规则初始化➡️带入前面生成的费用，**若单据中有行程组件还需带入行程。**➡️根据单据配置的规则，用AI分析并尽量填写剩余必填内容
    14. 判断是否能直接提交
        6. 单据必填字段未齐全，提示用户哪些字段未齐全。用户可以对话补充或者点击去单据详情补充，每次对话后都需要重新触发必填字段校验。
        7. 单据必填字段已经齐全了，用户可以点击去提交，左侧打开单据详情。
        8. 如果用户点击去提交时，单据已经提交了，提示语：单据已提交，可以点击AI助理左上角“新对话”提交新的单据哦

### **配置**

欢迎语：

1、你好，请直接上传发票或选择已有发票

2、自动发送一张**上传发票卡片**。交互见后审批

### **支持企业级提示词**

之前我们已经支持了系统级的提示词管理，但针对生成费用匹配规则、填单规则，企业根据各自业务要求不同，会存在企业级定制的规则。

提示词管理工具支持维护**报销各环节的agent**企业级提示词，以变量形式传入到agent系统提示词中。
- 生成费用agent
- 整理行程agent
- 生成单据草稿agent

系统提示词中增加描述“当企业级规则和通用规则存在矛盾时，**优先遵循企业级规则。**”

运维可以在管理后台配置企业级提示词。
```
默认消费事由填写“出差”；
```

## **新增查询费用标准Agent**

### **流程**

用户发送查询我的费用标准，系统根据当前用户登录信息，查询费用标准模块，匹配员工的费用各项费用标准。
- 涉及到费用标准多维度的，把该项费用标准下的多维度都展示。例如客户标准根据客户标签设置了，那么把多个标签的规则都展示出来。根据用户权限做过滤。
- 其中，按天的不需要分析用户历史单据，仅返回费用标准额度本身即可。
- 需要支持其他标准。

### **配置**

欢迎语：你好，我可以帮你查询你的费用标准。

常用问题：查询我的费用标准

## **在线客服Agent优化**

### **流程**

线上效果即可，分流到单独的agent中。

### **配置**

欢迎语：你好，有任何软件操作上的问题可以咨询我

知识库：有成报销产品操作手册、**营销材料、常见问题库**

常用问题：
1. 如何实现批量支付？——对接银企直联
2. 如何自动生成财务凭证？
3. 如何查看项目利润表？
4. 如何搭建自定义报表？
5. 打印效果不满意，如何调整？

## **移动端交互**

移动端的逻辑是一样的，卡片唤起的已有交互样式需要适配移动端。






