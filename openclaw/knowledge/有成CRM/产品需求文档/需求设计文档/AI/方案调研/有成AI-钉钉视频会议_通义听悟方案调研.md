---
title: "有成AI-钉钉视频会议_通义听悟方案调研"
nodeId: r1R7q3QmWe7M9wKYh7OLv9AXJxkXOEP2
workspaceId: R2PmK2Q8rxRbeXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/r1R7q3QmWe7M9wKYh7OLv9AXJxkXOEP2?utm_scene=team_space"
exportedAt: 2026-03-31T03:52:12.362Z
source: dingtalk-document-mcp
---
# 有成AI-钉钉视频会议/通义听悟方案调研

| **修订时间** | **版本** | **修订说明** |
|----------------|----------|----------------|
| 2025 | v1.0 | 新建 |
|  |  |  |

## 1、钉钉闪记的可行性分析

### 1.1、应用内预约视频会议

[<u>创建预约会议 - 开放平台</u>](https://open.dingtalk.com/document/isvapp/create-appointment-meeting)

#### a.问题1：是否可以选外部联系人作为与会人，需前端调研钉钉选人组件是否支持

##### 结论1：钉钉移动端支持选择外部联系人，PC端是否支持需前端调研

[<u>chooseExternalUsers - 开放平台</u>](https://open.dingtalk.com/document/orgapp/jsapi-choose-external-users)

可以通过这个接口，记录当前企业的外部联系人，以便于后续使用

[<u>根据unionid获取用户userid - 开放平台</u>](https://open.dingtalk.com/document/isvapp/query-a-user-by-the-union-id)

### 1.2、应用内创建视频会议

[<u>创建视频会议 - 开放平台</u>](https://open.dingtalk.com/document/isvapp/create-a-video-conference)

### 1.3、会议状态事件订阅

[<u>视频会议状态变更 - 开放平台</u>](https://open.dingtalk.com/document/isvapp/event-meeting-status-change)
- conference\_created : 会议创建事件
- conference\_closed : 会议关闭事件

### 1.4、开启云录制API（闪记）

[<u>开启视频会议云录制 - 开放平台</u>](https://open.dingtalk.com/document/isvapp/video-conference-open-cloud-recording)

### 1.5、结束云录制API（闪记）

[<u>停止视频会议云录制 - 开放平台</u>](https://open.dingtalk.com/document/isvapp/video-conferencing-stops-cloud-recording)

### 1.6、闪记文本内容获取

[<u>查询会议录制中的文本信息 - 开放平台</u>](https://open.dingtalk.com/document/isvapp/queries-the-text-information-about-cloud-recording)

### 1.7、将录制的文本内容交给大模型分析

参考有成AI的新建意图实现



![Picture 1](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Yvenve5bJjVWVloy/img/b06ec561-cfed-4004-9092-cc307c64112f.jpeg?Expires=1774934295&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=IKhzEcxyQ%2BOcFbsymbeDsEtJKE8%3D "")

## 2、通义听悟的可行性分析

### 2.1、计费说明

[<u>通义听悟如何计费\_工作学习 AI 助手通义听悟(TINGWU)-阿里云帮助中心</u>](https://help.aliyun.com/zh/tingwu/pricing-and-billing-rules?spm=a2c4g.11186623.help-menu-454189.d_0_2_1.657b5041zDFhBH)



![Picture 2](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Yvenve5bJjVWVloy/img/d7b6fd47-4f23-480c-9bcf-e74531331a10.png?Expires=1774934295&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=etnCjExZDTzcPHQei1P9wOQsr8I%3D "")

收费较贵，需用户充值额度，可只使用ASR模块，大模型能力有可替代的方案(0.6元/3600秒)

### 2.2、创建听悟任务

[<u>CreateTask - 创建听悟任务\_工作学习 AI 助手通义听悟(TINGWU)-阿里云帮助中心</u>](https://help.aliyun.com/zh/tingwu/api-tingwu-2023-09-30-createtask?spm=a2c4g.11186623.help-menu-454189.d_2_2_3_0.5c117792a2YKjv)

### 2.3、查询任务结果

[<u>GetTaskInfo - 查询任务状态和任务结果\_工作学习 AI 助手通义听悟(TINGWU)-阿里云帮助中心</u>](https://help.aliyun.com/zh/tingwu/api-tingwu-2023-09-30-gettaskinfo?spm=a2c4g.11186623.help-menu-454189.d_2_2_3_1.1c316cf1yUPWVT)

### 2.4、将任务返回的文本内容交给大模型分析

参考有成AI的新建意图实现
