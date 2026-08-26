---
title: "呼叫中心通话记录支持生成AI会议"
nodeId: 6LeBq413JAzGj9vYH3kekm2k8DOnGvpb
workspaceId: R2PmK2Q8rxRbeXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/6LeBq413JAzGj9vYH3kekm2k8DOnGvpb?utm_scene=team_space"
updateTime: 1785319302000
exportedAt: 2026-08-05T04:10:20.907Z
source: dingtalk-document-mcp
---
| 修订时间 | 版本 | 修订人 | 修订说明 |
|-----------------------------------------------------------------------|-----------------------------------------------------------------|--------------------------------------------------------------------|-----------------------------------------------------------------------|
| 2026-7-6 | v1.0 | 黄艺平 | 新建 |
|  |  |  |  |

## 需求详情

| 需求 | 描述 |
|-----------------------------------------------------------------|-----------------------------------------------------------------|
| 呼叫中心支持AI分析 | 增加如下配置
非必填，多选，目前选型只有‘呼叫中心（通话记录）’
上述有选择‘呼叫中心（通话记录）’\+AI销售助理未过期
同步时机：通话结束后录音自动传到应用内 或 手动上传音频
通话记录（有音频文件的）自动生成AI会议，字段映射如下
AI会议.会议对象：取 呼叫中心.对象类型
AI会议.关联对象：取 呼叫中心.对象名称
AI会议.会议方式：=电话沟通
AI会议.会议类型：=呼叫中心录音
会议开始时间：取 呼叫中心.开始时间
会议结束时间：取 呼叫中心.结束时间
会议时长：取 呼叫中心.通话时长（分钟）
创建人：取 呼叫中心.创建人
创建时间：取 呼叫中心.结束时间
修改人：取 呼叫中心.创建人
最后修改时间：取 呼叫中心.结束时间
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/AJdl65AVokMz7Oke/img/3e157be8-4d6d-42a3-9edc-dbfa7ce72ed6.png?Expires=1785910221&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=JJqJLYYr3pJz6bHZtlhzMNXCJ1M%3D "")
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/AJdl65AVokMz7Oke/img/8a0d564c-bb8c-47a4-8dac-5f23112f45b2.png?Expires=1785910221&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=TpVrcpxzuD7oNjzcTBTtzhvQCfc%3D "") |
| AI会议支持编辑/删除 | 角色设置
AI销售助理-AI会议：增加~~‘编辑’~~‘删除’功能权限
删除会议：需要重新复盘
~~编辑会议~~
~~会议开始时间~~
~~如果会议类型~~~~=~~~~本地上传音视频：会议开始时间可编辑~~
~~如果会议类型~~~~≠本地上传音视频：会议开始时间不可编辑~~
~~会议对象~~
~~变更了会议对象：若AI复盘中相关适用模块-分析数据来源有依赖于AI会议，则需要重新复盘（变更前后的对象均A要重新判断是否要重新复盘）~~
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/AJdl65AVokMz7Oke/img/2bc3c0ca-471d-4afc-99db-a02ef7390bd4.png?Expires=1785910221&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=tIzKQabb2ZYZKYqOgA7U%2F%2F1rmic%3D "")
![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/AJdl65AVokMz7Oke/img/942be7f4-b97d-461d-aac8-cfd4afacaa25.png?Expires=1785910221&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=ZXTT58E6lUukBUDuwn%2BksnNdvxg%3D "") |
