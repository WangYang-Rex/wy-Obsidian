---
title: "PC端字段显示优化"
nodeId: dQPGYqjpJYg0lZOdIdE4D0B5Wakx1Z5N
workspaceId: R2PmK2gngjVnZXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/dQPGYqjpJYg0lZOdIdE4D0B5Wakx1Z5N?utm_scene=team_space"
exportedAt: 2026-04-01T02:16:40.311Z
source: dingtalk-document-mcp
---
# PC端字段显示优化

| **修订时间** | **版本** | **修订说明** | **作者** |
|----------------|----------|----------------|----------|
| 20240223 | v1.0 | 新建 | 秦国栋 |

## 1、需求背景

背景：目前字段显示

需求：对列表页的按钮、操作、功能布局等制定一定的规范要求，所有列表页都需要按照规范来执行

## 2、业务流程/架构



![Picture 1](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1GXn45Kb1kQKkqDQ/img/51dd4a67-dc79-4d10-9d30-5a4a2b0d1acd.png?Expires=1775017000&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=v%2FXITs6%2FIHEgLAeEwhkpYAKe0WI%3D "")

## 3、功能清单

根据个人需要补充

| **模块** | **功能点** | **备注** |
|----------|-------------|----------|
| 字段显示调整 | 字段显示交互调整、增加固定列设置 |  |
| 历史客户引导 | 对历史客户增加操作引导功能 |  |

## 4、需求详情

### 4.1、字段显示交互调整、增加固定列设置

1、字段显示因为不常用，居右对齐

2、字段显示左侧增加「刷新」按钮，点击后根据搜索条件更新列表内容、字段显示等

3、点击「字段显示」设置后会有弹框进行设置显示字段、位置、左侧固定列：
- 弹窗左侧为可选字段，可模糊搜索、勾选单个字段、勾选全部
- 弹窗右侧是已选字段，可将已选字段进行拖动位置、删除选择、添加为固定列
- 删除和清空字段时，左侧可选字段对应勾选也取消
- 弹窗右侧顶部显示已经选择字段数量、清空按钮
- 已选字段点击「添加为固定列」按钮会将字段置于顶部，可添加多个字段为固定列，最多10个，超过10个将禁用添加固定列按钮，并toast提示：最多可添加10个固定列字段
- 添加为固定列字段，第一次添加的在顶部，后续添加在其下方，同时支持拖动
- 拖动时，固定列字段仅限在固定列范围内拖动，其他字段仅限在下方拖动，不可跨区域

4、字段设置至少选择1个字段，否则确认按钮禁用



![Picture 2](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1GXn45Kb1kQKkqDQ/img/e637db05-4fe4-4670-861f-5152b049dbe8.png?Expires=1775017000&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=5Koe1VwNJmfRUVc7jAQKZG192iY%3D "")



![Picture 3](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/1GXn45Kb1kQKkqDQ/img/41a59485-3d1a-4e00-859c-30c8fa8f7183.png?Expires=1775017000&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=tYsD%2FTZGVPl4noP7IEw8y3m7LoY%3D "")
