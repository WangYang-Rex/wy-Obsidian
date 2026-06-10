---
title: "其乐融融如何实现e签宝自动盖章"
nodeId: ZgpG2NdyVXrOqRxzHG7BN9rK8MwvDqPk
workspaceId: R2PmK2Q8rxRbeXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/ZgpG2NdyVXrOqRxzHG7BN9rK8MwvDqPk?utm_scene=team_space"
updateTime: 1780042866000
exportedAt: 2026-06-09T12:20:19.959Z
source: dingtalk-document-mcp
---
## **先看效果**

:::
若自动盖章只盖单页章，发起签署的所有文档中并没有找到配置的盖章关键字，那么无法完成自动盖章，将自动转为手动盖章
:::

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ZWGl05m1Do4YZn34/img/1b8eb8aa-4a43-4a43-87c3-0cd31311dd03.png?Expires=1781014820&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=7okGhCYTWPH%2FN5qeIp3ceoGYtbo%3D "")

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ZWGl05m1Do4YZn34/img/72123b83-6c70-4204-a466-3161d8a56e0e.png?Expires=1781014820&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=WMXapNmq3iF4AOlwcMCOQiwMJHM%3D "")

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ZWGl05m1Do4YZn34/img/0bb3e27d-09fe-46c6-8c25-df29aba018f4.png?Expires=1781014820&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=oAC%2F1rAY3vs6TuYxbXR5r%2B6KQ3Q%3D "")



## **操作步骤**

### **步骤一：重新授权**

实现自动盖章，在配置、盖章环节，均需要获取e签宝的印章的查询接口，故在完成e签宝授权有成CMR应用上，按照要求需要有截图中的授权（实际我们只调用了印章的查询接口，不会通过有成CRM进行印章的新增、编辑、授权、删除等操作）

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ZWGl05m1Do4YZn34/img/b5cb8f93-2629-443b-b498-bd49de01b799.png?Expires=1781014820&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=d45KrUQHKDBEj3Dk9rUUxLhw%2Bgk%3D "")

因上一次授权还不支持自动盖章，所以本次要实现自动盖章，需要新增授权（本次授权较上次就是增加了第一项印章相关），授权时点击下面的链接：

[实名授权](https://h5.esign.cn/auth/h5/index?authFlowId=OF-3dc100fe12080032&clientType=ALL&appId=5111626896)

重新授权的授权内容如下：

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ZWGl05m1Do4YZn34/img/932e5af9-f122-49da-a39f-88d1280f5f06.png?Expires=1781014820&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=VPTl7sRD8Jg2kEUnn3RdBE4tNbk%3D "")

### **步骤二：e签宝中完成印章授权**

自动盖章配置中所选的印章（不管是单页章还是骑缝章），要能真正在发起签署后自动盖上，需要前往e签宝中进行印章授权（授权有成CRM应用能发起自动盖章）

#### **新增授权**

新增授权时所需填写的信息如下
- 企业名称：杭州光云科技股份有限公司
- 企业证件号：*91330108077312600N*
- 授权应用：5111626896

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ZWGl05m1Do4YZn34/img/6d06caaa-a826-4fd3-bc98-d43cb66ba96a.png?Expires=1781014820&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=ULYcaDTWSkii3hI0Wc96OQXKQes%3D "")

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ZWGl05m1Do4YZn34/img/601d8f89-4774-4714-92ab-c1787f85d09d.png?Expires=1781014820&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=Znb8cJ5j5i6mV%2Br%2BkdWewEKxhBQ%3D "")

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ZWGl05m1Do4YZn34/img/65ee5383-fb30-4d24-8515-b5f49f11e283.png?Expires=1781014820&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=7Veg2viT0JYDgL4Gnx0HhgzMQms%3D "")

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ZWGl05m1Do4YZn34/img/ccee8448-2bfd-4598-aee9-424b64446ba2.png?Expires=1781014820&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=Z8CoHFj4uP72j15t7AhYevBkUL0%3D "")

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ZWGl05m1Do4YZn34/img/04685137-0642-4263-8f42-73eb9942dd5f.png?Expires=1781014820&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=vILrKBvxq6L4k%2BUGxkBWsYt6Kjg%3D "")

#### **查看/管理授权**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ZWGl05m1Do4YZn34/img/8d94e11a-de4b-4a41-a0d1-0cf0df31bb2a.png?Expires=1781014820&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=FJyz%2BnVQLbIDbuwy2ItWk3Y4FsY%3D "")

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/ZWGl05m1Do4YZn34/img/bd1f2ef8-0f21-4d04-b5a6-cc585f32acf2.png?Expires=1781014820&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=6UBhPbKzwpY3EDeEYp1P8Czx4rM%3D "")




