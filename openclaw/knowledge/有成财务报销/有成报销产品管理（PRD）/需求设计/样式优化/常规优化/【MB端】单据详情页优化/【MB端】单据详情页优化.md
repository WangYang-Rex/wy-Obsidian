---
title: "【MB端】单据详情页优化"
nodeId: YndMj49yWjPvNlg2I0Gjx0AbJ3pmz5aA
workspaceId: R2PmK2gngjVnZXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/YndMj49yWjPvNlg2I0Gjx0AbJ3pmz5aA?utm_scene=team_space"
updateTime: 1751427288000
exportedAt: 2026-05-14T12:07:07.808Z
source: dingtalk-document-mcp
---
# 【MB端】单据详情页优化

| **修订时间** | **版本** | **编写人** | **修订说明** |
|----------------|----------|-------------|----------------|
| 20230131 | v1.0 | 小乔 | 新建 |

## 1、需求背景

1、PC端-表当编辑时，字段标题较长时，内容混乱



![Picture 1](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0bvDDRebnw1/img/b59f24cd-6565-4da5-8bc0-3e11e6b02bba.png?Expires=1778766694&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=asCYoRTgCFH9rjXfUa7%2BsIFPAU0%3D "")

2、MB端-单据字段较长时，内容展示很乱，叠在一起展示；内容模块样式不统一



![Picture 2](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0bvDDRebnw1/img/b0ab7d5c-82f3-45fa-b704-a4bf0cfd6d63.png?Expires=1778766694&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=UK888N4peP4mMqwOAxDCjjqnxJs%3D "")

## 2、业务流程/架构

## 3、功能清单

| **模块** | **功能点** | **备注** |
|----------|-------------|----------|
| 【MB】单据详情 | 前端优化 |  |
| 【PC】表单编辑 | 前端优化 |  |
|  |  |  |

## 4、需求详情

### 4.1、需求说明

**系统：**【有成报销】**MB端 & PC端**

