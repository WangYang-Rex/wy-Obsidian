---
title: "对接蚂蚁企信AI拓客助手/AI招投标"
tags:
  - 有成CRM
  - PRD
  - 需求设计文档-AI-产品�
created: 2026-03-24
source: 钉钉文档
original_url: https://alidocs.dingtalk.com/i/nodes/R1zknDm0WR3ey6R2T24PoepxVBQEx5rG?utm_scene=team_space
node_id: R1zknDm0WR3ey6R2T24PoepxVBQEx5rG
exported_at: 2026-03-22
---

# 对接蚂蚁企信AI拓客助手/AI招投标

> 🔗 **原文链接**：[对接蚂蚁企信AI拓客助手/AI招投标 - 钉钉文档](https://alidocs.dingtalk.com/i/nodes/R1zknDm0WR3ey6R2T24PoepxVBQEx5rG?utm_scene=team_space)

| 修订时间 | 版本 | 修订人 | 修订说明 |
|-----------------------------------------------------------------------|-----------------------------------------------------------------|--------------------------------------------------------------------|-----------------------------------------------------------------------|
| 2026-2-25 | v1.0 | 黄艺平 | 新建 |
|  |  |  |  |

## 需求详情

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbbEowQ3Om9/img/2160f9e0-6c29-4600-9367-efbbb672e218.png?Expires=1774165005&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=29aKy6DkpLP3PIb1pAvCmwaorZg%3D "")

