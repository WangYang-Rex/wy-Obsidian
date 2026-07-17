---
title: "【报销V2】补充首页AI助手指引以及联系方式"
nodeId: Gl6Pm2Db8D3mXMgZTezLxLlQJxLq0Ee4
workspaceId: R2PmK2gngjVnZXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/Gl6Pm2Db8D3mXMgZTezLxLlQJxLq0Ee4?utm_scene=team_space"
updateTime: 1784105895000
exportedAt: 2026-07-16T11:07:57.102Z
source: dingtalk-document-mcp
---
| 修订时间 | 版本 | 修订说明 |
|------------|------|------------|
| 2026.7.9 | v1.0 | 新建 |
|  |  |  |

# **1\. 需求背景**

提升AI助理全面开放使用频率，具备强指引，提高用户体感

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

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/XNkOM5j2Z64VKOY7/img/9c0e402b-aea3-45fc-bdee-a6ec029e5459.png?Expires=1784207277&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=txcYlqwNFGBtl8CwXLzZvpN1%2FN8%3D "")
1. 新增“AI助理”“售前联系方式”
2. 新增随手记、AI助理、售前联系方式的可见开关
3. 初始化上线后，默认开启，可手动关闭

#### **4.1.2APP端**

首页--设置APP首页--编辑/新增模版--设置展示模块

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/XNkOM5j2Z64VKOY7/img/167ba82f-64f8-49b5-83bf-63243e172868.png?Expires=1784207277&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=3qCpsa4hFk1oCsKGO5yvPnP4FrU%3D "")
1. 新增“AI助理”“售前联系方式”
2. 新增随手记、AI助理、售前联系方式的可见开关
3. 初始化上线后，默认开启，可手动关闭

### **4.2展示效果**

#### **4.2.1PC端**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/XNkOM5j2Z64VKOY7/img/60fad849-84c0-4f4f-b489-296cf5f61bc7.png?Expires=1784207277&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=pE0nCdlJ1ParPDvkg%2B5uNgu3UyE%3D "")

AI助理：
1. AI助理卡片放在左侧，内容：（标题：AI助理；     副标题：报销、问数、分析、客服、查标准）

[AI助理卡片_等距机器人版.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/XNkOM5j2Z64VKOY7/att/0277e8b1-52e6-45f6-8b95-17275cbc94ab.png?Expires=1784207277&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=1yikT7XEmpUAeX%2FRX%2FzzLFZmIcY%3D)
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

![](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/XNkOM5j2Z64VKOY7/img/4c740444-2c90-4d59-bc5c-33e91aac77d0.png?Expires=1784207277&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=deT3vr09gN%2FD78dwKvHKrSPBqas%3D "")

如果用户个性化了：

1、左侧无论怎么个性化，要么记费用和创建单据在一行，要么记费用和创建单据分别占一行。那么新加的AI助理就放在创建单据的右侧

2、右侧无论怎么个性化，要么就是放在通知这个组件下，要么就是放在放在最上面

#### **4.2.2APP端**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/XNkOM5j2Z64VKOY7/img/b2bda10d-fdd2-4015-b246-a4627dcc4bfd.png?Expires=1784207277&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=7%2FySkO%2BB%2BYKzVKcV6NKPBYehiLY%3D "")

AI助理：
1. 放在顶部栏内【按照一行五个图标来展示，超出则重起一行单独展示】
2. 同样需要设计埋点【AI数据统计报表：需要记录在该板块进行统计】MB端首页-AI助理点击坐标：：10790.79422.80690.80691.97048

注：APP端也需要针对于AI助理卡片进行点击事件的埋点统计，与PC端的分开统计

[AI助理2.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/XNkOM5j2Z64VKOY7/att/7cdd4674-33aa-4c32-a245-3f187e935607.png?Expires=1784207277&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=cmt9uGP%2Fy6mUGFgHiKgVWe%2FmDIQ%3D)

售前售后联系方式：
1. 固定交互两行展示：售前联系：清歌 19975294512；售后联系：蓝湛 19357165801
2. 每一行右侧有对应的查看二维码按钮[售前和售后联系方式](https://alidocs.dingtalk.com/i/nodes/14lgGw3P8vvl0xnzIg71l7yL85daZ90D?utm_scene=team_space)
点击即可弹窗展示二维码图片。
3. 电话号码需要支持点击，直接调手机拨号页面
4. 同样要求不同的产品环境展示不同的二维码图片，但是联系方式均相同
