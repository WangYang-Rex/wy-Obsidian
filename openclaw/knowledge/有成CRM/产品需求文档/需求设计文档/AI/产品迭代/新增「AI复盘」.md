---
title: "新增「AI复盘」"
tags:
  - 有成CRM
  - PRD
  - 需求设计文档-AI-产品�
created: 2026-03-24
source: 钉钉文档
original_url: https://alidocs.dingtalk.com/i/nodes/jb9Y4gmKWr7lmxrahpKAQLDPVGXn6lpz?utm_scene=team_space
node_id: jb9Y4gmKWr7lmxrahpKAQLDPVGXn6lpz
exported_at: 2026-03-22
---

# 新增「AI复盘」

> 🔗 **原文链接**：[新增「AI复盘」 - 钉钉文档](https://alidocs.dingtalk.com/i/nodes/jb9Y4gmKWr7lmxrahpKAQLDPVGXn6lpz?utm_scene=team_space)

| 修订时间 | 版本 | 修订人 | 修订说明 |
|-----------------------------------------------------------------------|-----------------------------------------------------------------|--------------------------------------------------------------------|-----------------------------------------------------------------------|
| 2025-11-6 | v1.0 | 黄艺平 | 新建 |
|  |  |  |  |

## 需求详情

| 需求 | 描述 |
|-----------------------------------------------------------------|-----------------------------------------------------------------|
| 角色设置 | 1、AI助理设置
原先在「AI会议」分组下，改为独立一个组
2、增加「AI复盘」、「~~AI视图管理」~~分组及权限
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/8K4nyeZxJ3223nLb/img/ec2766d3-9740-49df-b63b-ffe9b32e6996.png?Expires=1774165013&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=kyROsyhcuYFN1dt3TpVemnWGSgk%3D "") |
| 「AI复盘」列表 | 一、客户、销售机会、工单、项目、线索模块，增加预设字段（均为系统默认回刷字段，新建编辑不可见）
- 1. 最近AI会议时间：日期时间类型
- 2. 最近AI会议方式：单选类型，取公共字典值
- 3. AI复盘风险类型：单选类型，选项值‘未分析’‘无分析数据’‘又风险’‘无风险’，默认‘未分析’
- 4. 风险摘要：单行文本
二、筛选器
- 对象：客户、销售机会、工单、项目、线索，默认‘客户’
- 场景：同对应对象
- 模板：同对应对象
- 销售机会流程：仅‘销售机会’对象有
- 项目阶段推进流程：仅‘项目’对象
- AI复盘风险类型
二、视图管理
- 功能说明
<li style="margin-left:1em">根据所选对象展示对应视图设置
<li style="margin-left:1em">有「AI视图管理」-「视图设置」权限才有此入口
<li style="margin-left:1em">视图相关配置参考参考需求：[https://gykj.yuque.com/vhho51/asmkvg/oma8rd2p5s00m1ao?singleDoc#](https://gykj.yuque.com/vhho51/asmkvg/oma8rd2p5s00m1ao?singleDoc#)
备注：此视图配置在普通列表也同步存储/展示，ai复盘这里只展示‘AI复盘’这个视图
- 功能上线时默认配置
<li style="margin-left:1em">客户对象
<li style="margin-left:2em">视图名称：AI复盘
<li style="margin-left:2em">可见范围：公开（不可改）
<li style="margin-left:2em">分组字段：客户级别
<li style="margin-left:2em">排序方式：降序
<li style="margin-left:2em">范围设置：-
<li style="margin-left:2em">展示字段：负责人、最近AI会议时间、最近AI会议方式、风险摘要
<li style="margin-left:1em">商机对象
<li style="margin-left:2em">视图名称：AI复盘
<li style="margin-left:2em">可见范围：公开（不可改）
<li style="margin-left:2em">分组字段：销售机会阶段
<li style="margin-left:2em">排序方式：降序
<li style="margin-left:2em">范围设置：-
<li style="margin-left:2em">展示字段：销售机会金额、客户、负责人、最近AI会议时间、最近AI会议方式、风险摘要
<li style="margin-left:1em">工单
<li style="margin-left:2em">视图名称：AI复盘
<li style="margin-left:2em">可见范围：公开（不可改）
<li style="margin-left:2em">分组字段：工单优先级
<li style="margin-left:2em">排序方式：降序
<li style="margin-left:2em">范围设置：-
<li style="margin-left:2em">展示字段：客户、工单状态、最近AI会议时间、最近AI会议方式、风险摘要
<li style="margin-left:1em">项目
<li style="margin-left:2em">视图名称：AI复盘
<li style="margin-left:2em">可见范围：公开（不可改）
<li style="margin-left:2em">分组字段：阶段
<li style="margin-left:2em">排序方式：降序
<li style="margin-left:2em">范围设置：-
<li style="margin-left:2em">展示字段：客户、项目状态、负责人、最近AI会议时间、最近AI会议方式、风险摘要
<li style="margin-left:1em">线索
<li style="margin-left:2em">视图名称：AI复盘
<li style="margin-left:2em">可见范围：公开（不可改）
<li style="margin-left:2em">分组字段：来源
<li style="margin-left:2em">排序方式：降序
<li style="margin-left:2em">范围设置：-
<li style="margin-left:2em">展示字段：线索池、负责人、最近AI会议时间、最近AI会议方式、风险摘要
三、搜索框：同对应对象
四、卡片内容
- 主键字段
- 展示字段配置
五、卡片颜色及标签
- 对应单据，无AI复盘风险提示类AI执行分析 or 无可分析的数据来源，则为灰色
- 对应单据，有AI复盘风险提示类AI执行分析 and 有可分析的数据来源  and 分析结果为有风险，则为红色，且有‘风险’的标签
- 对应单据，有AI复盘风险提示类AI执行分析 and 有可分析的数据来源  and 分析结果为无风险，则为蓝色
六、前端埋点
- pc查看：10790.16098.16100.93873.94143.94144
- ~~mb查看：10790.16098.16101.93916.94146.94147~~
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/8K4nyeZxJ3223nLb/img/63cc974e-e3a1-40c8-956e-520b74777adf.png?Expires=1774165013&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=zSQAZ5g5p4BOeXvrSTOYXV3aORY%3D "") |
| AI助理设置 | 一、AI复盘总结类助理
- 1. AI助理列表：对应AI展示‘适用模块’信息
- 2. 功能上线时：将预设2个启用的助理
<li style="margin-left:1em">1. AI跟进总结
假设你是资深销售专家，请依据下面要求，进行跟进总结：
**核心分析维度**
- **沟通节奏分析**
<li style="margin-left:1em">计算平均沟通间隔周期，识别沟通频率异常波动（突增/突减）的时间节点
<li style="margin-left:1em">统计不同会议方式的占比分布，分析沟通渠道偏好变化
- **客户需求挖掘**
<li style="margin-left:1em">提取并量化客户提及的核心需求关键词（按出现频次排序）
<li style="margin-left:1em">追踪关键需求点的演变轨迹，标注需求新增/变更/删除的具体沟通记录
<li style="margin-left:1em">识别客户未明确表达但隐含的潜在需求（基于上下文推断）
- **风险趋势研判**
<li style="margin-left:1em">构建风险变化时间轴，关联风险出现/解除与特定沟通内容的关系
<li style="margin-left:1em">分析高风险沟通中的客户异议类型及我方应对效果
<li style="margin-left:1em">预测未来30天内的风险概率变化趋势（需说明预测依据）
- **决策信号捕捉**
<li style="margin-left:1em">识别客户提及的决策流程、决策人、预算范围等关键信息
<li style="margin-left:1em">标记可能影响决策的外部因素（竞品动态/行业政策/内部调整）
<li style="margin-left:1em">判断当前所处销售阶段及下一步推进障碍
**特别注意事项**
- 所有分析结论需标注数据来源（格式：\[沟通日期\] - 记录ID:XXX）
- 区分客观事实陈述（如"客户提及预算有限"）与推测性判断（如"可能选择竞品"需注明"推测"）
- 当不同沟通记录中的信息存在矛盾时，需并列呈现并标注矛盾点
- 对于超过3个月未更新的需求信息，需特别标注"信息时效性待确认"
**分析约束条件**
- 严格基于提供的对话原文进行分析，不得引入外部知识库信息
- 风险评估需保持保守倾向，对模糊表述应按"存在潜在风险"处理
- 避免使用营销话术，所有结论需采用中性客观的表述方式
**输出格式要求**
仅使用纯文本输出分析结果（不使用表格/列表/Markdown格式），字数严格控制在200字以内。
<li style="margin-left:1em">2. AI行动建议
假设你是资深销售专家，请依据下面要求，生成下一步行动建议：
**核心分析维度**
- **沟通节奏分析**
<li style="margin-left:1em">计算平均沟通间隔周期，识别沟通频率异常波动（突增/突减）的时间节点
<li style="margin-left:1em">统计不同会议方式的占比分布，分析沟通渠道偏好变化
- **客户需求挖掘**
<li style="margin-left:1em">提取并量化客户提及的核心需求关键词（按出现频次排序）
<li style="margin-left:1em">追踪关键需求点的演变轨迹，标注需求新增/变更/删除的具体沟通记录
<li style="margin-left:1em">识别客户未明确表达但隐含的潜在需求（基于上下文推断）
- **风险趋势研判**
<li style="margin-left:1em">构建风险变化时间轴，关联风险出现/解除与特定沟通内容的关系
<li style="margin-left:1em">分析高风险沟通中的客户异议类型及我方应对效果
<li style="margin-left:1em">预测未来30天内的风险概率变化趋势（需说明预测依据）
- **决策信号捕捉**
<li style="margin-left:1em">识别客户提及的决策流程、决策人、预算范围等关键信息
<li style="margin-left:1em">标记可能影响决策的外部因素（竞品动态/行业政策/内部调整）
<li style="margin-left:1em">判断当前所处销售阶段及下一步推进障碍
**特别注意事项**
- 所有分析结论需标注数据来源（格式：\[沟通日期\] - 记录ID:XXX）
- 区分客观事实陈述（如"客户提及预算有限"）与推测性判断（如"可能选择竞品"需注明"推测"）
- 当不同沟通记录中的信息存在矛盾时，需并列呈现并标注矛盾点
- 对于超过3个月未更新的需求信息，需特别标注"信息时效性待确认"
**分析约束条件**
- 严格基于提供的对话原文进行分析，不得引入外部知识库信息
- 风险评估需保持保守倾向，对模糊表述应按"存在潜在风险"处理
- 避免使用营销话术，所有结论需采用中性客观的表述方式
**输出格式要求**
使用列表输出分析结果，整体字数严格控制在200字以内，每条行动建议不超过30个字
\- \[行动建议1\]   
\- \[行动建议2\]
- 3. AI助理增加一个操作按钮【全量分析】
<li style="margin-left:1em">3. 该企业限制1天只能全量分析1次，超出则toast提示‘企业1天只能操作全量分析1次，请明天重试’
<li style="margin-left:1em">4. 该企业、该AI助理已有在运行中的分析任务，不支持全量分析，toast提示‘该助理已有在运行中的分析任务，不支持全量分析，请稍后重试’
<li style="margin-left:1em">5. 无上述情况，弹窗提示，点击【确认】执行全量分析
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/8K4nyeZxJ3223nLb/img/aa3535e2-a631-401d-91fb-a733e9a4057a.png?Expires=1774165013&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=FqTbyQTeYWKvj%2FczBtI52UZAUJU%3D "")
- 4. 设置
<li style="margin-left:1em">6. 增加‘适用模块’选项，单选，必填，可选客户、销售机会、工单、项目、线索
<li style="margin-left:1em">7. 分析数据来源：选项‘AI会议记录’、‘跟进记录’，默认‘AI会议记录’，本期不可变更选项
<li style="margin-left:1em">8. 分析数据条数：选项‘最近1条’‘最近3条’‘最近5条’‘最近10条’，默认‘最近1条’
<li style="margin-left:1em">9. 预览调试数据：根据所选适用模块，选择对应对象数据，不校验数据权限（保存设置后，对话框中发送任意文字如‘调试’即可查看分析结果）
- 5. 该类型助理企业可自定义3个
- 6. 该类型助理支持全部启用
- 7. 前端埋点
<li style="margin-left:1em">10. 新建（10790.16098.16100.93873.93893.94129.94131）
<li style="margin-left:1em">11. 编辑（10790.16098.16100.93873.93893.94129.94132）
<li style="margin-left:1em">12. 禁用（10790.16098.16100.93873.93893.94129.94133）
<li style="margin-left:1em">13. 启用（10790.16098.16100.93873.93893.94129.94134）
<li style="margin-left:1em">14. 删除（10790.16098.16100.93873.93893.94129.94135）
<li style="margin-left:1em">15. 全量分析（10790.16098.16100.93873.93893.94129.94136）
二、AI复盘风险提示类助理
- 1. AI助理列表：对应AI展示‘适用模块’信息
- 2. 功能上线时：将预设1个启用的助理
<li style="margin-left:1em">1. 风险提示
你是一名资深销售专家，你负责将历次会议的内容按照如下要求进行总结提炼，并识别本次沟通中的流失预警信号：
A. 有风险（卡片变为红色）：若按分析维度得出情绪积极性评分\+流失意图评分\+负面关联动态评分\>18分，则判断为有风险，且需要按‘二、输出规则’的要求展示提取到的结果；
B. 无风险：若按分析维度得出情绪积极性评分\+流失意图评分\+负面关联动态评分≤18分，则判断为无风险，且需要按‘### 输出规则’的要求展示提取到的结果；
分析维度
1、负面情绪评分（1-10分）
•识别负面情绪词汇（如"不满意""太贵""不够高效"）及强度
•检测负面情绪词汇占比（负面情绪词汇/（积极词汇\+负面情绪词汇）），一旦负面情绪词汇占≥70%，则触发负面情绪评分\>7分
2、流失意图评分（1-10分）
•需求弱化类：频繁使用暂时不需要""再考虑""再看看""不确定’’"不着急""可以推迟”’’预算紧张’’等回避性措辞，或对关键问题回答含糊其辞，或不再追问产品核心功能细节，转而询问边缘性服务条款，或不再主动分享业务痛点，对个性化解决方案无兴趣
•竞品提及类："XX家的功能更好"
•退款流程询问类：突然询问’’退款需要什么手续""如果更换供应商需要哪些流程"等过渡性问题，流失意图评分权重较大，一旦提及则流失意图评分\>7分
3、负面关系评分（1-10分）
•决策者参与度下降标记（如"需要向上级汇报""需要讨论"频次增加），转接非相关人员沟通
•非承诺性回应计数（"可能""再说吧"出现≥5次触发评分\>7分）
输出内容格式要求
**风险等级**   🔴 高危（负面情绪评分\+流失意图评分\+负面关联评分\>21分，或者流失意图评分\>9分）  
🟠 中危（负面情绪评分\+流失意图评分\+负面关联评分\>18分，或者流失意图评分\>7分）  
🟢 正常
**判断依据**   展示各分析维度评分、评分依据（每条依据内容不超过30个字）、总分（按以下格式分行展示）：
- **负面情绪评分**：\[分数\]分 
<li style="margin-left:1em">\[具体依据1，如负面词汇举例\]
<li style="margin-left:1em">\[具体依据2，如负面情绪词汇占比值\]
- **流失意图评分**：\[分数\]分 
<li style="margin-left:1em">\[具体依据1，如流程询问类证据\]
<li style="margin-left:1em">\[具体依据2，如竞品提及/需求弱化证据\]
- **负面关系评分**：\[分数\]分 
<li style="margin-left:1em">\[具体依据1，如决策者参与度变化\]
<li style="margin-left:1em">\[具体依据2，如非承诺性回应计数\] 
总分：\[负面情绪分\]\+\[流失意图分\]\+\[负面关系分\] = \[总分\]分
示例输出
**风险等级**  🟠 中危
**判断依据**
- **负面情绪评分**：7分 
<li style="margin-left:1em">检测到客户使用"太贵""预算不够"等负面情绪词汇8次
<li style="margin-left:1em">负面情绪词汇占比高（90%），满足负面情绪评分\>7分条件
- **流失意图评分**：9分 
<li style="margin-left:1em">询问"退款流程...违约金"，符合退款流程询问类，流失意图评分\>7分
<li style="margin-left:1em">表达""内部在测试xx家的系统"，显示竞品迁移行动
- **负面关系评分**：5分 
<li style="margin-left:1em">表示"得跟股东们商量"，决策者参与度下降
<li style="margin-left:1em">非承诺性回应如"再说吧""可能吧"出现2次 
总分：7 \+ 9 \+ 5 = 21分 \> 18分，满足中危条件
- 3. 增加一个操作按钮【全量分析】，同上
- 4. 设置
<li style="margin-left:1em">2. 增加‘适用模块’选项：同上
<li style="margin-left:1em">3. 分析数据来源：同上
<li style="margin-left:1em">4. 分析数据条数：同上
<li style="margin-left:1em">5. 预览调试数据：同上
- 5. 该类型助理企业可自定义4个
- 6. 该类型助理支持最多启用1个，某个启用之后其他启用的助理均要自动禁用
- 7. 前端埋点
<li style="margin-left:1em">6. 新建（10790.16098.16100.93873.93893.94130.94137）
<li style="margin-left:1em">7. 编辑（10790.16098.16100.93873.93893.94130.94138）
<li style="margin-left:1em">8. 禁用（10790.16098.16100.93873.93893.94130.94139）
<li style="margin-left:1em">9. 启用（10790.16098.16100.93873.93893.94130.94140）
<li style="margin-left:1em">10. 删除（10790.16098.16100.93873.93893.94130.94141）
<li style="margin-left:1em">11. 全量分析（10790.16098.16100.93873.93893.94130.94142）
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/8K4nyeZxJ3223nLb/img/a250b9e5-a2ea-46e7-9ebf-586f9ebf29be.png?Expires=1774165013&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=RZYmONz6J0TZtN9mlVsJ2j23VW0%3D "") |
| 分析结果详情 | - 1. 客户、销售机会、工单、项目、线索均增加展示‘AI销售助理’模块
<li style="margin-left:1em">1. 开了AI销售助理模块才展示
- 2. 总体分析
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/8K4nyeZxJ3223nLb/img/22f4818f-5751-4e3f-b1bf-9ea254054bc6.png?Expires=1774165013&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=A5e3LmDkily69D4lTsRM%2FNzfayI%3D "") |
| 应用中心 | 新增「AI复盘」应用开关
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/8K4nyeZxJ3223nLb/img/f6e147c0-2a25-4490-a5dc-70737ed07296.png?Expires=1774165013&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=fQxNaFGKFiyWbHQ%2FvciR93NBM9M%3D "") |
