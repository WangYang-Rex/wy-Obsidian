---
title: "客户导入支持按客户ID匹配"
nodeId: 14lgGw3P8vvl0xnzIgzevwBD85daZ90D
workspaceId: R2PmK2Q8rxRbeXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/14lgGw3P8vvl0xnzIgzevwBD85daZ90D?utm_scene=team_space"
updateTime: 1785395446000
exportedAt: 2026-08-05T04:10:34.216Z
source: dingtalk-document-mcp
---
| 修订时间 | 版本 | 修订人 | 修订说明 |
|-----------------------------------------------------------------------|-----------------------------------------------------------------|--------------------------------------------------------------------|-----------------------------------------------------------------------|
| 2026-7-30 | v1.0 | 黄艺平 | 新建 |
|  |  |  |  |

## 需求详情

| 需求 | 描述 |
|-----------------------------------------------------------------|-----------------------------------------------------------------|
| 客户对象 | 1、字段‘客户ID’
在详情、列表页面可见
模板中默认配置为隐藏，支持切换为不隐藏
其他配置属性不展示
2、增加导入唯一标识配置
新企业默认为‘客户名称’
文案
关联客户导入唯一标识：举例导入客户的联系人，导入模板中‘客户’应填写客户的‘\{配置项\}’，否则可能会导入匹配失败。
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/v9kqDea9KvM0MOVx/img/4686b08a-e409-4051-9113-cc92efdccd6b.png?Expires=1785910234&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=3i4NyAKkUb5HaZgUE2p%2FYwDrx5s%3D "") |
| 其他对象导入 | 需要关联匹配客户时，若规则为依据客户ID为匹配条件，在导入模板中示例数据如图，导入匹配逻辑也改为按客户ID
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/v9kqDea9KvM0MOVx/img/7e0aea24-917f-4287-bdd6-7b0d1361c38f.png?Expires=1785910234&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=uod9uQCjdViK4ICxWbdxAQ4%2BW1g%3D "") |
| 客户覆盖导入 | 1、增加唯一性匹配规则选项，如图
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/v9kqDea9KvM0MOVx/img/6c5cde1b-1618-4b0b-8f2b-f709d4cef937.png?Expires=1785910234&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=muCQ9UUFn909wmaZDogGERGyDi4%3D "")
2、如果规则为依据客户ID为匹配条件
覆盖导入模板中，展示客户ID字段，并必填
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/v9kqDea9KvM0MOVx/img/d6ba685b-23a2-4d1b-92c4-0e5cf56d8150.png?Expires=1785910234&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=tGLy36qxpKWg4DQaUNys%2BGtANb0%3D "") |