| 需求 | 描述 |
|-----------------------------------------------------------------|-----------------------------------------------------------------|
| 新增「AI拓客助手」/「AI招投标」模块 | 一、应用开关中增加「AI拓客助手」/「AI招投标」开关（默认均为开）
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbbEowQ3Om9/img/36c680f2-9172-4cc9-ac08-16eddec1ff6f.png?Expires=1774165005&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=JNY8TNZ5cG4pJRlF6sAyk0bvEXk%3D "")
二、功能权限
增加如下功能权限，功能上线时：
- 历史企业：默认所有角色均勾选此功能权限
- 新企业：系统预设角色，均默认勾选此功能权限
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbbEowQ3Om9/img/8e77ed1d-3061-4a6b-a094-012b80f0e132.png?Expires=1774165005&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=ziJedTY4bkCP2Lp1neeDRt7VwRQ%3D "")
三、菜单排序（仅PC端）
- 新企业：依次默认排在客户下方
- 旧企业：默认排在最后（设置上方）
~~备注：菜单设置中不展示上述两个菜单~~
四、开通并使用「AI拓客助手」
1、企业未开通「AI拓客助手」
- 点击【XXX协议】可应用内弹窗预览查看协议内容
- 点击【开通试用「AI拓客助手」】，为企业自动创建试用订单
<li style="margin-left:1em">运营后台
<li style="margin-left:2em">企业名称：取当前企业
<li style="margin-left:2em">订单类型：拓客助⼿试用版
<li style="margin-left:2em">订单金额：0
<li style="margin-left:2em">购买账号数：2
<li style="margin-left:2em">购买年限：-
<li style="margin-left:2em">生效时间：取开通时间
<li style="margin-left:2em">失效时间：开通时间\+5天
<li style="margin-left:2em">备注：-
<li style="margin-left:2em">作废状态：未作废
<li style="margin-left:2em">创建人：系统
<li style="margin-left:2em">创建时间：取开通时间
<li style="margin-left:1em">对接企信（通过创建助手会员权益包接口）
<li style="margin-left:2em">外部业务ID？？--蚂蚁一直没答复
<li style="margin-left:2em">服务商ID：RAYCLOUD
<li style="margin-left:2em">商家ID：取企业ID
<li style="margin-left:2em">企信会员产品包：拓客助⼿试⽤版
<li style="margin-left:2em">生效时间：取开通时间
<li style="margin-left:2em">失效时间：开通时间\+5天
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbbEowQ3Om9/img/83e166cd-5858-4780-a31f-ccd83ef937b4.png?Expires=1774165005&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=BvzwPkRjRchY8S%2BbYbcJcqvPdcw%3D "")
2、企业已开通「AI拓客助手」但是服务已到期
- 点击【联系客服】，处理同应用中心-音视频转写-联系充值（依据各平台）
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbbEowQ3Om9/img/fb68cf53-b84b-493d-ba19-3690364e77dc.png?Expires=1774165005&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=uJ651fsfMILKcYZaIoXtJq73X%2B4%3D "")
3、企业已开通「AI拓客助手」但是服务未到期
- 个人鉴权失败（未绑定有效许可），展示如下
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbbEowQ3Om9/img/f8a95fe2-4d27-4e23-a13d-6775f8968771.png?Expires=1774165005&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=7fCZvaKl31nr7iPFLx4Bzje8yWs%3D "")
- 鉴权成功，但个人未授权：需要先授权
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbbEowQ3Om9/img/f593002f-2bef-4b97-8a55-d8bb374d9cf9.png?Expires=1774165005&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=P7qCeC07DKFKFXBqyi3eo5nKDSg%3D "")
- 个人已授权：正常使用
五、开通并使用「AI招投标」
1、企业未开通「AI拓客助手」
- 点击【XXX协议】可应用内弹窗预览查看协议内容
- 点击【开通试用「AI招投标助手」】，为企业自动创建试用订单
<li style="margin-left:1em">运营后台
<li style="margin-left:2em">企业名称：取当前企业
<li style="margin-left:2em">订单类型：招投标助⼿试用版
<li style="margin-left:2em">订单金额：0
<li style="margin-left:2em">购买账号数：1
<li style="margin-left:2em">购买年限：-
<li style="margin-left:2em">生效时间：取开通时间
<li style="margin-left:2em">失效时间：开通时间\+15天
<li style="margin-left:2em">备注：-
<li style="margin-left:2em">作废状态：未作废
<li style="margin-left:2em">创建人：系统
<li style="margin-left:2em">创建时间：取开通时间
<li style="margin-left:1em">对接企信（通过创建助手会员权益包接口）
<li style="margin-left:2em">外部业务ID？？--蚂蚁一直没答复
<li style="margin-left:2em">服务商ID：RAYCLOUD
<li style="margin-left:2em">商家ID：取企业ID
<li style="margin-left:2em">企信会员产品包：招投标助⼿试用版
<li style="margin-left:2em">生效时间：取开通时间
<li style="margin-left:2em">失效时间：开通时间\+15天
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbbEowQ3Om9/img/a4aff139-8490-4ab4-8af3-1aec991b0432.png?Expires=1774165005&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=XI2qoFt2u3KBn2aPuvNf%2FC3Sqj4%3D "")
2、企业已开通「AI招投标」但是服务已到期
- 点击【联系客服购买】，处理同应用中心-音视频转写-联系充值（依据各平台）
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbbEowQ3Om9/img/621cd8a8-59e4-4ba6-8bc6-a9417e460956.png?Expires=1774165005&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=NkeuTTa9NRoVl3JlFULVp7Y712E%3D "")
3、企业已开通「AI拓客助手」但是服务未到期
同拓客助手：先鉴权-\>再看有无授权，上述两个都满足，则进入使用 |
| 运营后台 | 一、运营后台菜单调整，所有增值服务菜单集中在一个一级菜单
二、新增「AI拓客订单」（本期暂不管退款的场景，等待后续企信同步上线）
- 订单类型：新建时可选只有‘拓客助手通用版’，数据库中枚举包含‘拓客助手试用版’（试用版让用户自己在页面开通）
- 购买账号数：只能填写\>=2的正整数，默认=2，不可编辑（置灰）
- 购买年限：下拉选择，可选‘半年’、‘1年’、‘2年’、‘3年’、‘4年’，默认=1年，不可编辑（置灰）
- 生效时间：默认=当前时间，不可编辑（置灰）
- 失效时间：按照生效时间\+购买年限自动计算
备注：此处下单后，需要同步在企信处下单
三、新增「AI招投标订单」---同「AI拓客订单」，不同点如下
- 订单类型：当前只有‘招投标助手通用版’，数据库中枚举包含‘招投标助手试用版’（试用版让用户自己在页面开通）
- 购买账号数：只能填写正整数，默认=2，不可编辑（置灰）
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbbEowQ3Om9/img/7e49e637-2d96-48b8-b361-433666e615b0.png?Expires=1774165005&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=nb9%2B6cvvm7lfCBL0BXqQZBYwN9k%3D "") |
| 「AI招投标」广告弹窗 | 功能上线时，历史所有企业、所有用户弹窗（仅PC端，只弹1次），点击【前往查看】
- 企业「AI招投标」已关闭 或 用户无对应功能权限：按无此功能权限逻辑提示
备注：截止时间是上线之日起\+7天
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbbEowQ3Om9/img/0fc60a0d-47b9-4d6c-9b69-c37c5d7c94a5.png?Expires=1774165005&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=D7q8uWw7OOwZ1EP9yck%2F5ogFIng%3D "") |
| 应用中心 | 一、新增「AI拓客助手」增值服务模块
- 未开通时：点击【申请开通】：处理参照上述广告弹窗中点击【前往查看】
- 使用中/使用到期
<li style="margin-left:1em">判断依据：配置/订单中，订单查询列表中
<li style="margin-left:2em">有生效中的订单（生效时间\<当前时间\<失效时间），则为‘使用中’
<li style="margin-left:2em">有订单但是不存在生效中的订单，否则为‘使用到期’
![d5f42e61a6d6e7651eda0fb6c163b790.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbbEowQ3Om9/img/1ec09bc6-5bf2-48c1-9a25-f2921f006f1c.png?Expires=1774165005&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=cb81zZqrHigQgehJQGCFlHLlJmQ%3D "")
<li style="margin-left:1em">点击【配置/订单】可查看服务配置、订单信息
<li style="margin-left:2em">配置
<li style="margin-left:3em">模块/模板
<li style="margin-left:4em">模块：必填，可选线索/客户/联系人/项目/销售机会，变更模块，清除下述所选模板、字段映射配置
<li style="margin-left:4em">模板：非必填，可清空，依据所选模块选择对应模板
<li style="margin-left:4em">其他
<li style="margin-left:5em">当选择的模块为客户
<li style="margin-left:6em">可勾选信息是否同步至公海（默认不勾选，勾选后所属公海必填）
<li style="margin-left:6em">可选择所属公海，非必填
备注：对应处理逻辑以及？中的文案都如下
所属公海有选择：信息入库时所属公海取配置信息
勾选了同步至公海：信息入库时负责人为空
<li style="margin-left:5em">当选择的模块为线索
<li style="margin-left:6em">可勾选信息是否进入线索池（默认不勾选）
<li style="margin-left:6em">可选择所属线索池，必填
备注：对应处理逻辑以及？中的文案都如下
勾选了同步至线索池：信息入库时负责人为空
<li style="margin-left:3em">字段映射（参考工商查询字段映射逻辑）
<li style="margin-left:4em">拓客助手字段
<li style="margin-left:5em">企业公开联系方式信息列表：展示为字段名‘可信联系方式’，归为‘手机’类型
<li style="margin-left:5em">企业名称：‘单行文本’类型
<li style="margin-left:5em">企业证件号：‘单行文本’类型
<li style="margin-left:5em">相似企业名：数组中企业名做拼接，如‘企业1,企业2’，‘多行文本’类型
<li style="margin-left:5em">相似原因：‘多行文本’类型
<li style="margin-left:5em">购买力分数：‘整数’类型
<li style="margin-left:5em">购买力得分原因：‘多行文本’类型
<li style="margin-left:5em">机会分析：‘多行文本’类型
<li style="margin-left:5em">企业公开法人信息：‘单行文本’类型
<li style="margin-left:5em">匹配度得分：‘整数’类型
<li style="margin-left:5em">推荐理由：‘多行文本’类型
<li style="margin-left:5em">主营列表：数组中主营内容做拼接，‘多行文本’类型
<li style="margin-left:5em">标讯公告名称：：‘单行文本’类型
<li style="margin-left:4em">CRM字段
<li style="margin-left:5em">依据所选模块\+所选拓客助手字段所属类型，展示可选字段
<li style="margin-left:3em">默认配置
<li style="margin-left:4em">模块：客户
<li style="margin-left:4em">模板：默认模板
<li style="margin-left:4em">字段映射
<li style="margin-left:5em">可信联系方式--\>电话
<li style="margin-left:5em">企业名称--\>企业名称
<li style="margin-left:5em">企业证件号--\>统一信用代码
<li style="margin-left:2em">订单
<li style="margin-left:3em">查询该企业在企信中见创建的订单，按生效时时间倒序排列
<li style="margin-left:3em">支持绑定员工
<li style="margin-left:4em">已过期的订单不支持【绑定员工】操作
<li style="margin-left:4em">选择员工-【确定】时，校验所选人员数须\<=该订单购买人数，超出则提示‘当前订单最多可绑定\{购买人数\}人’
<li style="margin-left:3em">备注：企业开通试用后，默认可以绑定2个License，给企信下单并获取到License后，其中一个License默认绑定开通人
![729c515f74194ba718f2d0ffd3d5d054.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbbEowQ3Om9/img/49882684-2a04-4124-9d6b-723c09e73bde.png?Expires=1774165005&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=D8ADSGFUd8bMEbU8UF6%2FLDBFJXk%3D "")
二、新增「AI招投标」增值服务模块
基本同「AI招投标」，区别在
- 配置
<li style="margin-left:1em">字段映射
<li style="margin-left:2em">拓客助手字段
<li style="margin-left:3em">标讯公告名称：‘单行文本’类型
<li style="margin-left:3em">标讯负责人名称：‘单行文本’类型
<li style="margin-left:1em">默认配置
<li style="margin-left:2em">模块：线索
<li style="margin-left:2em">模板：默认模板
<li style="margin-left:2em">~~字段映射~~
<li style="margin-left:3em">~~可信联系方式--\>电话~~
<li style="margin-left:3em">~~企业名称--\>企业名称~~
<li style="margin-left:3em">~~企业证件号--\>统一信用代码~~
- 订单
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbbEowQ3Om9/img/a9b92637-f7ca-4b49-8cad-8db6840c3bb2.png?Expires=1774165005&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=ttIqVAQcg9wRquJF549O2XAhCvQ%3D "") |
| 线索入库 | 一、「AI拓客助手」
依据企业「AI拓客助手」配置
- 选择模板：若配置中，模板有选择，选择模板页面默认选择配置的模板
- 信息入库
<li style="margin-left:1em">依据字段映射配置
<li style="margin-left:1em">负责人取值：若入库时选择进入公海/线索池的，负责人为空；否则，取当前操作人
备注：
- 客户/线索/联系人/项目/销售机会-来源平台中增加枚举值‘企信拓客助手’，信息入库时在该字段中标记信息来源（项目/销售机会对象该字段历史不存在，本次新增）
二、「AI招投标」
依据企业「AI招投标」配置，其他同「AI拓客助手」
备注：所有对象增加字段（隐藏字段），用来记录企信传入的‘入库内容的链接地址’，该字段有值的数据，详情页展示企信的icon，并支持跳转---拓客的链接暂时没有，等他们迭代了之后再存
![8ffb3ef7b071b7c18c5d0d990af968f6.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbbEowQ3Om9/img/dec613c3-2965-4382-9912-2aff9ae9b5ff.png?Expires=1774165005&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=fflsj1vWsycT%2FTJmpO%2FYccJSm5k%3D "") |
| 消息推送 | 接入企信消息订阅，获取到消息后推送至对应用户
点击【查看详情】跳转至「AI拓客助手」/「AI招投标」页面
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbbEowQ3Om9/img/1b4fa7d9-4b5e-465b-b937-1bff118b8f48.png?Expires=1774165005&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=N7einrPnLVAlHMvwEdfNA2pknJY%3D "") |


附：品牌icon ,用于应用中心/应用开关

[标讯助手.zip]

[找客助手.zip]
