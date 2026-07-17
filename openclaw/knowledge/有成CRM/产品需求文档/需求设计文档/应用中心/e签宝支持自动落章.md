---
title: "e签宝支持自动落章"
nodeId: amweZ92PV6vZeDLpIKaQElOYVxEKBD6p
workspaceId: R2PmK2Q8rxRbeXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/amweZ92PV6vZeDLpIKaQElOYVxEKBD6p?utm_scene=team_space"
updateTime: 1780049653000
exportedAt: 2026-06-09T12:22:00.869Z
source: dingtalk-document-mcp
---
| 修订时间 | 版本 | 修订人 | 修订说明 |
|-----------------------------------------------------------------------|-----------------------------------------------------------------|--------------------------------------------------------------------|-----------------------------------------------------------------------|
| 2026-5-9 | v1.0 | 黄艺平 | 新建 |
|  |  |  |  |

## 需求背景

以其乐融融为例：销售发起政策申请签署（标准合同模板），发起签署后需要自动盖其乐融融的公章

这里需要注意，他们政策申请有多种合同，近标准合同需要自动盖章，非标准合同不用自动盖章

## 解决方案
- 需要配置满足什么条件的数据需要自动盖章
    - 其中配置选择盖什么印章，通过接口：[https://open.esign.cn/doc/opendoc/seal3/ups6h1](https://open.esign.cn/doc/opendoc/seal3/ups6h1)
- 满足自动盖章条件时
    - 通过企业配置的盖章‘关键字’，获取该关键字处于文件的第几页、坐标：[https://open.esign.cn/doc/opendoc/pdf-sign3/ze0ahv](https://open.esign.cn/doc/opendoc/pdf-sign3/ze0ahv)
    - 获取到上述信息后，在从页面发起签署的接口中，传入对应参数：[https://open.esign.cn/doc/opendoc/pdf-sign3/lp54bn](https://open.esign.cn/doc/opendoc/pdf-sign3/lp54bn)

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/jP2lRYjez5pwEO8g/img/b7b424f5-b2e0-4635-92d2-b8a0bbe4c722.png?Expires=1781014921&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=%2BMsMCBTvWQJcDp%2FFt4ScSW0UeEA%3D "")

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/jP2lRYjez5pwEO8g/img/a9559523-364e-48ea-93c5-89b24454b640.png?Expires=1781014921&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=Dh0I0oMXJ%2BVD9807xDxG0nvLs1s%3D "")


    - 

## 需求详情

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/jP2lRYjez5pwEO8g/img/d2a5110e-f2d7-4ef2-b051-be390402744f.png?Expires=1781014921&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=CjZtRWuCHO76TBtRXIRYHbwHWnM%3D "")

| 需求 | 描述 |
|-----------------------------------------------------------------|-----------------------------------------------------------------|
| 自动落章 | 发起签署文件配置优化1. 页面展示优化见上：区块划分更明显2. 增加‘发起后自动签署’配置1. 仅开启新版e签宝的企业才有此配置项，非新版企业隐藏2. 默认为关，关闭时下述配置项隐藏；开启时下述配置项展示1. 满足自动盖章条件1. 必填2. 选择‘部分数据’时，可配置数据范围（只能取主要对象字段，参考列表筛选）2. 盖章位置3. 必填，可多选4. 勾选了‘单页签章’必须维护一组关键字（最多输入32字符）\+印章，否则保存配置时提示'勾选了需要单页签章，关键字、印章必填'可加多组，最多可添加5组5. 勾选了‘骑缝章’默认‘所有页’，印章必选选择‘指定页码’必须维护一组页码范围（只能输入1-9999的正整数）\+印章组内，起始页码需要小于终止页码，否则保存配置时提示'骑缝章起始页面需要小于终止页码'3. 处理逻辑：发起签署时，依据盖章条件，满足时则传入预设签署方signers-signFields--normalSignFieldConfig相关参数freeMode：falseautoSign：truemovableSignField：falseassignedSealId：依据配置signFieldStyle：依据配置signFieldPositionacrossPageMode：依据骑缝章配置positionPage单页签章：依据关键字查找其所在页码（pageNum），并传入骑缝签章：依据骑缝章配置positionX：依据关键字查找其所在页的x轴（positionX），并传入positionY：依据关键字查找其所在页的Y轴（positionY），并传入增加需求：e签订配置增加版本，用于记录每次配置变更情况[https://tb.raycloud.com/task/6a196699cf1cc2001ec41eca](https://tb.raycloud.com/task/6a196699cf1cc2001ec41eca) |
| 发起签署 | 发起签署-选择文件-选择打印文件：支持选择多个打印模板生成文件 |
