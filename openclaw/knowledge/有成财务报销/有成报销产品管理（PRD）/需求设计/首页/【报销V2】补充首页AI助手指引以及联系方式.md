---
title: "【报销V2】补充首页AI助手指引以及联系方式"
nodeId: Gl6Pm2Db8D3mXMgZTezLxLlQJxLq0Ee4
workspaceId: R2PmK2gngjVnZXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/Gl6Pm2Db8D3mXMgZTezLxLlQJxLq0Ee4?utm_scene=team_space"
updateTime: 1784613486000
exportedAt: 2026-08-12T04:19:33.572Z
source: dingtalk-document-mcp
---
| 修订时间 | 版本 | 修订说明 |
|------------|------|------------|
| 2026.7.9 | v1.0 | 新建 |
| 2026.7.21 | v1.1 | 把PC端和移动端的随手记开关控制展示功能移除，后续再处理 |

# **1\. 需求背景**

<span style="color: rgb(41, 46, 51);">提升AI助理全面开放使用频率，具备强指引，提高用户体感</span>

# **2\. 业务流程/架构**

# **3\. 功能清单**

| 模块 | 功能点 | 备注 |
|------|---------|------|
| 首页 | 自定义板块新增AI助理、售前联系方式以及开关控制 |  |
|  |  |  |

# **4\. 需求详情**

### **4.1首页模版配置**

#### **4.1.1PC端**

首页--设置PC首页--编辑/新增模版--设置展示模块

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/XNkOM5j2Z64VKOY7/img/9c0e402b-aea3-45fc-bdee-a6ec029e5459.png?Expires=1786515445&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=KlzxfbeOWq2gIjPM0UsTr%2FpVet8%3D "")
1. 新增“AI助理”“售前联系方式”
2. 新增<span style="background-color: #FE0300;">~~随手记~~</span>、AI助理、售前联系方式的可见开关
3. 初始化上线后，默认开启，可手动关闭

#### **4.1.2APP端**

首页--设置APP首页--编辑/新增模版--设置展示模块

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/XNkOM5j2Z64VKOY7/img/167ba82f-64f8-49b5-83bf-63243e172868.png?Expires=1786515445&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=wHqabSjxHf%2BWsQm4ZIDaFU7Sogk%3D "")
1. 新增“AI助理”“售前联系方式”
2. 新增<span style="background-color: #FE0300;">~~随手记~~</span>、AI助理、售前联系方式的可见开关
3. 初始化上线后，默认开启，可手动关闭

### **4.2展示效果**

#### **4.2.1PC端**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/XNkOM5j2Z64VKOY7/img/60fad849-84c0-4f4f-b489-296cf5f61bc7.png?Expires=1786515445&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=Do51a1UeLnh881ES1LpjedGUrDo%3D "")

AI助理：
1. AI助理卡片放在左侧，内容：（标题：AI助理；     副标题：报销、问数、分析、客服、查标准）

[ai-assistant-card.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/XNkOM5j2Z64VKOY7/att/4c441c40-006a-4611-b074-7218e301830d.png?Expires=1786515445&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=%2BiyqGbvuNZIPsLxK57R%2F%2B6fuVV8%3D)
2. 缩小原本的记费用、创建单据组件，跟AI助理共占一行【默认样式】
3. 当记费用、创建单据、AI助理完成拖拽移动或者不展示后，组件也不会放大，维持调整后的大小
4. 指引还是保留现有逻辑，展示AI报销的指引流程
5. 需要点击事件埋点，记录AI助理使用次数进行后续数据统计
    1. AI数据统计报表：需要记录在该板块进行统计

注：需要分别针对于AI助理卡片和右侧的Ai助理悬浮球进行点击事件的埋点统计

PC首页-AI助理点击坐标：10790.79422.80689.80705.97046

PC首页-AI助理LOGO点击坐标：10790.79422.80689.80705.97047







售前售后联系方式：
1. 固定交互两行展示：售前联系：清歌 19975294512；售后联系：蓝湛 19357165801
2. 每一行右侧会有对应的查看二维码按钮[售前和售后联系方式](https://alidocs.dingtalk.com/i/nodes/14lgGw3P8vvl0xnzIg71l7yL85daZ90D?utm_scene=team_space)
点击即可弹窗展示二维码图片
3. 要求不同的产品环境展示不同的二维码图片，但是联系方式均相同



**处理规则：**

如果用户没做过调整，也就是初始化的规则，那就是这个图的位置

![](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/XNkOM5j2Z64VKOY7/img/4c740444-2c90-4d59-bc5c-33e91aac77d0.png?Expires=1786515445&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=5nqakmgziH6rfNxWcK9eR%2BpuEQQ%3D "")

如果用户个性化了：

1、左侧无论怎么个性化，要么记费用和创建单据在一行，要么记费用和创建单据分别占一行。那么新加的AI助理就放在创建单据的右侧

2、右侧无论怎么个性化，要么就是放在通知这个组件下，要么就是放在放在最上面





#### **4.2.2APP端**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/XNkOM5j2Z64VKOY7/img/b2bda10d-fdd2-4015-b246-a4627dcc4bfd.png?Expires=1786515445&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=DZ1aXwV%2B1fJ2Kz9twPSy1bOOY%2FU%3D "")

AI助理：
1. 放在顶部栏内【按照一行五个图标来展示，超出则重起一行单独展示】
2. 同样需要设计埋点【AI数据统计报表：需要记录在该板块进行统计】MB端首页-AI助理点击坐标：：10790.79422.80690.80691.97048

注：APP端也需要针对于AI助理卡片进行点击事件的埋点统计，与PC端的分开统计

[AI助理2.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/XNkOM5j2Z64VKOY7/att/7cdd4674-33aa-4c32-a245-3f187e935607.png?Expires=1786515445&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=4c%2BaKS1aJPkFG9M5G0TnA%2Bnj31M%3D)



售前售后联系方式：
1. 固定交互两行展示：售前联系：清歌 19975294512；售后联系：蓝湛 19357165801
2. 每一行右侧有对应的查看二维码按钮[售前和售后联系方式](https://alidocs.dingtalk.com/i/nodes/14lgGw3P8vvl0xnzIg71l7yL85daZ90D?utm_scene=team_space)
点击即可弹窗展示二维码图片。
3. 电话号码需要支持点击，直接调手机拨号页面
4. 同样要求不同的产品环境展示不同的二维码图片，但是联系方式均相同



注：特殊逻辑，由于AI助理已经全部开放试用，所以不再需要购买才会出现该悬浮组件。所以不影响首页的AI助理卡片的展示，无非就是点击后还有流量正常使用，没有流量就不使用了