**UI：**[<u>https://lanhuapp.com/link/#/invite?sid=lX0FkjDc</u>](https://lanhuapp.com/link/#/invite?sid=lX0FkjDc)

| **模块** | **现状** | **优化** |
|----------|----------|----------|
| MB单据详情-基础信息 | 1、左右结构2、字段标题过长时，会覆盖下面的字段 | 1、字段与字段那样改成上下结构；2、标题过长时，仅展示一行，其他用“...”代替，支持点击展示标题 |
| MB单据详情-“发票”组件 |  | 1、原“发票”标题字号与其他独立展示组件标题字号保持一致2、标题与发票内容增加分割线 |
| MB单据详情-“消费明细”组件 |  | 1、统计数据右对齐显示，统计文案与“发票”组件保持一致2、标题与筛选项之间增加分割线3、具体消费明细字段标题与内容分别左右对齐4、内容过长时，换行显示5、发票标题与统计数据左右对齐 |
| MB单据详情-“项目”组件 |  | 1、组件标题与内容用分割线隔开2、标题与内容分别左右对齐3、项目名称过长时，换行显示 |
| MB单据详情-“行程”组件 |  | 1、组件标题与内容用分割线隔开2、标题与内容分别左右对齐 |
| MB单据详情-“关联单据”组件 |  | 1、组件标题与内容用分割线隔开2、标题与内容分别左右对齐3、项目名称过长时，换行显示，金额统计右对齐 |
| MB单据详情-“借款核销”组件 |  | 同“关联单据” |
| MB单据详情-“产品明细”组件 |  | 同“消费明细” |
| PC-表单编辑 | 标题过长时，会覆盖下面的字段展示 | 字段过长时换行展示，该字段上下间距增大 |

![Picture 3](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0bvDDRebnw1/img/38abd096-c45d-4dbc-884a-f113710a82d5.png?Expires=1778766694&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=aeR7prGDxaERLlqbLMy4a07oUdk%3D "")

![Picture 4](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0bvDDRebnw1/img/e9eda543-b074-4699-99a9-5304f34064af.png?Expires=1778766694&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=i1B0%2BbTpXet76Mo2LmW7wHkmPZ4%3D "")

![Picture 5](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0bvDDRebnw1/img/4050b591-2cdb-4f42-a6d7-217a512d8601.png?Expires=1778766694&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=RIQ5B%2FuxHJYXik8bJfAb7HeOOA4%3D "")

![Picture 6](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0bvDDRebnw1/img/32157b7f-ae63-4a89-bc91-2652703d8be8.png?Expires=1778766694&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=EN97Z93GfwxwmXUyWqXKbiLzC4A%3D "")

![Picture 7](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0bvDDRebnw1/img/9ec3312c-f41f-4d07-97b7-d50676d11243.png?Expires=1778766694&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=ugSTlzMEAX%2F0r%2FIvtb%2FfMVHI9KI%3D "")

![Picture 8](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0bvDDRebnw1/img/eb4c8d07-bf70-4863-a135-c3a2cf9099b0.png?Expires=1778766694&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=P8YmcquPzf7xrTTGYTUzQwwnXqQ%3D "")

![Picture 9](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0bvDDRebnw1/img/27727fd4-76af-499c-9f3c-ba66a6b26d5b.png?Expires=1778766694&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=xYCbY9h0KeIBnXU8sy6vF8x3YkM%3D "")

![Picture 10](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0bvDDRebnw1/img/2bf26b1a-51f7-40a8-9946-15bd344a635d.png?Expires=1778766694&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=MCAeRSEASAabuwiRcxl8f9Niuuo%3D "")

![Picture 11](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0bvDDRebnw1/img/957799b6-0152-46c6-a774-b3c2304e64a1.png?Expires=1778766694&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=n58PtnAzpGZQ0e3d0f0Jk56vrQE%3D "")

![Picture 12](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0bvDDRebnw1/img/5efde71e-ee9e-4ca1-91e0-246cd4b485e0.png?Expires=1778766694&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=pbeHyXeD8RvGQ8xgcxsghuvGJMA%3D "")

![Picture 13](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0bvDDRebnw1/img/57322381-d931-4b5c-98e9-d3777758e900.png?Expires=1778766694&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=TaduScXYwhv1RtISWXVo8KheBZE%3D "")

![Picture 14](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0bvDDRebnw1/img/c498c3d1-5024-411c-85e5-56f42d5f189e.png?Expires=1778766694&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=kh%2BKtXMnEfovw%2B%2BoQ9L%2B0BygVPM%3D "")

![Picture 15](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0bvDDRebnw1/img/da3cc207-da99-4b88-a1e9-bd9e22dacf5d.png?Expires=1778766694&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=zXZ1Q8mLYJAZr%2BoFdW8af%2F%2BP%2BHU%3D "")

![Picture 16](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0bvDDRebnw1/img/9a270280-7ae4-43a4-b102-228a5432a30f.png?Expires=1778766694&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=9KWp%2Brw8CPX%2BYjVSQbCvpr3Lw7Y%3D "")

![Picture 17](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0bvDDRebnw1/img/f4eb401d-0f69-4039-a9c9-1a44b9953ba8.png?Expires=1778766694&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=2sdrd%2BSJUaUT%2FCBAXEheXMRObwc%3D "")

![Picture 18](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0bvDDRebnw1/img/123db089-ec14-4f7a-9d6c-9172374af1ab.png?Expires=1778766694&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=9DzNirkZMn7tdMwJ%2FL%2FfRyO2K2M%3D "")

![Picture 19](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0bvDDRebnw1/img/b59f24cd-6565-4da5-8bc0-3e11e6b02bba.png?Expires=1778766694&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=asCYoRTgCFH9rjXfUa7%2BsIFPAU0%3D "")

MB端原型：

![Picture 20](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4jKqm0bvDDRebnw1/img/246c18bd-9d1f-495a-848e-c39b50a97928.png?Expires=1778766694&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=eaXQ%2FNpQ4gdBD1z%2FbfH6EXYOPGo%3D "")
