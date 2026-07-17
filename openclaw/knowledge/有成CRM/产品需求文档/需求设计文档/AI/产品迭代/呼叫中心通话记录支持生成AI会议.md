---
title: "呼叫中心通话记录支持生成AI会议"
nodeId: 6LeBq413JAzGj9vYH3kekm2k8DOnGvpb
workspaceId: R2PmK2Q8rxRbeXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/6LeBq413JAzGj9vYH3kekm2k8DOnGvpb?utm_scene=team_space"
updateTime: 1783331160000
exportedAt: 2026-07-16T11:02:51.928Z
source: dingtalk-document-mcp
---
| 修订时间 | 版本 | 修订人 | 修订说明 |
|-----------------------------------------------------------------------|-----------------------------------------------------------------|--------------------------------------------------------------------|-----------------------------------------------------------------------|
| 2026-7-6 | v1.0 | 黄艺平 | 新建 |
|  |  |  |  |

## 需求详情

| 需求 | 描述 |
|-----------------------------------------------------------------|-----------------------------------------------------------------|
| 呼叫中心支持AI分析 | 增加如下配置非必填，多选，目前选型只有‘呼叫中心（通话记录）’上述有选择‘呼叫中心（通话记录）’\+AI销售助理未过期同步时机：通话结束后录音自动传到应用内 或 手动上传音频通话记录（有音频文件的）自动生成AI会议，字段映射如下AI会议.会议对象：取 呼叫中心.对象类型AI会议.关联对象：取 呼叫中心.对象名称AI会议.会议方式：=电话沟通AI会议.会议类型：=呼叫中心录音会议开始时间：取 呼叫中心.开始时间会议结束时间：取 呼叫中心.结束时间会议时长：取 呼叫中心.通话时长（分钟）创建人：取 呼叫中心.创建人创建时间：取 呼叫中心.结束时间修改人：取 呼叫中心.创建人最后修改时间：取 呼叫中心.结束时间![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/AJdl65AVokMz7Oke/img/3e157be8-4d6d-42a3-9edc-dbfa7ce72ed6.png?Expires=1784206972&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=tmHTblrT39367kSjv%2FCLpMDIVho%3D "")![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/AJdl65AVokMz7Oke/img/8a0d564c-bb8c-47a4-8dac-5f23112f45b2.png?Expires=1784206972&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=saVp%2FHK%2BydZ3sYks2yikvfqaA3U%3D "") |
| AI会议支持编辑/删除 | 角色设置AI销售助理-AI会议：增加‘编辑’‘删除’功能权限编辑会议会议开始时间如果会议类型=本地上传音视频：会议开始时间可编辑如果会议类型≠本地上传音视频：会议开始时间不可编辑会议对象变更了会议对象：若AI复盘中相关适用模块-分析数据来源有依赖于AI会议，则需要重新复盘（变更前后的对象均要重新判断是否要重新复盘）![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/AJdl65AVokMz7Oke/img/942be7f4-b97d-461d-aac8-cfd4afacaa25.png?Expires=1784206972&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=ZQWkFS1lnILe9zLtEtl3uNZYyDU%3D "") |
