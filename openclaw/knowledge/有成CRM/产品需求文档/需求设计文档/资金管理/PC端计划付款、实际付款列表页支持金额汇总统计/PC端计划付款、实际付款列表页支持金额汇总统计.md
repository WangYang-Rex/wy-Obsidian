---
title: "PC端计划付款、实际付款列表页支持金额汇总统计"
nodeId: Y1OQX0akWm3gpzNXTYkPMx42JGlDd3mE
workspaceId: R2PmK2Q8rxRbeXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/Y1OQX0akWm3gpzNXTYkPMx42JGlDd3mE?utm_scene=team_space"
exportedAt: 2026-03-31T04:12:38.400Z
source: dingtalk-document-mcp
---
# PC端计划付款、实际付款列表页支持金额汇总统计

| **修订时间** | **版本** | **修订说明** |
|----------------|----------|----------------|
| 20220117 | v1.0 | 新建 |
|  |  |  |

## 1、需求背景

期望计划付款、实际付款列表页能快捷查看汇总金额

## 2、业务流程/架构

暂无

## 3、功能清单

| **模块** | **功能点** | **备注** |
|----------|-------------|----------|
| 计划付款 | 新增指标“实际付款总额”、“未付款金额” |  |
| 实际付款 | 新增指标“实际付款总额” |  |
|  |  |  |

## 4、需求详情

### 4.1、PC端计划付款列表页支持金额汇总统计

1、计划付款列表页，右下角新增指标“实际付款总额”、“未付款金额”

实际付款总额：取筛选结果所有计划付款的“实付金额”之和

未付款总额：取筛选结果所有计划付款的“未付款金额”之和

2、区分币种展示



![Picture 1](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/YdgOk2b1Q30PKq4B/img/8b5e54cd-9520-4bbe-a17e-ed0b73f666ab.png?Expires=1774937560&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=CNf9jHcUFr8uYqPDzsOLoGQcplY%3D "")

### 4.2、PC端实际付款列表页支持金额汇总统计

1、实际付款列表页，右下角新增指标“实际付款总额”

实际付款总额：取筛选结果所有计划付款的“实际付款金额”之和

2、区分币种展示



![Picture 2](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/YdgOk2b1Q30PKq4B/img/169ef8f5-8194-4738-b184-55dfa77e98f0.png?Expires=1774937560&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=F9eK%2F0OgL%2Bs3CMnM4Vv5OcuVYi0%3D "")
