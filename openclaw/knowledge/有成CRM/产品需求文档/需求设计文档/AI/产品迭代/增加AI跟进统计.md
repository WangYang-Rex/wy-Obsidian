---
title: "增加AI跟进统计"
nodeId: Obva6QBXJw9lbx7RTRe9mXd0Wn4qY5Pr
workspaceId: R2PmK2Q8rxRbeXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/Obva6QBXJw9lbx7RTRe9mXd0Wn4qY5Pr?utm_scene=team_space"
exportedAt: 2026-03-31T03:49:41.959Z
source: dingtalk-document-mcp
---
| 修订时间 | 版本 | 修订人 | 修订说明 |
|-----------------------------------------------------------------------|-----------------------------------------------------------------|--------------------------------------------------------------------|-----------------------------------------------------------------------|
| 2025-10-21 | v1.0 | 黄艺平 | 新建 |
|  |  |  |  |

## 需求详情

| 需求 | 描述 |
|-----------------------------------------------------------------|-----------------------------------------------------------------|
| aI会议对象表单可配置 | 1. 增加‘AI销售助理’分组，该分组属性同‘设置’1. 分组信息在列表不可见2. 其他对象不可挪到该组，该组对象不可挪到组外2. 下包含对象「AI会议」3. 预设字段如下（可配置参数同其他预设对象）1. 标题（主键）1. 新建编辑页面不可见（内容系统已自动生成）2. 会议对象（单选、参考跟进记录-对象类型）2. 新建编辑页面可见可编辑3. 默认必填4. 选项值1. 新企业：选项值‘客户’、‘销售机会’、‘工单’、‘项目’、‘线索’，默认值‘客户’2. ~~历史已开通企业：选项值及默认值，依据该企业跟进记录-对象类型刷数据~~（辉俊看过了，历史客户会议记录只有关于客户、商机的）3. 关联对象（关联单选，参考跟进记录-关联对象）5. 新建编辑页面可见可编辑6. 默认必填4. 会议方式（单选）7. 新建页面可见可编辑8. 默认必填9. 选项值3. 新企业：选项值 ‘线上会议’、‘线下拜访’、‘电话沟通’、‘其他’4. 历史已开通企业：选项值及默认值，依据其企业跟进记录-跟进类型刷数据5. 会议类型10. 新建页面不可见11. 单选，选项值：钉钉视频会议、腾讯视频会议、飞书视频会议、呼叫中心录音、本地上传音视频12. 历史已开通企业：会议记录中该字段值=钉钉视频会议6. 会议开始时间13. 本期新建页面不可见（后续本地上传的音视频需要用户填写）7. 会议结束时间14. 新建页面不可见8. 会议时长15. 新建页面不可见9. 风险类型16. 新建页面可见不可编辑17. 单选，选项值：‘无风险’、‘有风险’10. 创建人11. 创建时间12. 修改人13. 最后修改时间4. 对象在列表中不可见5. 表单不可添加字段控件![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/3M0OzeZgQr5Qgqze/img/2acfefe2-de6f-41ff-96ac-634fcae577e3.png?Expires=1774934114&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=%2Fi9XVniU0jyD8WgvTAZMcapkaPE%3D "") |
| AI销售助理-跟进看板 | 1. 【发起会议】-【选择跟进信息】弹窗1. 弹窗标题变更2. 字段名、可见范围根据上述对象表单字段配置（会议对象为空时，关联对象字段置灰）3. 新建页面无可见字段，此弹窗隐藏![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/3M0OzeZgQr5Qgqze/img/5ef182d7-1533-48f0-96db-cd21fa2bf812.png?Expires=1774934114&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=akAmiPg4QgHoDoTE8Pje9A9tN44%3D "")2. 生成的会议卡片![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/3M0OzeZgQr5Qgqze/img/ca1c4245-a2a2-4787-ab5e-4b79a2d7dc59.png?Expires=1774934114&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=dta72dzUEivN4XgQic83iVv6eYk%3D "")3. AI生成跟进4. 所选对象类型/关联数据能对应上，则取对应值5. 对应不上，或者为空值，则不取4. 日历组件（样式参考日程）6. 对应日期 当前用户有跟进记录且无风险提示类型卡片：蓝色7. 对应日期 5. 筛选器8. ~~人员筛选：增加【设为默认】操作（同首页）~~9. 增加是否有会议记录筛选：单选，选项 全部/有跟进员工/无跟进员工，默认全部10. 增加卡片类型筛选： 单选，选项 全部/有风险/无风险，默认全部6. 新手引导位置调整（加了菜单后，新手引导前几个步骤都有调整）![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/3M0OzeZgQr5Qgqze/img/2cb941d7-4827-4061-a9f9-7f90709bc361.png?Expires=1774934114&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=TC%2BWHjOCIEeS2aB8AtyBKm%2FP4vE%3D "") |
| 新增「AI转化分析’」 | 1. 筛选器：人员筛选、日期筛选（同首页）2. 维度：员工3. 维度属性：所属部门4. 指标1. 跟进客户数/风险客户数（去重）2. 其他同首页5. 环比3. 环比日期区间1. 今天-\>昨天2. 本周-\>上周3. 本月-\>上月4. 本年-\>上年5. 自定义日期区间如2025-10-01～ 2025-10～24，则比对取镜像日期为2025-9-7～2025-9-304. 上述所有指标均有环比计算（不行的话就指定指标：新建订单数、新建订单金额、会议次数、会议时长（h）、提示风险次数）6. 环比增长率 = (本期数值 - 上期数值) / \|上期数值\| × 100%7. 上期数值=0，增长率=100%5. 页面中环比结果展示：环比增长（增长率\>0）/降低（增长率\<0）\>=20%的才展示6. 指标支持排序7. 奖牌展示：固定展示在前三行数据（手动排序，排序后前三展示）8. 数据支持导出6. 导出结果中要展示环比结果列7. 导出结果中要展示合计行![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/3M0OzeZgQr5Qgqze/img/38e82072-cd18-4d93-8677-50729f3215b8.png?Expires=1774934114&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=y6bj6s8Q03m8jn5yx1zkTb9FOdw%3D "")1. 增加前端埋点（仅PC端）1. 查看报表：10790.16098.16100.93873.93930.939312. 导出：10790.16098.16100.93873.93930.93932 |
| 角色设置 | 一、原‘AI跟进’改为‘AI会议’二、增加模块：AI转化分析功能权限：列表、导出备注：功能上线时，历史已开通企业管理员默认有此功能权限![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/3M0OzeZgQr5Qgqze/img/cbc2f3de-dde2-492a-a3f0-e7c3ea3297df.png?Expires=1774934114&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=ZFvpichyU%2FdHYYJ9Ch9QaQ8oWgA%3D "") |
| 应用中心 | 增加「AI转化分析」应用开关![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/3M0OzeZgQr5Qgqze/img/9e31f2d2-584f-4a5b-abc8-cd7c851dfaa3.png?Expires=1774934114&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=Hlx2aWHQ%2F8vZ1Uqh0saqHeSfsVw%3D "") |

