---
title: "字段AI提取/填充"
nodeId: o14dA3GK8g5NgQvGFKKEZPEDV9ekBD76
workspaceId: R2PmK2Q8rxRbeXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/o14dA3GK8g5NgQvGFKKEZPEDV9ekBD76?utm_scene=team_space"
updateTime: 1779868157000
exportedAt: 2026-05-28T11:23:19.260Z
source: dingtalk-document-mcp
---
| 修订时间 | 版本 | 修订人 | 修订说明 |
|-----------------------------------------------------------------------|-----------------------------------------------------------------|--------------------------------------------------------------------|-----------------------------------------------------------------------|
| 2026-5-27 | v1.0 | 黄艺平 | 新建 |
|  |  |  |  |

## 需求详情

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4EZlweZM6KLK9qxA/img/9d3a5ac7-5d28-41c8-ac58-a9e2068a9fa7.png?Expires=1779974600&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=653C8ae3%2Fl%2BYTnlqdCBNTHqzWvU%3D "")

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4EZlweZM6KLK9qxA/img/3c8afd55-9e58-4ad3-b6a6-d4a26b4dafaf.png?Expires=1779974600&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=JntRQ3FUW4qxg8MYSmf0wgTy%2BeY%3D "")



| 需求 | 描述 |
|-----------------------------------------------------------------|-----------------------------------------------------------------|
| 字段AI提取/填充 | 一、字段增加AI信息提取/填充配置<br><ul><li>1. 支持配置的控件类型：单行文本、多行文本、图片、附件</li><br><li>2. 提取/填充选项：必填，三个选项值</li><br><li style="margin-left:1em">1. 无需提取/填充：默认此选项</li><br><li style="margin-left:1em">2. 自定义提取/填充：可设置自定义规则</li><br><li style="margin-left:2em">1. 信息提取后填充至字段</li><br><li style="margin-left:3em">填充至此字段</li><br><li style="margin-left:4em">必填</li><br><li style="margin-left:4em">可选择本对象中以下字段类型：单行文本、多行文本、单选、多选、多级单选、网址、手机、电话、整数、小数、传真、邮件、金额、身份证、日期、日期时间、百分比、关联单选、关联多选、人员单选、人员多选、部门单选、部门多选、地址、银行组件（组件类型控件，在配置时需要拆分多个字段，如银行组件，在此处可选 账号、账户名称、账户类型、银行名称、开户省、开户市、开户行）</li><br><li style="margin-left:4em">同一字段不可多次被重复选中</li><br><li style="margin-left:3em">字段说明：选填，至多填写50字符</li><br><li style="margin-left:2em">2. 预览调试：依据当前配置的字段类型，同pc端新建页面样式</li><br><li style="margin-left:2em">3. 返回结果：以 ‘字段名：字段值’的格式返回，多个字段则换行</li><br><li style="margin-left:1em">3. 智能填充</li><br><li>3. 单对象最多可1个字段设置选项为‘自定义提取/填充’或‘智能填充’，达到上限时其余字段该设置上述2个选项不可见；配置了‘自定义提取/填充’或‘智能填充’的字段被隐藏，同样也是在隐藏字段中加红色标记（同AI值）</li><br>![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/4EZlweZM6KLK9qxA/img/d531ffa4-db34-45d3-a875-e5c31db2c048.png?Expires=1779974600&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=%2FS0Y7opKlKu%2BACLQIdfPEgeSmRg%3D "")<br>二、新建编辑页<br><li>1. AI值获取的icon变更为新版（AI生成），见原型</li><br><li>2. 单行/多行文本类型字段</li><br><li style="margin-left:1em">1. 设置了‘自定义提取/填充’或‘智能填充’的字段，有‘AI提取’按钮</li><br><li style="margin-left:1em">2. AI销售助理已过期：弹窗提示（同AI生成）</li><br><li style="margin-left:1em">3. AI销售助理未过期</li><br><li style="margin-left:2em">1. 自定义填充：依据自定义提取/填充配置，完成提取-\>填充</li><br><li style="margin-left:2em">2. 智能填充：同在悬浮窗中新建单据，解析当前字段内容（文字）-\>获取当前模板中所需填写字段-\>归纳--\>填充</li><br><li>3. 图片/附件类型字段</li><br><li style="margin-left:1em">4. 企业文件存储配置选了‘有成CRM服务器’且 设置了‘自定义提取/填充’或‘智能填充’的字段，有‘AI提取’按钮，且展示提示（见原型）</li><br><li style="margin-left:1em">5. AI销售助理已过期：弹窗提示（同AI生成）</li><br><li style="margin-left:1em">6. AI销售助理未过期：只取前6个符合条件的文档</li><br><li style="margin-left:2em">3. 没有符合条件的文档： toast提示‘AI提取数据失败：没有符合条件的文件’</li><br><li style="margin-left:2em">4. 有符合条件的文档</li><br><li style="margin-left:3em">自定义填充：依据自定义提取/填充配置，完成提取-\>填充</li><br><li style="margin-left:3em">智能填充：同在悬浮窗中新建单据，解析当前字段内容（文字）-\>获取当前模板中所需填写字段-\>归纳--\>填充</li></ul> |
