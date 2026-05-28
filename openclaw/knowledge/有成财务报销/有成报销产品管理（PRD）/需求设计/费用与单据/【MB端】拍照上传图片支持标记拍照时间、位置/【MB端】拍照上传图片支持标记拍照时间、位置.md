---
title: "【MB端】拍照上传图片支持标记拍照时间、位置"
nodeId: 14lgGw3P8vvl0xnzIdD6XeZp85daZ90D
workspaceId: R2PmK2gngjVnZXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/14lgGw3P8vvl0xnzIdD6XeZp85daZ90D?utm_scene=team_space"
updateTime: 1751427322000
exportedAt: 2026-05-14T12:11:11.654Z
source: dingtalk-document-mcp
---
# 【MB端】拍照上传图片支持标记拍照时间、位置

| **修订时间** | **版本** | **编写人** | **修订说明** |
|----------------|----------|-------------|----------------|
| 20230106 | v1.0 | 张乔艳 | 新建 |

## 1、需求背景

客户：海南金世纪建设工程有限公司

背景：客户为建筑公司，为确保工地现场人员出勤的准确性，移动端创建单据现场拍照上传图片时，支持带上时间、地点信息

## 2、业务流程/架构

## 3、功能清单

| **模块** | **功能点** | **备注** |
|----------|-------------|----------|
| 自定义单据 | PC-单据字段“图片”字段设置中新增“拍照设置” |  |
| 创建单据 | PC、MB创建单据/重新提交单据-获取/修改地点时间 |  |
| 单据详情 | PC、MB-显示拍照“地点”、“时间” |  |

## 4、需求详情

### 4.1、需求说明

**系统：**【有成报销】PC & MB

**一、【PC】自定义单据-图片“拍照设置”**

1、仅允许拍照上传 ：勾选该配置后，只允许在手机端进行拍照上传，PC禁掉本地图片上传功能
- 注释文案：仅允许在手机端通过“拍照”方式上传图片

2、勾选仅允许拍照上传后，展示“标记拍照位置”、“标记拍照位置”设置项，默认为勾选状态；必填选项默认：已勾选；位置微调范围默认：100米
- 微调范围选项：100米、200米、500米、1000米
- “标记拍照位置”注释文案：上传图片时，标记拍照地点
- “标记拍照位置”注释文案：上传图片时，标记拍照时间



![Picture 1](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Mp7ld7bBDQJAMOBQ/img/e449a05b-6b20-4389-89d8-fd561cc1def3.png?Expires=1778767313&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=WHBCh3vk3i%2FZbjnxzbj7y3rVLFM%3D "")

 “图片”组件设置

注：历史单据都需要刷上该配置项（默认状态：未勾选）



**二、创建单据**

创建单据时，先判断图片是否为必填项，再根据“位置/时间”是否必填，最终判断是否允许单据提交

| **序号** | **【图片】是否必填** | **【时间/位置】是否必填** | **是否已上传图片** | **【时间/位置】获取是否成功** | **是否允许提交** | **提示** |
|----------|----------------------------|-----------------------------------|-------------------------|-----------------------------------------|----------------------|----------|
| 1 | 必填 | 必填 | 已上传 | 时间/位置已自动获取 | 允许提交 |  |
| 2 |  | 必填 | 未上传/已删除 | 时间位置未获取/已清除 | 不允许提交 | 请上传图片 |
| 3 |  | 必填 | 已上传 | 位置获取失败 | 不允许提交 | 请点击获取拍照位置 |
| 4 |  | 非必填 | 已上传 | 位置获取失败 | 允许提交 |  |
| 5 |  | 非必填 | 未上传/已删除 | 时间位置未获取/已清除 | 不允许提交 | 请上传图片 |
| 6 |  | 非必填 | 已上传 | 时间/位置已自动获取 | 允许提交 |  |
| 7 | 非必填 | 必填 | 已上传 | 时间/位置已自动获取 | 允许提交 |  |
| 8 |  | 必填 | 已上传 | 位置获取失败 | 不允许提交 | 请点击获取拍照位置 |
| 9 |  | 必填 | 未上传/已删除 | 时间位置未获取/已清除 | 允许提交 |  |
| 10 |  | 非必填 | 已上传 | 位置获取失败 | 允许提交 |  |
| 11 |  | 非必填 | 未上传/已删除 | 时间位置未获取/已清除 | 允许提交 |  |
| 12 |  | 非必填 | 已上传 | 时间/位置已自动获取 | 允许提交 |  |

**1、PC-创建单据**

当图片设置为“仅允许拍照上传”时，在页面给出二维码，支持手机扫码进行拍照



![Picture 2](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Mp7ld7bBDQJAMOBQ/img/cd996bd6-c532-42ac-adc3-2a8bde357c55.png?Expires=1778767313&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=9RBsomCmEiv4Xs6X9zVybdtu7wA%3D "")

**2、MB-创建单据**
- 当图片设置为“仅允许拍照上传”时，点击图片上传按钮，直接调起相机拍照；
- 地址/时间获取、刷新逻辑：每上传一张照片，先获取照片拍摄时间/地址，若照片无拍摄时间/地址，获取当前设备的时间/地址，刷新显示最新时间/地址（时间/地址与照片关联）；若图片删除，关联的时间/地点信息一并删除，显示最近一张图片的时间/地点；删除所有上传的图片，时间/地点也被清除
- 地址获取失败（未授权/网络问题等），支持点击重新获取网络问题：网络失败，请点击重新获取位置未授权：未进行位置授权，请在系统设置中完成授权，再重新获取位置



![Picture 3](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Mp7ld7bBDQJAMOBQ/img/d60521b2-8a4e-4f74-9cb9-a56bfca95f59.png?Expires=1778767313&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=pWu1WEJNli0U2tcY%2Fp8%2FcflUKnM%3D "")
- 地址支持微调，微调范围取图片组件设置的微调范围



![Picture 4](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Mp7ld7bBDQJAMOBQ/img/1bf6958f-9d26-4b7f-9d2f-9d95962a83ab.png?Expires=1778767313&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=9agdCGYMMnSoBsJAea%2FVufIeFBI%3D "")
- 当未限制图片“仅允许拍照上传”时，支持三种图片上传方式（拍照、选取文件、照片图库）上传图片



![Picture 5](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Mp7ld7bBDQJAMOBQ/img/b28d783c-7f95-4c15-afc1-784019a0a0e1.png?Expires=1778767313&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=0BheswO6DRWJZygk4Cg6ld0G0QA%3D "")

**三、单据详情**

仅允许拍照上传的图片，标记了时间/位置，单据详情页-展示样式如下：



![Picture 6](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Mp7ld7bBDQJAMOBQ/img/6f5f53b9-0edc-455c-9d87-699338ef6f84.png?Expires=1778767313&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=ZXfqdltIBi3KzbUVU%2Fe9dy0ccOQ%3D "")

 单据详情-图片 时间/位置标记
