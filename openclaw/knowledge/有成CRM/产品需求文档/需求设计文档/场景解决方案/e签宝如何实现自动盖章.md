---
title: "e签宝如何实现自动盖章"
nodeId: Y1OQX0akWm3gpzNXTvj1Dq5YJGlDd3mE
workspaceId: R2PmK2Q8rxRbeXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/Y1OQX0akWm3gpzNXTvj1Dq5YJGlDd3mE?utm_scene=team_space"
updateTime: 1779967159000
exportedAt: 2026-05-28T11:23:14.763Z
source: dingtalk-document-mcp
---
## **先看效果**

:::
若自动盖章只盖单页章，发起签署的所有文档中并没有找到配置的盖章关键字，那么无法完成自动盖章，将自动转为手动盖章
:::

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ZWGl05m1Do4YZn34/img/1b8eb8aa-4a43-4a43-87c3-0cd31311dd03.png?Expires=1779974595&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=o9Kr%2FUOHHfFU79pdrjibxCTE5iQ%3D "")

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ZWGl05m1Do4YZn34/img/72123b83-6c70-4204-a466-3161d8a56e0e.png?Expires=1779974595&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=tTYuxZZXM4U53VSRr4BXRCBe2Yw%3D "")

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ZWGl05m1Do4YZn34/img/0bb3e27d-09fe-46c6-8c25-df29aba018f4.png?Expires=1779974595&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=3iOoWh5rdPvyqLfDpCa%2Bb2fKzTc%3D "")

## **步骤一：CRM中完成自动盖章配置**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ZWGl05m1Do4YZn34/img/ab7152a3-1c41-472f-9f54-b33f1715278b.png?Expires=1779974595&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=3LAgTIHVOFWo7UbAwBULMqpJNdY%3D "")

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ZWGl05m1Do4YZn34/img/35dc3a2e-a0b3-46e8-a40d-5c08d34c6d31.png?Expires=1779974595&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=8WW0iYblgEogFGZEo9GCHo2dWYI%3D "")

1.1 满足自动盖章条件：即单据满足什么条件，才会发起后自动盖章

1.2 盖章位置

1） 单页章：可设置关键字（如甲方、盖章等，可多个），依据配置的关键字，定位自动签章的位置

2）骑缝章
- 可选择所有页码都盖骑缝章
- 可选择指定页码盖骑缝章

## **步骤二：e签宝中完成印章授权**

自动盖章配置中所选的印章（不管是单页章还是骑缝章），要能真正在发起签署后自动盖上，需要前往e签宝中进行印章授权（授权有成CRM应用能发起自动盖章）

#### **新增授权**

新增授权时所需填写的信息如下
- 企业名称：杭州光云科技股份有限公司
- 企业证件号：*91330108077312600N*
- 授权应用：5111626896

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ZWGl05m1Do4YZn34/img/6d06caaa-a826-4fd3-bc98-d43cb66ba96a.png?Expires=1779974595&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=Q3DbDca55vkn%2BZvBVEtVgGwYYDA%3D "")

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ZWGl05m1Do4YZn34/img/601d8f89-4774-4714-92ab-c1787f85d09d.png?Expires=1779974595&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=nSrxoY3kqi5Kl%2B8c5RCpTp8yroU%3D "")

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ZWGl05m1Do4YZn34/img/65ee5383-fb30-4d24-8515-b5f49f11e283.png?Expires=1779974595&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=W2RDNqa03uGVrv0E6wsfOe0PVzM%3D "")

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ZWGl05m1Do4YZn34/img/ccee8448-2bfd-4598-aee9-424b64446ba2.png?Expires=1779974595&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=Up62a0DoCM7WNhOVMeszkGRxkbM%3D "")

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ZWGl05m1Do4YZn34/img/04685137-0642-4263-8f42-73eb9942dd5f.png?Expires=1779974595&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=DFKOg3uEsNOR3wf7mSKsYoadWh0%3D "")

#### **查看/管理授权**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ZWGl05m1Do4YZn34/img/8d94e11a-de4b-4a41-a0d1-0cf0df31bb2a.png?Expires=1779974595&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=SZaKlgXHhL7r%2FEnsOGlyPmeXlTA%3D "")

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ZWGl05m1Do4YZn34/img/bd1f2ef8-0f21-4d04-b5a6-cc585f32acf2.png?Expires=1779974595&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=A5jlAYQnJZ83ewtUmLNxWSN2JqE%3D "")


