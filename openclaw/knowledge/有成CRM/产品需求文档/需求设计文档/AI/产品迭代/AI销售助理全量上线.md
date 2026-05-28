---
title: "AI销售助理全量上线"
nodeId: YMyQA2dXW793dgQZTpn5EnMzJzlwrZgb
workspaceId: R2PmK2Q8rxRbeXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/YMyQA2dXW793dgQZTpn5EnMzJzlwrZgb?utm_scene=team_space"
exportedAt: 2026-03-31T03:48:55.046Z
source: dingtalk-document-mcp
---
| 修订时间 | 版本 | 修订人 | 修订说明 |
|-----------------------------------------------------------------------|-----------------------------------------------------------------|--------------------------------------------------------------------|-----------------------------------------------------------------------|
| 2025-11-27 | v1.0 | 黄艺平 | 新建 |
|  |  |  |  |

## 需求详情

| 需求 | 描述 |
|-----------------------------------------------------------------|-----------------------------------------------------------------|
| 增加弹窗 | 功能上线后，新旧企业所有用户均弹窗pc\+mb（1个用户只弹1次）<br>备注：无ai销售助理的功能权限，点击【去使用】提示‘暂无权限，请联系贵企业CRM管理员开通’<br>![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eYVOL5j8R3GdGlpz/img/b7f597df-919a-4930-9b6e-065e416dc67f.png?Expires=1774934031&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=aH%2FrkRhkDAbmncPJb%2FpBzgI8F%2BQ%3D "") |
| 全企业默认开通AI销售助理 | 1、未付费企业：默认全部开通，到日期=应用到期日<br>2、付费企业：默认全部开通，历史客户到日期=上线日\+15天<br>3、支持后台下单<br><ul><li>订单类型：单选，枚举‘试用订单’‘正式订单’</li><br><li>失效日期：选日期，只能选择当前日期及之后（存数据库时失效日期取23:59:59）</li><br><li>保存时校验（剔除已作废的订单）</li><br><li style="margin-left:1em">已有正式订单，不可再新建试用订单，保存失败并提示‘已下正式订单的企业，不可再建试用订单’---目的是拿来判断页面说明文案显隐</li><br><li>【作废】订单</li><br><li style="margin-left:1em">作废弹窗文案：作废订单后，可能影响企业AI销售助理到期时间计算，是否确认作废？</li></ul><br>![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eYVOL5j8R3GdGlpz/img/c426c279-1d00-40ce-9c08-a3fe9234a1f2.png?Expires=1774934031&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=%2BCNDuDBKvK7LAgjSxT00abfDlTI%3D "")<br>4、应用中心展示应用使用情况<br>UI：<br>[https://www.figma.com/design/z48HU1flOaZxM8PuxxVJfc/%E6%9C%89%E6%88%90CRM-PC2024?node-id=1529-33109&p=f](https://www.figma.com/design/z48HU1flOaZxM8PuxxVJfc/%E6%9C%89%E6%88%90CRM-PC2024?node-id=1529-33109&p=f)<br>![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eYVOL5j8R3GdGlpz/img/060672af-774d-428d-be6b-c1d899476e3f.png?Expires=1774934031&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=TVI%2BsBhs3fJpqXp0SYAWP3v1eS0%3D "")<br>4、功能上线时，除以下企业，所有企业所有角色均有以下功能权限<br>![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eYVOL5j8R3GdGlpz/img/6472f2d4-80ca-4c72-a399-e1b770bd4785.png?Expires=1774934031&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=lcL%2BhCa9qJqTIskWDjh8STLDDyY%3D "")<br>轮趣科技（东莞）有限公司 dingb55b1930d8d38ed835c2f4657eb6378f<br>广州汉马自动化控制设备有限公司 ding26dc9aa73d6a61d9a1320dcb25e91351<br>杭州皓焜科技有限公司 ding3a10aacf2dfe714cacaaa37764f94726<br>南宁市聚链五金机电有限公司 ding18a07f6c967b671035c2f4657eb6378f<br>笨鸟集团渠道联盟 ding96479bbd378e45bf35c2f4657eb6378f<br>钉学(杭州)科技有限公司 ding939a85cb101e83b0<br>南京沃天科技股份有限公司 dingbbd1f73b8f3ae6a835c2f4657eb6378f <br>潍坊乐丰生物农药有限公司 ding8a3ee755a6f7794bf2c783f7214b6d69 <br>山东广鹏 dinge8c68638bfc7351935c2f4657eb6378f<br>南京天创智能科技股份有限公司 dingd472b05babca489f<br>浙江有数数字科技有限公司 dingf283a1a43baf1ccf<br>南京贝奇尔 ding575c40b75f1fee1ff5bf40eda33b7ba0<br>广州聚鸿化工科技有限公司 dingbc39d819c71957a5<br>西朗门业(苏州)有限公司 dingaafc9b9cdb72a8fb35c2f4657eb6378f<br>恒策咨询  ding1a74ffc40ba1cca6 <br>南京蜂芒软件有限公司 ding1279a41f55f50046<br>杭州其乐融融科技有限公司 dingae6534c3c9b77f8535c2f4657eb6378f <br>长沙光云科技有限公司 ding43bcafb7be530398a1320dcb25e91351<br>杭州快小智科技有限公司 dinga3ba7e70fb12804ba1320dcb25e91351 <br>快麦硬件事业部 dingac386c5ee5e85e0eacaaa37764f94726 <br>快麦人工智能事业部 ding64be52bc1e66579cf2c783f7214b6d69 <br>快麦CRM ding61851b9f675d504ff5bf40eda33b7ba0 <br>有成系列客户管理平台 ding74d88e04ad655ab435c2f4657eb6378f<br>杭州快云 ding180b4617ce28f3b135c2f4657eb6378f   |
| 增加说明 | 付费企业，在后台有下正式订单（剔除已作废订单），说明内容隐藏<br>![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eYVOL5j8R3GdGlpz/img/04205494-89ea-4201-a472-aafa2eba449e.png?Expires=1774934031&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=242KqI4KoAjsrQKYh639AiBRYgw%3D "") |
| 增加功能宣传页（仅pc） | ui：<br>[https://www.figma.com/design/z48HU1flOaZxM8PuxxVJfc/%E6%9C%89%E6%88%90CRM-PC2024?node-id=1772-32067&t=sh2PSXsCA7N5kzul-1](https://www.figma.com/design/z48HU1flOaZxM8PuxxVJfc/%E6%9C%89%E6%88%90CRM-PC2024?node-id=1772-32067&t=sh2PSXsCA7N5kzul-1)<br>![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/eYVOL5j8R3GdGlpz/img/5b632ab1-e4a4-42b2-b26e-0e1f68d84b41.png?Expires=1774934031&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=q6jJjwA%2FMOMCX3Zz%2FrU%2Bba%2FKm6Y%3D "") |


