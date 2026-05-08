---
title: "增加AI跟进统计"
tags:
  - 有成CRM
  - PRD
  - 需求设计文档-AI-产品�
created: 2026-03-24
source: 钉钉文档
original_url: https://alidocs.dingtalk.com/i/nodes/Obva6QBXJw9lbx7RTRe9mXd0Wn4qY5Pr?utm_scene=team_space
node_id: Obva6QBXJw9lbx7RTRe9mXd0Wn4qY5Pr
exported_at: 2026-03-22
---

# 增加AI跟进统计

> 🔗 **原文链接**：[增加AI跟进统计 - 钉钉文档](https://alidocs.dingtalk.com/i/nodes/Obva6QBXJw9lbx7RTRe9mXd0Wn4qY5Pr?utm_scene=team_space)

| 修订时间 | 版本 | 修订人 | 修订说明 |
|-----------------------------------------------------------------------|-----------------------------------------------------------------|--------------------------------------------------------------------|-----------------------------------------------------------------------|
| 2025-10-21 | v1.0 | 黄艺平 | 新建 |
|  |  |  |  |

## 需求详情

| 需求 | 描述 |
|-----------------------------------------------------------------|-----------------------------------------------------------------|
| aI会议对象表单可配置 | - 1. 增加‘AI销售助理’分组，该分组属性同‘设置’
<li style="margin-left:1em">1. 分组信息在列表不可见
<li style="margin-left:1em">2. 其他对象不可挪到该组，该组对象不可挪到组外
- 2. 下包含对象「AI会议」
<li style="margin-left:1em">3. 预设字段如下（可配置参数同其他预设对象）
<li style="margin-left:2em">1. 标题（主键）
<li style="margin-left:3em">1. 新建编辑页面不可见（内容系统已自动生成）
<li style="margin-left:2em">2. 会议对象（单选、参考跟进记录-对象类型）
<li style="margin-left:3em">2. 新建编辑页面可见可编辑
<li style="margin-left:3em">3. 默认必填
<li style="margin-left:3em">4. 选项值
<li style="margin-left:4em">1. 新企业：选项值‘客户’、‘销售机会’、‘工单’、‘项目’、‘线索’，默认值‘客户’
<li style="margin-left:4em">2. ~~历史已开通企业：选项值及默认值，依据该企业跟进记录-对象类型刷数据~~（辉俊看过了，历史客户会议记录只有关于客户、商机的）
<li style="margin-left:2em">3. 关联对象（关联单选，参考跟进记录-关联对象）
<li style="margin-left:3em">5. 新建编辑页面可见可编辑
<li style="margin-left:3em">6. 默认必填
<li style="margin-left:2em">4. 会议方式（单选）
<li style="margin-left:3em">7. 新建页面可见可编辑
<li style="margin-left:3em">8. 默认必填
<li style="margin-left:3em">9. 选项值
<li style="margin-left:4em">3. 新企业：选项值 ‘线上会议’、‘线下拜访’、‘电话沟通’、‘其他’
<li style="margin-left:4em">4. 历史已开通企业：选项值及默认值，依据其企业跟进记录-跟进类型刷数据
<li style="margin-left:2em">5. 会议类型
<li style="margin-left:3em">10. 新建页面不可见
<li style="margin-left:3em">11. 单选，选项值：钉钉视频会议、腾讯视频会议、飞书视频会议、呼叫中心录音、本地上传音视频
<li style="margin-left:3em">12. 历史已开通企业：会议记录中该字段值=钉钉视频会议
<li style="margin-left:2em">6. 会议开始时间
<li style="margin-left:3em">13. 本期新建页面不可见（后续本地上传的音视频需要用户填写）
<li style="margin-left:2em">7. 会议结束时间
<li style="margin-left:3em">14. 新建页面不可见
<li style="margin-left:2em">8. 会议时长
<li style="margin-left:3em">15. 新建页面不可见
<li style="margin-left:2em">9. 风险类型
<li style="margin-left:3em">16. 新建页面可见不可编辑
<li style="margin-left:3em">17. 单选，选项值：‘无风险’、‘有风险’
<li style="margin-left:2em">10. 创建人
<li style="margin-left:2em">11. 创建时间
<li style="margin-left:2em">12. 修改人
<li style="margin-left:2em">13. 最后修改时间
<li style="margin-left:1em">4. 对象在列表中不可见
<li style="margin-left:1em">5. 表单不可添加字段控件
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/3M0OzeZgQr5Qgqze/img/2acfefe2-de6f-41ff-96ac-634fcae577e3.png?Expires=1774165016&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=5oQvS9Z6FBYm4M6HEXLQV4uTb9s%3D "") |
| AI销售助理-跟进看板 | - 1. 【发起会议】-【选择跟进信息】弹窗
<li style="margin-left:1em">1. 弹窗标题变更
<li style="margin-left:1em">2. 字段名、可见范围根据上述对象表单字段配置（会议对象为空时，关联对象字段置灰）
<li style="margin-left:1em">3. 新建页面无可见字段，此弹窗隐藏
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/3M0OzeZgQr5Qgqze/img/5ef182d7-1533-48f0-96db-cd21fa2bf812.png?Expires=1774165016&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=KWSwJG6A2vKc%2BYrg4fBdksTXums%3D "")
- 2. 生成的会议卡片
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/3M0OzeZgQr5Qgqze/img/ca1c4245-a2a2-4787-ab5e-4b79a2d7dc59.png?Expires=1774165016&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=WqmS%2FFWFAUuUA%2BprJuEfoKZ0yaI%3D "")
- 3. AI生成跟进
<li style="margin-left:1em">4. 所选对象类型/关联数据能对应上，则取对应值
<li style="margin-left:1em">5. 对应不上，或者为空值，则不取
- 4. 日历组件（样式参考日程）
<li style="margin-left:1em">6. 对应日期 当前用户有跟进记录且无风险提示类型卡片：蓝色
<li style="margin-left:1em">7. 对应日期 
- 5. 筛选器
<li style="margin-left:1em">8. ~~人员筛选：增加【设为默认】操作（同首页）~~
<li style="margin-left:1em">9. 增加是否有会议记录筛选：单选，选项 全部/有跟进员工/无跟进员工，默认全部
<li style="margin-left:1em">10. 增加卡片类型筛选： 单选，选项 全部/有风险/无风险，默认全部
- 6. 新手引导位置调整（加了菜单后，新手引导前几个步骤都有调整）
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/3M0OzeZgQr5Qgqze/img/2cb941d7-4827-4061-a9f9-7f90709bc361.png?Expires=1774165016&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=AXuRig9xvSHrIY1n%2BJNSQmwvZ%2Bs%3D "") |
| 新增「AI转化分析’」 | - 1. 筛选器：人员筛选、日期筛选（同首页）
- 2. 维度：员工
- 3. 维度属性：所属部门
- 4. 指标
<li style="margin-left:1em">1. 跟进客户数/风险客户数（去重）
<li style="margin-left:1em">2. 其他同首页
- 5. 环比
<li style="margin-left:1em">3. 环比日期区间
<li style="margin-left:2em">1. 今天-\>昨天
<li style="margin-left:2em">2. 本周-\>上周
<li style="margin-left:2em">3. 本月-\>上月
<li style="margin-left:2em">4. 本年-\>上年
<li style="margin-left:2em">5. 自定义日期区间如2025-10-01～ 2025-10～24，则比对取镜像日期为2025-9-7～2025-9-30
<li style="margin-left:1em">4. 上述所有指标均有环比计算（不行的话就指定指标：新建订单数、新建订单金额、会议次数、会议时长（h）、提示风险次数）
<li style="margin-left:2em">6. 环比增长率 = (本期数值 - 上期数值) / \|上期数值\| × 100%
<li style="margin-left:2em">7. 上期数值=0，增长率=100%
<li style="margin-left:1em">5. 页面中环比结果展示：环比增长（增长率\>0）/降低（增长率\<0）\>=20%的才展示
- 6. 指标支持排序
- 7. 奖牌展示：固定展示在前三行数据（手动排序，排序后前三展示）
- 8. 数据支持导出
<li style="margin-left:1em">6. 导出结果中要展示环比结果列
<li style="margin-left:1em">7. 导出结果中要展示合计行
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/3M0OzeZgQr5Qgqze/img/38e82072-cd18-4d93-8677-50729f3215b8.png?Expires=1774165016&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=SUevctyJtidFiH2UxgmSgUrMPSs%3D "")
- 1. 增加前端埋点（仅PC端）
<li style="margin-left:1em">1. 查看报表：10790.16098.16100.93873.93930.93931
<li style="margin-left:1em">2. 导出：10790.16098.16100.93873.93930.93932 |
| 角色设置 | 一、原‘AI跟进’改为‘AI会议’
二、增加
模块：AI转化分析
功能权限：列表、导出
备注：功能上线时，历史已开通企业管理员默认有此功能权限
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/3M0OzeZgQr5Qgqze/img/cbc2f3de-dde2-492a-a3f0-e7c3ea3297df.png?Expires=1774165016&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=eZOzwJR0IE68YWACe3Ul1TreqPQ%3D "") |
| 应用中心 | 增加「AI转化分析」应用开关
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/3M0OzeZgQr5Qgqze/img/9e31f2d2-584f-4a5b-abc8-cd7c851dfaa3.png?Expires=1774165016&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=drQ%2Fd9SAtOLzfOmLWJM0%2BRiV%2B3s%3D "") |


