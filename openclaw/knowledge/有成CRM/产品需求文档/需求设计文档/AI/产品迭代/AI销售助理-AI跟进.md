---
title: "AI销售助理-AI跟进"
nodeId: NZQYprEoWoerzxXOHPPbkp7bJ1waOeDk
workspaceId: R2PmK2Q8rxRbeXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/NZQYprEoWoerzxXOHPPbkp7bJ1waOeDk?utm_scene=team_space"
exportedAt: 2026-03-31T03:50:00.824Z
source: dingtalk-document-mcp
---
| 修订时间 | 版本 | 修订人 | 修订说明 |
|-----------------------------------------------------------------------|-----------------------------------------------------------------|--------------------------------------------------------------------|-----------------------------------------------------------------------|
| 2025-7-3 | v1.0 | 黄艺平 | 新建 |
|  |  |  |  |

## 需求详情

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0bvmpKWGnw1/img/8e9404d4-f79d-41d9-bfd2-037ddf462832.png?Expires=1774934120&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=KZhJueYzKuR32NqwiD0EI2QkiXc%3D "")


| 需求 | 描述 |
|-----------------------------------------------------------------|-----------------------------------------------------------------|
| AI跟进 | 一、支持发起钉钉视频会议：点击按钮，若该用户发起其他会议且未结束，不允许重复发起，toast提示‘您正在正在视频会议中’不存在上述问题，则选择跟进信息--\>发起会议(自动录制)--\>结束会议（结束录制）--\>获取会议基本信息、视频信息、转文本信息备注：跟进对象类型/跟进对象/跟进类型均取跟进记录中对应字段二、设置1. AI会议助理1. 系统预设2个agent（提示词在持续优化中...）2. 企业最多可自定义添加3个agent，达到限制时 【创建助理】按钮隐藏1. 自定义agent的头像（创建时默认给一个，不可以清除，只能更改）、助理名称、技能描述为必填2. AI会议风险预警1. 系统预设1个agent（提示词在持续优化中...）2. 企业最多可自定义添加3个agent，达到限制时 【创建助理】按钮隐藏3. 启用一个agent后，另外一个agent默认禁用4. 调试中，不会发送消息5. 消息提醒1. 可勾选会议发起人‘员工本人’（默认勾选）2. 若勾选了‘员工本人’，可选择提醒员工各级主管3. 可选择通知自定义人员3. 展示时段1. 规则中的开始、结束时间必填，未填写时保存失败并toast提示‘展示时段规则设置中的开始、结束时间必填’2. 时间选择的分钟选择，只能选择00 15 30 45 ，即不能选择例如9:113. 备注：系统上线时，默认配置为09:00～18:00![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0bvmpKWGnw1/img/d6eb3d2e-f128-4489-9226-08163a6973cd.png?Expires=1774934120&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=s7bjqi83s0X5xlJJ5R10tdDdUjI%3D "")4. 生成单据1. 自动生成跟进1. 默认关闭2. 开启时，必须选择模板三、筛选左上角展示选人组件（依据用户角色设置中的‘其他数据权限’，同目标管理）四、列表展示1. 人员：依据人员组件筛选范围2. 时间段：依据设置-展示时段~~1）第二个拼接部分开始时间要展示，即13:30这一条线要展示~~~~2）第一个部分与第二个部分拼接处，用蓝色线标记，中间有间隔（能展示出时间信息即可）~~![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0bvmpKWGnw1/img/b02f4e4b-bd1e-4e55-81c9-8aac6c107abd.png?Expires=1774934120&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=cPYg2ab1htfpLoLi0NcLu5CB%2FPk%3D "")3. 卡片信息1. 展示字段信息1. 视频会议主题名称2. 会议时长（天、时、分）3. 依据‘判断依据’设置，获取到的提示信息（若有）2. 卡片颜色：若有获取到提示信息，则展示为红色，否则为绿色五、详情1. 参会人员：只展示实际参会人员的信息，展示如下信息1. 参会人员头像（外部人员则默认头像，如图）2. 参会人员昵称3. 是否是所属企业内成员（是的话展示‘内’标记）4. 入会时间～离会时间2. 关联跟进5. 展示手动/自动生成的跟进信息6. 自动生成跟进记录，存在部分必填字段未填写，则暂存为草稿（跟进记录列表不展示）3. 【生成跟进】7. 若已关联跟进（草稿或者非草稿），该按钮隐藏 |
| 跟进记录 | 一、列表：增加一列展示关联的ai会议（仅钉钉平台 且 应用开关中ai会议为开启的）二、详情：增加展示关联的ai会议（仅钉钉平台 且 应用开关中ai会议为开启的） |
| 应用开关 | 增加‘Ai跟进’应用开关，新旧企业均默认开启（仅钉钉企业）![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0bvmpKWGnw1/img/0caf2beb-6de5-4afd-b425-16a839d4a96a.png?Expires=1774934120&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=aH1M0mgdAKS8wxtQ5B44kICGb5k%3D "") |
| 角色设置 | 增加如下功能权限（仅钉钉企业）AI会议的功能权限，上线时仅角色‘crm管理员’刷上（新旧企业均是）![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0bvmpKWGnw1/img/f2d60ecc-e6c7-4168-9e6f-f97d89234c90.png?Expires=1774934120&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=04yyqcwplStxTDGI8F3QWHG2P44%3D "") |
