---
title: "自定义logo和主题色"
tags:
  - 有成报销
  - PRD
  - 需求设计-系统设置-自�
created: 2026-03-24
source: 钉钉文档
original_url: https://alidocs.dingtalk.com/i/nodes/Y1OQX0akWm3gpzNXTYk1DmjrJGlDd3mE?utm_scene=team_space
node_id: Y1OQX0akWm3gpzNXTYk1DmjrJGlDd3mE
exported_at: 2026-03-22
---

# 自定义logo和主题色

> 🔗 **原文链接**：[自定义logo和主题色 - 钉钉文档](https://alidocs.dingtalk.com/i/nodes/Y1OQX0akWm3gpzNXTYk1DmjrJGlDd3mE?utm_scene=team_space)

# 自定义logo和主题色

| **修订时间** | **版本** | **修订说明** |
|----------------|----------|----------------|
| 20230818 | v1.0 | 新建 |
| 20230915 | v1.1 | 新增4.1.2 配置及控制区域说明 |

## 1、需求背景

客户：禾川科技

客户要求系统界面上不要展示有成相关元素，主要是导航条的logo以及浏览页标签里的logo和标题。考虑到logo更换后，可能与报销系统蓝色的整体配色不协调，本次还增加了对导航条、左侧菜单栏颜色的自定义功能。

## 2、业务流程/架构

## 3、功能清单

| **模块** | **功能点** | **备注** |
|----------|-------------|----------|
| 系统设置 | 增加菜单“主题色和logo” |  |
| 系统设置/主题色和logo | 支持用户自定义主题色、头部导航logo和浏览器标签logo及标题 |  |
| 系统设置/角色权限 | 在功能授权中系统设置分类里增加“主题色和logo”模块的授权 |  |

## 4、需求详情

#### 4.1 增加主题色和logo菜单

##### 4.1.1 页面功能及交互如图

设计稿需增加：导航logo和网页标签logo支持用户上传后进行剪裁。


![Picture 1](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/AJdl65Aj9v3dQOke/img/7090022f-3922-4870-bf58-ac5a69f6d6d0.png?Expires=1774157486&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=eeg99W6LJGm92Mvl9Orv5DIDnrY%3D "")

##### 4.1.2 配置及控制区域说明

| **配置项** | **控制区域** |  |
|-------------|----------------|---|
|  | **钉钉打开** | **浏览器打开** |
| 主题色 | 最终效果：中间操作区域的按钮、tab、字体的颜色也能一起替换。本次可以只做部分按钮和tab的颜色替换，视前端工作量而定，后续持续改进即可。 | 最终效果：中间操作区域的按钮、tab、字体的颜色也能一起替换。本次可以只做部分按钮和tab的颜色替换，视前端工作量而定，后续持续改进即可。 |
| 头部导航logo |  |  |
| 网页标题与logo | 无法控制钉钉内的网页标题和logo，需要客户在其钉钉管理后台修改。 |  |

![Picture 2](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/AJdl65Aj9v3dQOke/img/e68dc9df-eaaf-4215-94f7-d7255d4eb1a3.png?Expires=1774157486&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=dSupLEF%2FCmf9YWqv5YHKqgWUvOY%3D "")

![Picture 3](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/AJdl65Aj9v3dQOke/img/7e3ba539-5d0c-4eb4-8523-e6e2816507e7.png?Expires=1774157486&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=xHpZJbJOYAr8ZuC%2FmHvxniKAo4Y%3D "")

![Picture 4](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/AJdl65Aj9v3dQOke/img/dbd2dbde-b928-46f8-8e0b-326fe5e1c54a.png?Expires=1774157486&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=pXsskONaYslxXCT1pN2KBEqZ70g%3D "")

![Picture 5](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/AJdl65Aj9v3dQOke/img/ce61fe3d-98aa-463d-9884-b1d5a5e6bc56.png?Expires=1774157486&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=1d3ORRG0OYSnwrrAJMqiCP3De%2F4%3D "")

![Picture 6](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/AJdl65Aj9v3dQOke/img/a91241ac-376c-49da-963d-86739fb40dd7.png?Expires=1774157486&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=UwSiAk2HTNmWOfxZvlGQPrMhQZk%3D "")

#### 4.2 权限

本次新增的菜单支持功能授权，在系统设置分类里增加“主题色和logo”模块的授权，系统管理员默认勾选。


![Picture 7](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/AJdl65Aj9v3dQOke/img/b0aca082-97b8-437d-8395-04b4e09be246.png?Expires=1774157486&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=CvKsGvgnez9tHp6shI0wRrYIHQo%3D "")

#### 4.3 导航条logo处增加设置入口

对于有权限设置主题色与logo的用户，在页面上点击导航条logo区域（红色框出的区域），直接打开主题色与logo设置页。没有权限的用户点击无效。


![Picture 8](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/AJdl65Aj9v3dQOke/img/df555a5d-7058-4efa-9e22-1f6651099429.png?Expires=1774157486&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=FRorQY83AXYHQv0H82JyR6fvDW0%3D "")

## 设计稿

[<u>https://www.figma.com/file/THUSQ5rRVKLafOw5E80A76/%E6%9C%89%E6%88%90%E6%8A%A5%E9%94%80-PC%E7%AB%AF?type=design&node-id=1464-59667&mode=design</u>](https://www.figma.com/file/THUSQ5rRVKLafOw5E80A76/%E6%9C%89%E6%88%90%E6%8A%A5%E9%94%80-PC%E7%AB%AF?type=design&amp;node-id=1464-59667&amp;mode=design)
