---
title: "增加表单AI规则"
tags:
  - 有成CRM
  - PRD
  - 需求设计文档-AI-产品�
created: 2026-03-24
source: 钉钉文档
original_url: https://alidocs.dingtalk.com/i/nodes/N7dx2rn0JbZ9KxGotyyn4ronJMGjLRb3?utm_scene=team_space
node_id: N7dx2rn0JbZ9KxGotyyn4ronJMGjLRb3
exported_at: 2026-03-22
---

# 增加表单AI规则

> 🔗 **原文链接**：[增加表单AI规则 - 钉钉文档](https://alidocs.dingtalk.com/i/nodes/N7dx2rn0JbZ9KxGotyyn4ronJMGjLRb3?utm_scene=team_space)

| 修订时间 | 版本 | 修订人 | 修订说明 |
|-----------------------------------------------------------------------|-----------------------------------------------------------------|--------------------------------------------------------------------|-----------------------------------------------------------------------|
| 2026-1-14 | v1.0 | 黄艺平 | 新建 |
|  |  |  |  |

## 需求详情

| 需求 | 描述 |
|-----------------------------------------------------------------|-----------------------------------------------------------------|
| 增加表单AI规则 | **一、业务模板增加‘AI规则’**
- 1. 增加此模块的对象：<u>同工作流-流程设置-关联对象</u>
- 2. 助理设置
<li style="margin-left:1em">1. 助理操作
<li style="margin-left:2em">1. 新建助理
<li style="margin-left:3em">企业单个对象最多可添加5个助理，超出时【新建助理】按钮消失
<li style="margin-left:3em">新建助理页面
<li style="margin-left:4em">头像：必填
<li style="margin-left:4em">助理名：必填
<li style="margin-left:4em">触发动作：单选，必填，枚举 新增/编辑/删除（<u>默认新增</u>）
<li style="margin-left:4em">规则描述：必填
<li style="margin-left:5em">可插入字段类型：同字段默认值-AI值-插入字段
<li style="margin-left:5em">可插入字段过滤：可以是本表单中设置了默认值-计算公式/AI值、统计字段、计算字段的字段
<li style="margin-left:4em">控制策略：单选，必填，枚举‘强控制’‘弱控制’（<u>默认强控制</u>）
<li style="margin-left:4em">预览调试数据：选填，可选本对象中某条数据（点击【<u>调试</u>】<u>配置页面弹窗提示</u>）
<li style="margin-left:2em">2. 支持编辑/启用/禁用/删除助理（<u>鼠标悬浮展示</u>）
<li style="margin-left:2em">3. 支持拖动卡片调整优先级（<u>分组内拖动</u>）
<li style="margin-left:1em">2. 助理卡片展示如下信息
<li style="margin-left:2em">4. 助理的头像
<li style="margin-left:2em">5. 助理名称
<li style="margin-left:2em">6. 创作者（企业名）
<li style="margin-left:2em">7. 触发动作
<li style="margin-left:2em">8. 控制策略
<li style="margin-left:2em">9. 启用状态
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1GXn45KN3932bqDQ/img/f85582dd-69c7-4d34-8f2c-f59fbd4015dd.png?Expires=1774165007&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=kLrCB5%2BsMkUHj4Djk1%2B3GZ%2FKX%2BY%3D "")
**二、新建/编辑/删除页面**
- 1. 校验顺序
<li style="margin-left:1em">1. 优先级1:已存在校验
<li style="margin-left:1em">2. 优先级2:AI强控制（<u>按优先级逐个执行（须已启用），满足校验立即提示，不执行后续AI弱控制校验</u>）
<li style="margin-left:1em">3. 优先级3:AI弱控制（<u>按优先级逐个执行（须已启用），满足校验立即提示，选择【继续提交】后执行后续AI弱控制校验</u>）
- 2. 触发时机
<li style="margin-left:1em">4. 手动新增/编辑提交单据、手动删除（<u>单个</u>）
<li style="margin-left:1em">5. 批量删除：若本对象配置了AI规则中触发动作=删除且已启用，不支持批量删除，点击【批量删除】后--\>确认删除弹窗【确定】--\>toast提示‘AI规则中配置了删除的校验，不允许批量删除’
- 3. 页面loading:同AI值![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1GXn45KN3932bqDQ/img/75c51c79-b86d-4b44-80f4-e19bd1d60f26.png?Expires=1774165007&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=cJxtJWZN2EPJhZNPn0uH2vRF4qo%3D "")
- 4. 弹窗提示
  备注：若依据提示词未输出提示内容，默认展示
- 强控制弹窗提示内容：依据AI规则校验，满足强控制策略，单据无法\{触发动作\}
- 弱控制弹窗提示内容：依据AI规则校验，满足弱控制策略，请确认是否\{触发动作\}
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1GXn45KN3932bqDQ/img/5b1ece2a-8267-4091-96bc-8069f2736823.png?Expires=1774165007&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=dKDgesWTkHM8avvDAMGfDjztkco%3D "")
**三、版本控制**
- 仅开通了AI销售助理应用的企业，出现**‘AI规则’设置tab**
- AI销售助理应用未启用时，新建/编辑/删除不触发上述AI规则 |


